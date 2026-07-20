# BlackMule Knowledge Hub

> SecAtlas 实战知识分区与日常内容管理中枢

[返回 SecAtlas 首页](../README.md) · [打开知识总索引](./knowledge-base/MASTER_INDEX.md)

## 概览

BlackMule 将漏洞知识、可复用技术和案例记录组织为三个相互关联的层级：

`漏洞分类 → 技术卡 → 案例复盘`

当前收录 **14 类漏洞索引（150+条目）、28 张技术卡（11类）和 9 份案例**，内容面向网络渗透学习、授权安全评估与复盘。

## 内容结构

| 分区 | 内容 | 规模 | 入口 |
| --- | --- | ---: | --- |
| **Knowledge Base** | SQLi、XSS、SSRF、文件包含、命令注入、反序列化、SSTI、JWT、OAuth、请求走私、访问控制、IDOR、Pwn 与综合技巧 | 150+ 条目 | [知识总索引](./knowledge-base/MASTER_INDEX.md) |
| **Techniques** | SQLi(5)、IDOR(3)、Pwn(1)、JWT(3)、SSRF(3)、SSTI(2)、命令注入(3)、请求走私(2)、反序列化(2)、XSS(2)、认证(1) | 28 张 | [技术卡目录](./techniques/) |
| **Cases** | CTF、Pwn、授权评估与靶场案例记录 | 9 份 | [案例目录](./cases/) |

## 最近更新 (2026-07-21)

### 新增技术卡 (17张)
- **JWT**: `alg-none` 签名绕过 · `rs256-to-hs256` 算法混淆 · `kid-injection` 头注入
- **SSRF**: `cloud-metadata` 云凭证窃取 · `scheme-bypass` 协议绕过 · `filter-bypass` IP过滤绕过
- **SSTI**: `jinja2-rce` Python RCE · `detection` 引擎识别
- **命令注入**: `blind-oob` OOB盲注 · `waf-bypass` WAF绕过 · `arg-injection` 参数注入
- **请求走私**: `cl-te` CL.TE走私 · `h2-downgrade` H2降级
- **反序列化**: `java-urldns` Java探测 · `php-pop` PHP POP链
- **XSS**: `reflected-stored` 反射/存储 · `dom-blind` DOM/盲XSS

### 补全分类条目
- **ACL** (12行→5条目): 水平/垂直越权、上下文绕过、CORS、IDOR
- **IDOR** (21行→5条目): RESTful枚举、复合引用、文件路径IDOR
- **PWN** (15行→5条目): 堆溢出、栈溢出、格式化字符串、整数溢出、UAF

## 推荐阅读方式

1. 在 [知识总索引](./knowledge-base/MASTER_INDEX.md) 中选择漏洞类型；
2. 阅读条目的信号、原理、验证方式和修复建议；
3. 进入对应技术卡，核对适用条件、证据和停止点；
4. 使用案例复盘多个技术点在同一场景中的组合关系。

## 项目管理

BlackMule 负责 SecAtlas 的日常内容管理：

- 维护目录结构、分类索引与公开导航；
- 对新增资料进行分类、去重、来源核验和链接检查；
- 将社区建议整理为专题、技术卡或案例更新；
- 同步主 README、知识索引与仓库实际内容；
- 通过 Git 提交记录保留可审计的更新轨迹。

## 内容约定

- 分类条目用于快速理解漏洞信号、原理、变体与修复；
- 技术卡用于记录可复用条件、最小验证、证据和边界；
- 案例用于复盘完整路径、关键判断和技术组合；
- 主动验证面向自有系统、明确授权目标、官方实验室或隔离靶场；
- 技术结论优先回溯到标准、官方文档、源码或公开实验材料。

## 参与完善

- [提交 Issue](https://github.com/shuaiqideyu/SecAtlas/issues/new) 反馈错误、失效来源或分类建议；
- 通过 Pull Request 补充技术卡、案例和公开来源；
- [Star SecAtlas](https://github.com/shuaiqideyu/SecAtlas/stargazers) 支持项目持续维护。
