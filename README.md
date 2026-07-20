<div align="center">
  <img src="./assets/brand/secatlas-cover.svg" alt="SecAtlas 网络渗透学习资料库" width="100%" />
</div>

<div align="center">
  <br />
  <a href="#核心专题">核心专题</a>
  <span>&nbsp;·&nbsp;</span>
  <a href="#学习路线">学习路线</a>
  <span>&nbsp;·&nbsp;</span>
  <a href="#实战资料">实战资料</a>
  <span>&nbsp;·&nbsp;</span>
  <a href="#快速开始">快速开始</a>
</div>

<div align="center">
  <br />
  <img alt="Learning Library" src="https://img.shields.io/badge/LEARNING-LIBRARY-0B2230?style=flat-square&labelColor=07131F" />
  <img alt="Chinese" src="https://img.shields.io/badge/LANGUAGE-简体中文-D7B468?style=flat-square&labelColor=07131F" />
  <img alt="Focus" src="https://img.shields.io/badge/FOCUS-PENETRATION_TESTING-35C9DC?style=flat-square&labelColor=07131F" />
</div>

## SecAtlas

**SecAtlas** 是一套中文网络渗透学习资料库，聚焦漏洞原理、攻击面分析、授权测试、代码审计、证据判断、修复与复测。

> [!NOTE]
> 仓库只保留与网络渗透学习直接相关的文字资料、技术卡和案例，不收录音视频、生成数据集、运行时文档或空目录骨架。

## 核心专题

| 分区 | 入口 | 用途 |
| --- | --- | --- |
| **通用漏洞** | [`通用漏洞技术`](./通用漏洞技术/) | SQL 注入、身份认证、OAuth/OIDC、HTTP 请求走私 |
| **Web 与 API** | [`Web与API安全`](./Web与API安全/) | WebSocket、SSE 与接口边界 |
| **网络协议** | [`网络与协议安全`](./网络与协议安全/) | DNS、DNSSEC、TLS、PKI 与 0-RTT |
| **云环境** | [`云与云原生安全`](./云与云原生安全/) | 元数据服务、工作负载身份与云权限边界 |
| **软件供应链** | [`源码审计与供应链`](./源码审计_供应链与DevSecOps/) | SBOM、制品签名、Sigstore、in-toto、SLSA 与 VEX |
| **漏洞与案例** | [`blackmule`](./blackmule/) | 漏洞分类、技术卡与靶场案例 |

## 学习路线

1. 从 [`SQL 注入`](./通用漏洞技术/注入类/SQL注入/) 学习漏洞根因、判断、代码审计和修复。
2. 继续学习 [`Passkey 与 WebAuthn`](./通用漏洞技术/身份认证/Passkey与WebAuthn/)、[`OAuth/OIDC`](./通用漏洞技术/会话与令牌/) 与 [`HTTP Desync`](./通用漏洞技术/请求与协议边界/HTTP请求走私与Desync/)。
3. 进入 [`WebSocket 与 SSE`](./Web与API安全/WebSocket与SSE/)、[`DNS/DNSSEC`](./网络与协议安全/DNS与DNSSEC/) 和 [`TLS 1.3 0-RTT`](./网络与协议安全/TLS_PKI与证书/TLS1.3-0RTT重放防护/)。
4. 扩展到 [`云身份`](./云与云原生安全/元数据与工作负载身份/) 与 [`软件供应链`](./源码审计_供应链与DevSecOps/制品_签名_SBOM/)。
5. 使用 [`blackmule`](./blackmule/) 中的分类条目、技术卡和案例进行复盘。

## 实战资料

| 子目录 | 用途 |
| --- | --- |
| [`knowledge-base`](./blackmule/knowledge-base/) | 按漏洞类型整理的知识索引与分类条目 |
| [`techniques`](./blackmule/techniques/) | 可复用技术卡（如 SQLi、IDOR、Pwn） |
| [`cases`](./blackmule/cases/) | CTF / Pwn 等案例记录 |

入口建议先看 [`knowledge-base/MASTER_INDEX.md`](./blackmule/knowledge-base/MASTER_INDEX.md)。

## 快速开始

```bash
git clone git@github.com:shuaiqideyu/SecAtlas.git
cd SecAtlas
```

仓库以 Markdown、JSON/JSONL、YAML 和 SVG 为主，可直接阅读与全文检索。

## 收录原则

- 只保留直接服务网络渗透学习的原理、测试方法、证据、修复、技术卡和案例。
- 不保留音频、视频、字幕、生成数据集、模型训练资料、运行时运维文档或空占位目录。
- 主动测试仅用于自有系统、明确授权目标、官方实验室或隔离靶场。
- 优先引用标准、官方文档、源码、补丁和可复现实验。

## 资料来源

仓库包含原创整理和公开资料，第三方内容仍适用其原始许可与署名要求，具体见 [`LICENSES.md`](./LICENSES.md) 及各资料目录中的来源说明。

---

<div align="center">
  <sub>SecAtlas is an independent knowledge project and is not affiliated with OWASP, MITRE, NIST, or referenced upstream projects.</sub>
</div>
