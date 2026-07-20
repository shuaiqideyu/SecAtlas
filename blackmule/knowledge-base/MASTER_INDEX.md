# 黑骡渗透知识库

> 来源：公开靶场、OWASP、PortSwigger、HackTricks、PayloadsAllTheThings 与公开规范

## 内容入口

- [`categories`](./categories/)：按漏洞类型整理的知识条目。
- [`techniques`](../techniques/)：可复用技术卡。
- [`cases`](../cases/)：靶场、CTF 与 Pwn 案例。

## 分类速览

| 类别 | 文件 | 覆盖主题 |
| --- | --- | --- |
| SQL 注入 | [`sqli.md`](./categories/sqli.md) | Union、Error、Blind、OOB、二阶注入 |
| XSS | [`xss.md`](./categories/xss.md) | Reflected、Stored、DOM、CSP、mXSS |
| SSRF | [`ssrf.md`](./categories/ssrf.md) | 内网访问、云元数据、协议与 DNS 边界 |
| 文件包含 | [`file-inclusion.md`](./categories/file-inclusion.md) | 路径穿越、Wrapper、日志与环境文件 |
| 命令注入 | [`command-injection.md`](./categories/command-injection.md) | 直接、盲注、参数与带外信号 |
| 反序列化 | [`deserialization.md`](./categories/deserialization.md) | Java、PHP、Python、Node.js、.NET |
| SSTI | [`ssti.md`](./categories/ssti.md) | 模板识别、沙箱边界与修复 |
| JWT | [`jwt.md`](./categories/jwt.md) | 算法、密钥、Header 与声明校验 |
| OAuth/OIDC | [`oauth.md`](./categories/oauth.md) | 回调、state、PKCE、Code 与 Token |
| 请求走私 | [`request-smuggling.md`](./categories/request-smuggling.md) | CL.TE、TE.CL、H2 与缓存边界 |
| 访问控制 | [`acl.md`](./categories/acl.md) | 权限、对象归属与策略边界 |
| IDOR | [`idor.md`](./categories/idor.md) | 对象级授权与枚举 |
| Pwn | [`pwn.md`](./categories/pwn.md) | 内存破坏与堆利用案例 |
| 综合技巧 | [`misc.md`](./categories/misc.md) | 侦察、前端逆向与组合漏洞 |

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
