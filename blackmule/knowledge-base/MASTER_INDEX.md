# 黑骡渗透知识库

> 来源：公开靶场、OWASP、PortSwigger、HackTricks、PayloadsAllTheThings 与公开规范

## 内容入口

- [`categories`](./categories/)：按漏洞类型整理的知识条目（14类 150+ 条目）。
- [`techniques`](../techniques/)：可复用技术卡（11类 20+ 张）。
- [`cases`](../cases/)：靶场、CTF 与 Pwn 案例。

## 分类速览

| 类别 | 文件 | 覆盖主题 | 条目数 |
| --- | --- | --- | ---: |
| SQL 注入 | [`sqli.md`](./categories/sqli.md) | Union、Error、Blind、OOB、二阶注入、NoSQL | 15 |
| XSS | [`xss.md`](./categories/xss.md) | Reflected、Stored、DOM、Blind、CSP、mXSS、SVG | 10 |
| SSRF | [`ssrf.md`](./categories/ssrf.md) | 内网访问、云元数据、协议与 DNS 边界 | 10 |
| 文件包含 | [`file-inclusion.md`](./categories/file-inclusion.md) | 路径穿越、Wrapper、日志与环境文件 | 10 |
| 命令注入 | [`command-injection.md`](./categories/command-injection.md) | 直接、盲注、参数与带外信号 | 10 |
| 反序列化 | [`deserialization.md`](./categories/deserialization.md) | Java、PHP、Python、Node.js、.NET | 10 |
| SSTI | [`ssti.md`](./categories/ssti.md) | 模板识别、沙箱边界与修复 | 10 |
| JWT | [`jwt.md`](./categories/jwt.md) | 算法、密钥、Header 与声明校验 | 10 |
| OAuth/OIDC | [`oauth.md`](./categories/oauth.md) | 回调、state、PKCE、Code 与 Token | 10 |
| 请求走私 | [`request-smuggling.md`](./categories/request-smuggling.md) | CL.TE、TE.CL、H2 与缓存边界 | 10 |
| 访问控制 | [`acl.md`](./categories/acl.md) | 水平越权、垂直越权、上下文绕过、CORS | 5 |
| IDOR | [`idor.md`](./categories/idor.md) | 对象级授权、复合引用、文件路径 | 5 |
| Pwn | [`pwn.md`](./categories/pwn.md) | 堆溢出、栈溢出、格式化字符串、UAF | 5 |
| 综合技巧 | [`misc.md`](./categories/misc.md) | 侦察、前端逆向、组合漏洞、隐写 | 17 |

## 技术卡目录

| 类别 | 数量 | 技术卡 |
| --- | ---: | --- |
| SQLi | 5 | 万能密码、布尔盲注、逐字符提取 |
| IDOR | 2 | RESTful枚举、批量探测 |
| Pwn | 1 | PHP off-by-one 堆溢出 |
| JWT | 3 | alg:none、RS→HS混淆、kid注入 |
| SSRF | 3 | Cloud Metadata、Scheme绕过、过滤绕过 |
| SSTI | 2 | Jinja2 RCE、通用检测/引擎识别 |
| 命令注入 | 3 | OOB盲注、WAF绕过、参数注入 |
| 请求走私 | 2 | CL.TE、H2降级 |
| 反序列化 | 2 | Java URLDNS、PHP POP链 |
| XSS | 2 | 反射/存储、DOM/盲XSS |

## 案例目录

| 编号 | 名称 | 漏洞类型 | 结果 |
| --- | --- | --- | --- |
| 1 | Digital Wallet Lab | SQLi + IDOR + 业务逻辑 | ✅ Flag |
| 2 | 否极科技 | 文件隐写 + ZWC | ✅ Flag |
| 3 | Echoes of Heap | PHP堆利用 off-by-one | ⚠️ 利用阻塞 |

## 阅读建议

1. 先按漏洞类型阅读分类条目，理解信号、原理、最小验证与修复。
2. 再结合技术卡查看具体条件、证据和停止点。
3. 最后通过案例复盘多漏洞组合与错误判断。
4. 主动验证只用于自有系统、明确授权目标或隔离靶场。

## 来源声明

条目依据以下公开资源独立整理：
- PortSwigger Web Security Academy (https://portswigger.net/web-security)
- OWASP Testing Guide / ASVS / Cheat Sheets
- HackTricks (https://book.hacktricks.wiki/)
- PayloadsAllTheThings (https://github.com/swisskyrepo/PayloadsAllTheThings)
- MITRE CWE (https://cwe.mitre.org/)
- IETF RFCs

不包含：付费课程内容、非公开靶场答案、真实目标信息、凭据或密钥。
