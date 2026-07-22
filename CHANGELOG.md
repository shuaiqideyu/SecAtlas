# Changelog

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
- Repo root restructured: `blackmule/*` → top-level `techniques/`, `cases/`, `knowledge/`, `references/`, `tools/`
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
- `blackmule/` container directory
- Chinese-named technique cards (renamed)
- Case-derived duplicate technique cards (3)
- Stale README references to pre-restructure paths

## 2026-07-21 — Initial

- 46 Hermes security skills indexed
- 34 technique cards across 11 categories
- 14 knowledge categories (150+ entries)
- 11 case studies
- Multi-agent collaboration protocol (AGENTS.md)
