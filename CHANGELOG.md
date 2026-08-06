# Changelog

## 2026-08-06 — 六合彩站复测与会话劫持利用链

### Added
- `cases/authorized/20260803-case-ruoyi-gambling-admin-api.yaml`：追加六合彩站复测结果——首轮管理接口越权已修复；新增 getInfo 密码哈希泄露（评级修正为低危设计缺陷，独立利用价值低）与上传 HTML 同源托管发现。
- 会话劫持利用链全链实证：上传 HTML 同源 → 窃取 token → 外传 → 接口验证（已追加至上述案例文件）。

### Fixed
- getInfo 密码哈希泄露评级：高危 → 低危设计缺陷（独立利用价值低）。

### Changed
- `README.md` / `MASTER_INDEX.md` / `CAPABILITY.md` / `SKILL_INDEX.md`：数字与实际内容对齐（案例 11→13、专题 56→57 篇、知识条目 150+→130+、Skill 索引标注 47 历史快照 + 4 当前活跃）；MASTER_INDEX 技术卡表补 payment-bypass 类。

## 2026-08-04 — 预测平台系 同族迁移站 API 签名密钥恢复

### Added
- `cases/authorized/20260804-case-预测平台系-signature-reversal.yaml`：同族迁移站 API 签名密钥黑盒恢复案例（含修复后复测结论）。

## 2026-08-03 — RuoYi 博彩站管理接口越权读写

### Added
- `cases/authorized/20260803-case-ruoyi-gambling-admin-api.yaml`：RuoYi 博彩站管理接口越权读写案例，含支付密钥泄露与 XSS 注入点。

## 2026-07-23 — OA/ERP 框架漏洞库

### Added
- `knowledge/frameworks/chinese-oa-erp-vulnerabilities.md`：国产 OA/ERP 漏洞库 — 通达OA(~55 CVE)、泛微OA(~16)、致远OA(~13)、用友(~12)、蓝凌、万户。含 FOFA 指纹、攻击链、默认口令。

### Added
- `knowledge/frameworks/ruoyi-vulnerabilities-full.md`：RuoYi(若依)框架漏洞全集 — 40 条 CVE（v3.0 ~ v4.8.0），按版本+危害分级，含 Shiro RCE、文件上传 RCE、SQL 注入、权限提升、未授权配置读写、Druid 未授权等 10 大类攻击面。
- `techniques/auth/ruoyi-captcha-bypass-2captcha.yaml`：RuoYi 验证码绕过技术卡（2captcha OCR）
- `techniques/api-bypass/ruoyi-unauth-config-write.yaml`：RuoYi 未授权配置读写技术卡

### Changed
- README：技术卡 37→40，知识条目 15→16，新增「框架漏洞」专区

## 2026-07-23 — AI Agent/MCP 闭环与校验修复

### Added
- `knowledge/categories/agentic-ai.md`：AI Agent/MCP 漏洞原理、最小验证、证据、修复与复测。
- `references/agentic-ai/`：攻击面控制对、证据停止点复测清单、来源与取舍。

### Fixed
- `scripts/validate.sh` 改用当前顶层目录，并正确累计校验错误；此前可能在未检查任何文件时报告通过。
- `agent-manifest.yaml` 修正重构后的目录路径和知识条目闭环要求。

## 2026-07-23 — v2.0 Restructure

### Added
- `CAPABILITY.md` — single-source capability index mapping all assets
- `poison-ops` Skill (6 poisoning chains) + 6 technique cards
- 4 executable tools: `jwt-analyzer.py`, `cache-poison-detector.go`, `js-extractor.py`, `redis-exploit.py`
- `mirrors/` with codex-keysmith, claude-keysmith, zcode-keysmith
- `.github/` with CI workflow and issue templates
- `SECURITY.md`
- `.editorconfig`

### Changed
- Repo root restructured: `mule/*` → top-level `techniques/`, `cases/`, `knowledge/`, `references/`, `tools/`
- `knowledge-base/` → `knowledge/`
- Chinese directory names in `references/` → English
- `README.md` fully rewritten with updated paths and stats
- `SKILL_INDEX.md` updated to 47 skills with poison-ops category

### Fixed
- `__pycache__/` no longer tracked
- `.gitignore` expanded (Python, OS, editor patterns)
- Broken internal links after restructure
- All case files sanitized (TARGET_HOST placeholder)

### Removed
- `mule/` container directory
- Chinese-named technique cards (renamed)
- Case-derived duplicate technique cards (3)
- Stale README references to pre-restructure paths

## 2026-07-21 — Initial

- 46 Hermes security skills indexed
- 34 technique cards across 11 categories
- 14 knowledge categories (150+ entries)
- 11 case studies
- Multi-agent collaboration protocol (AGENTS.md)
