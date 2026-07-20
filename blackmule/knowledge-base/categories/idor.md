# IDOR - 渗透技巧

---
## 2026-07-20

### [IDOR-01] IDOR 枚举
- **信号**: 见技术卡
- **原理**: /api/user/1-6 全部可访问，无需权限校验
- **最小PoC**: 见技术卡 idor-枚举
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 技术卡: idor-枚举
### [IDOR-02] IDOR RESTful 用户枚举
- **信号**: /api/user/:id 或 /api/users/:id 端点, GET 请求返回用户 JSON, ID 为自增整数
- **原理**: 利用 RESTful API 的 /api/user/:id 端点，遍历 ID 获取所有用户信息。
常见于缺少权限校验的 Node.js/Express 后端。

- **最小PoC**: 见技术卡 restful-user-enum
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: [{'case': '20260720-digital-wallet-sqli-idor', 'outcome': '枚举 6 个用户完整信息'}]
