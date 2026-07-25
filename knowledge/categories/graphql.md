# GraphQL 安全

> 来源：PortSwigger Web Security Academy、GraphQL Spec、HackTricks
> 前缀：KB-GQ

---

### [KB-GQ01] Introspection Leak — 内省信息泄露
- **类别**: GraphQL / Reconnaissance
- **信号**: `POST /graphql` 发送 `__schema` 或 `__type` 查询返回完整类型信息；`GET /graphql?sdl` 返回 SDL schema；GraphiQL/Playground/Voyager 可公开访问
- **原理**: GraphQL 规范定义内省系统（Introspection System），允许客户端通过 `__schema` 元字段查询所有类型、字段、参数、枚举值的完整定义。生产环境若未禁用，攻击者可获取完整 API 结构，发现隐藏查询（如 adminExport、userDump）、敏感字段（passwordHash、creditCardToken）及未文档化的 mutation
- **最小PoC**: 发送 `{"query":"{__schema{types{name fields{name}}}}"}` 到 `/graphql`，观察是否返回类型树。使用标准内省查询 `fragment FullType on __Type{...}` 可导出 100% schema
- **绕过与变体**: 若内省被禁用但字段推荐错误开启，发送 `{user{passwordzzz}}` 触发 `Did you mean passwordHash?` 泄露字段名；持久化查询模式下尝试发送空 hash 但附带内省 query；WebSocket 订阅端点可能绕过 HTTP 中间件的内省限制
- **修复**: 生产环境禁用内省（apollo-server: `introspection: false`；graphql-js: 中间件拦截 `__schema` 和 `__type`）；关闭字段推荐错误详情；使用持久化查询白名单
- **参考**: GraphQL Spec §4: Introspection; CWE-200

### [KB-GQ02] Alias Batching — 别名批量查询绕过速率限制
- **类别**: GraphQL / Rate Limit Bypass / Enumeration
- **信号**: 单次 HTTP 请求中包含多个相同查询字段但使用不同别名；速率限制基于请求数而非查询复杂度
- **原理**: GraphQL 支持字段别名（Aliases），允许在同一查询中对相同字段使用不同参数多次请求。攻击者利用此特性在单次 HTTP 请求中批量发送数十次查询（如枚举用户 ID 1-100），绕过基于请求数量的速率限制。若无查询成本分析（Query Cost Analysis），服务器资源被单次请求耗尽
- **最小PoC**: `{"query":"{u1:user(id:1){email}u2:user(id:2){email}u3:user(id:3){email}}"}` — 单次请求完成 3 次用户查询。实际攻击中可批量 50-100 别名
- **绕过与变体**: 结合 fragment 减少 payload 大小：`fragment f on User{email} query{u1:user(id:1){...f}u2:user(id:2){...f}}`；分批发送避开超时限制；利用订阅（subscription）持续获取实时数据变更
- **修复**: 实施查询成本分析（Query Cost Analysis）— 别名查询计入 N 倍成本；设置单次查询最大深度和最大字段数；按复杂度（而非请求数）做速率限制
- **参考**: PortSwigger: GraphQL rate limiting; Apollo GraphOS: query cost analysis; CWE-770

### [KB-GQ03] Batching + Brute-Force — 批量爆破攻击
- **类别**: GraphQL / Authentication / Brute Force
- **信号**: GraphQL 登录/验证 mutation 可在单次请求中被别名调用多次；无单次请求内失败计数限制
- **原理**: 若 GraphQL mutation 用于认证（如 `login(username, password)`），攻击者可通过别名在单次 HTTP 请求中同时尝试多个密码，绕过基于 IP 的登录失败速率限制和账户锁定策略。服务器在单次请求上下文中处理所有别名查询，可能未对单次请求内的失败次数做计数
- **最小PoC**: `mutation{a:login(user:"admin",pass:"pass1"){token}b:login(user:"admin",pass:"pass2"){token}c:login(user:"admin",pass:"pass3"){token}}` — 单次请求测试 3 个密码，若任一成功返回 token
- **绕过与变体**: 结合变量（variables）动态传入密码列表；使用 fragment 复用 mutation 定义；WebSocket 订阅发送持续登录尝试流
- **修复**: 对 mutation 添加单次请求内操作数上限；认证 mutation 必须添加验证码或 proof-of-work；限流基于尝试次数（含别名）而非 HTTP 请求数
- **参考**: PortSwigger: GraphQL brute force; OWASP: GraphQL Cheat Sheet; CWE-307

### [KB-GQ04] Depth / Breadth DoS — 递归查询拒绝服务
- **类别**: GraphQL / Denial of Service
- **信号**: 目标 GraphQL 端点未限制查询深度或宽度；schema 中存在循环引用类型
- **原理**: GraphQL 查询可嵌套多层，若 schema 中存在循环引用（如 User → friends → User → friends ...），攻击者可构造深度嵌套查询导致服务器递归解析所有层级，耗尽 CPU/内存。类似地，大量并列字段（广度攻击）可造成数据库 N+1 问题被放大
- **最小PoC**: `{user{name friends{name friends{name friends{name friends{name friends{name friends{name}}}}}}}}` — 深度嵌套查询。广度攻击：`{user{field1 field2 ... field1000}}`
- **绕过与变体**: 使用 fragment 递归展开：`fragment f on User{...f}` 触发服务端无限展开；结合批量别名同时发送多个深度查询
- **修复**: 设置查询最大深度（max depth，通常 3-5）；设置单次查询最大字段数；使用查询成本分析为每个字段加权；设置查询超时（通常 5-10 秒）
- **参考**: GraphQL Spec §5: Validation; Apollo: query depth limiting; CWE-400

### [KB-GQ05] IDOR via Missing Field-Level Authorization
- **类别**: GraphQL / Authorization / IDOR
- **信号**: GraphQL 查询成功返回其他用户数据仅需修改参数（如 `user(id: 2)`），无服务端授权检查；同一 query 在不同用户上下文返回相同数据
- **原理**: GraphQL 的单一端点特性意味着所有数据通过同一个 `/graphql` 入口访问，若授权逻辑仅在 REST 层面实现而 GraphQL resolver 未做字段级访问控制，攻击者修改查询参数即可访问任意用户/资源的数据。GraphQL 的类型系统本身不包含授权语义
- **最小PoC**: 以用户 A 身份发送 `{user(id:2){email phone ssn}}`，若返回用户 B 的敏感数据即存在字段级 IDOR。同样尝试 `{orders(userId:2){id total cardLastFour}}`
- **绕过与变体**: 通过节点 ID（Node Interface / Global Object Identification）访问：`{node(id:"VXNlcjoy"){...on User{email}}}`；利用 batching 同时枚举多个 ID 加速发现
- **修复**: 在 GraphQL resolver 层（非 REST 中间件层）实施字段级授权；从认证上下文（如 JWT）获取当前用户标识，与请求参数校验；使用 DataLoader 批量加载时保持授权上下文
- **参考**: PortSwigger: GraphQL authorization flaws; OWASP: GraphQL Authorization; CWE-639

---
> 🤖 由 Claude Code 渗透员 贡献 · 2026-07-25
