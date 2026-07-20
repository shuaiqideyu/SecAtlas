<div align="center">
  <img src="./assets/brand/secatlas-cover.svg" alt="SecAtlas 网络渗透知识库" width="100%" />

  <p><strong>面向安全学习者、工程师与研发团队的结构化中文网络渗透知识库</strong></p>

  <p>
    <a href="#项目概览">项目概览</a>
    <span>&nbsp;·&nbsp;</span>
    <a href="#内容全景">内容全景</a>
    <span>&nbsp;·&nbsp;</span>
    <a href="#精选入口">精选入口</a>
    <span>&nbsp;·&nbsp;</span>
    <a href="#黑骡知识中枢">黑骡知识中枢</a>
    <span>&nbsp;·&nbsp;</span>
    <a href="#学习路线">学习路线</a>
    <span>&nbsp;·&nbsp;</span>
    <a href="#参与和支持">参与和支持</a>
  </p>

  <p>
    <a href="https://github.com/shuaiqideyu/SecAtlas/stargazers">
      <img alt="GitHub Stars" src="https://img.shields.io/github/stars/shuaiqideyu/SecAtlas?style=for-the-badge&logo=github&label=Stars&color=D7B468&labelColor=07131F" />
    </a>
    <a href="https://github.com/shuaiqideyu/SecAtlas/forks">
      <img alt="GitHub Forks" src="https://img.shields.io/github/forks/shuaiqideyu/SecAtlas?style=for-the-badge&logo=github&label=Forks&color=35C9DC&labelColor=07131F" />
    </a>
    <a href="https://github.com/shuaiqideyu/SecAtlas/commits/main">
      <img alt="Last Commit" src="https://img.shields.io/github/last-commit/shuaiqideyu/SecAtlas?style=for-the-badge&logo=git&label=Updated&color=4D8E9E&labelColor=07131F" />
    </a>
  </p>

  <p>
    <img alt="Maintained by BlackMule" src="https://img.shields.io/badge/MAINTAINED_BY-BLACKMULE-D7B468?style=flat-square&labelColor=07131F" />
    <img alt="Language" src="https://img.shields.io/badge/LANGUAGE-简体中文-35C9DC?style=flat-square&labelColor=07131F" />
    <img alt="Focus" src="https://img.shields.io/badge/FOCUS-PENETRATION_TESTING-4D8E9E?style=flat-square&labelColor=07131F" />
  </p>
</div>

## 项目概览

**SecAtlas** 以企业级内容治理方式组织网络渗透知识，将分散的技术资料统一为可检索、可复核、可持续维护的学习体系。

每个专题围绕一条完整闭环展开：

`漏洞原理 → 攻击面 → 最低影响验证 → 证据判断 → 修复建议 → 回归复测`

项目适合：

- 希望系统学习 Web、API、协议、云与供应链安全的学习者；
- 需要建立授权测试、代码审计和复测方法的安全工程师；
- 需要理解漏洞根因、修复边界与验证证据的研发团队；
- 需要检索漏洞分类、技术卡和案例的实战人员。

### 当前内容规模

| 深度专题 | 漏洞分类索引 | 技术卡 | 案例 | DNS Runbooks |
| ---: | ---: | ---: | ---: | ---: |
| **9** | **14** | **8** | **3** | **10** |

## 内容全景

| 领域 | 专题入口 | 核心内容 |
| --- | --- | --- |
| **注入安全** | [SQL 注入公开学习路线](./通用漏洞技术/注入类/SQL注入/README.md) | 根因、漏洞形态、盲注、代码审计、修复、误判与实验室 |
| **现代身份认证** | [Passkey 与 WebAuthn](./通用漏洞技术/身份认证/Passkey与WebAuthn/README.md) | 依赖方验证、抗钓鱼边界、凭据生命周期与审计清单 |
| **OAuth / OIDC** | [授权码流与令牌重放防护](./通用漏洞技术/会话与令牌/TECH-2026-9700-OAuth2授权码流与令牌重放防护.md) | 回调绑定、PKCE、Issuer、Token 与重放防护 |
| **HTTP 协议边界** | [HTTP 请求走私与 Desync](./通用漏洞技术/请求与协议边界/HTTP请求走私与Desync/README.md) | 多组件解析差异、连接状态、证据门槛与复测 |
| **实时通信安全** | [WebSocket 与 SSE](./Web与API安全/WebSocket与SSE/README.md) | Origin、消息授权、订阅、恢复、资源治理与审计 |
| **DNS 安全** | [DNS 与 DNSSEC](./网络与协议安全/DNS与DNSSEC/README.md) | 委派、解析、DNSSEC、动态更新、重绑定与子域接管 |
| **TLS 重放防护** | [TLS 1.3 0-RTT](./网络与协议安全/TLS_PKI与证书/TLS1.3-0RTT重放防护/README.md) | Early Data、反重放状态、业务幂等与多节点边界 |
| **云身份安全** | [元数据与工作负载身份](./云与云原生安全/元数据与工作负载身份/README.md) | 元数据入口、身份交换、云 IAM 与低影响验证 |
| **软件供应链** | [SBOM、签名与来源证明](./源码审计_供应链与DevSecOps/制品_签名_SBOM/README.md) | SBOM、VEX、Sigstore、in-toto、SLSA 与消费策略 |

## 精选入口

- **从零建立漏洞模型**：[SQL 注入公开学习路线](./通用漏洞技术/注入类/SQL注入/README.md) 提供从原理到修复复测的完整专题。
- **学习协议与证据判断**：[DNS/DNSSEC 授权渗透测试学习包](./网络与协议安全/DNS与DNSSEC/授权渗透测试学习包/README.md) 提供攻击面矩阵、证据判定和 10 篇 Runbook。
- **建立实时接口测试方法**：[WebSocket 与 SSE 攻击面](./Web与API安全/WebSocket与SSE/TECH-2026-6727-WebSocket与SSE攻击面与测试思路.md) 覆盖连接、消息、订阅和资源治理。
- **理解软件供应链信任**：[SBOM、签名与来源证明](./源码审计_供应链与DevSecOps/制品_签名_SBOM/README.md) 串联制品身份、签名、来源证明和 VEX。
- **快速检索实战知识**：[黑骡渗透知识库](./blackmule/README.md) 汇总漏洞分类、技术卡与案例。

## 黑骡知识中枢

[`blackmule`](./blackmule/README.md) 是 SecAtlas 的实战知识分区，也是项目后续的日常内容管理中枢。

| 分区 | 当前内容 | 入口 |
| --- | --- | --- |
| **Knowledge Base** | 14 类漏洞知识条目 | [总索引](./blackmule/knowledge-base/MASTER_INDEX.md) |
| **Techniques** | SQLi、IDOR、Pwn 共 8 张技术卡 | [技术卡目录](./blackmule/techniques/) |
| **Cases** | CTF 与 Pwn 共 3 份案例 | [案例目录](./blackmule/cases/) |

黑骡负责：

1. 维护专题目录、知识索引和公开入口；
2. 对新增内容进行分类、去重、来源核验和链接检查；
3. 将社区建议整理为专题、技术卡或案例更新；
4. 持续同步主 README 与仓库实际内容。

所有公开变更均通过 Git 提交记录保留完整轨迹。

## 学习路线

### 第一阶段：漏洞根因

从 [SQL 注入](./通用漏洞技术/注入类/SQL注入/README.md) 开始，掌握输入源、危险执行点、证据与根因修复之间的关系。

### 第二阶段：身份与应用协议

依次学习 [Passkey / WebAuthn](./通用漏洞技术/身份认证/Passkey与WebAuthn/README.md)、[OAuth / OIDC](./通用漏洞技术/会话与令牌/TECH-2026-9700-OAuth2授权码流与令牌重放防护.md)、[HTTP Desync](./通用漏洞技术/请求与协议边界/HTTP请求走私与Desync/README.md) 与 [WebSocket / SSE](./Web与API安全/WebSocket与SSE/README.md)。

### 第三阶段：基础设施与信任链

进入 [DNS / DNSSEC](./网络与协议安全/DNS与DNSSEC/README.md)、[TLS 1.3 0-RTT](./网络与协议安全/TLS_PKI与证书/TLS1.3-0RTT重放防护/README.md)、[云身份](./云与云原生安全/元数据与工作负载身份/README.md) 与 [软件供应链](./源码审计_供应链与DevSecOps/制品_签名_SBOM/README.md)。

### 第四阶段：技术卡与案例复盘

使用 [黑骡知识总索引](./blackmule/knowledge-base/MASTER_INDEX.md) 按漏洞类型检索，再结合 [技术卡](./blackmule/techniques/) 与 [案例](./blackmule/cases/) 复盘多漏洞组合。

## 内容标准

| 标准 | 要求 |
| --- | --- |
| **来源可追溯** | 优先引用标准、官方文档、源码、补丁和公开实验材料 |
| **范围可确认** | 主动验证面向自有系统、明确授权目标、官方实验室或隔离靶场 |
| **结论可复核** | 区分观察、假设、直接证据、推断结论与未验证范围 |
| **修复可落地** | 从漏洞根因提出修复方案，并使用相同条件完成复测 |
| **结构可维护** | 专题入口、技术正文、检查清单和来源索引保持一致 |

## 快速开始

```bash
git clone git@github.com:shuaiqideyu/SecAtlas.git
cd SecAtlas
```

推荐阅读顺序：

1. 从本页选择一个专题入口；
2. 阅读专题 README 与核心技术文档；
3. 使用检查清单梳理证据和复测条件；
4. 通过黑骡技术卡与案例完成复盘。

仓库采用 Markdown、JSONL、YAML 和 SVG，可直接阅读、全文检索或纳入团队内部知识系统。

## 参与和支持

如果 SecAtlas 对你的学习或工作有帮助，欢迎：

- [Star 本项目](https://github.com/shuaiqideyu/SecAtlas/stargazers)，帮助更多安全学习者发现这套资料；
- [提交 Issue](https://github.com/shuaiqideyu/SecAtlas/issues/new)，反馈事实错误、失效链接或专题建议；
- 提交 Pull Request，补充公开来源、技术卡、案例或修复说明；
- 分享你在授权实验环境中的学习路径和复测经验。

## 许可与使用

SecAtlas 用于网络安全学习、授权评估、代码审计与防护研究。仓库包含原创整理与不同许可条件的公开资料，第三方材料继续适用其原始许可与署名要求，详情见 [`LICENSES.md`](./LICENSES.md) 及各专题来源说明。

---

<div align="center">
  <strong>Built for security practitioners. Maintained by BlackMule.</strong>
  <br />
  <sub>SecAtlas is an independent knowledge project and is not affiliated with OWASP, MITRE, NIST, or referenced upstream projects.</sub>
</div>
