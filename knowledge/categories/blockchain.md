# 区块链充值对账安全 (Blockchain Deposit Reconciliation)

> 来源: TRC20/ERC20 标准、TronGrid API 文档、授权事故复盘
> 条目数: 1 | 分类: 区块链 (Blockchain)

---

### [KB-BLK-01] USDT approve 伪装充值（链上对账事件类型混淆）
- **信号**: 平台提供 TRC20/ERC20 地址充值自动上分；对账接口返回含 Approval 事件；充值确认仅校验 solidity 回执 SUCCESS；用户未转账但账户余额增加、充值地址链上无入账
- **原理**: `approve(spender, amount)` 是授权声明（允许 spender 最多划走 amount），不转移资金。TronGrid `/v1/accounts/{addr}/transactions/trc20?only_to=true` 会同时返回 Transfer 与 Approval，且 Approval 的 spender 位于 to 字段，导致充值地址命中；对账若未过滤事件类型，会把授权额度误写为充值金额。`solidity SUCCESS` 对 approve 同样成立，无法作为到账依据
- **最小PoC**: 对平台充值地址发起 `approve(充值地址, 1000 USDT)`（方法选择器 `095ea7b3`），观察平台是否上分而链上无 Transfer（topic `ddf252ad…`）；正常转账应为 `a9059cbb` + Transfer 事件（topic `8c5be1e5…` 为 Approval）
- **绕过与变体**: 多次 approve 放大金额；ERC20 同构（EVM 链同样适用）；对账轮询窗口内批量提交
- **修复**: 落库只认 `type=Transfer`；上分前校验 solidity + 本地址等额 USDT Transfer 事件；事件类型按 topic0 白名单；异常单标记 invalid + 告警；提现侧交叉验证链上真实入账
- **参考**: TRC20 标准（Tron Improvement Proposal）、TronGrid API docs、CWE-20（输入验证不当）

---
