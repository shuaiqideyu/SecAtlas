# MISC - 渗透技巧

---
## 2026-07-20

### [MISC-01] Express SPA: JS bundle 逆向必做 (搜 baseURL/api/fetch)
- **信号**: 见案例
- **原理**: Express SPA: JS bundle 逆向必做 (搜 baseURL/api/fetch)
- **最小PoC**: 见案例 20260720-digital-wallet-sqli-idor
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: Digital Wallet Lab
### [MISC-02] 万能密码 SQLi: username=' OR '1'='1 在 Node+SQLite 中有效
- **信号**: 见案例
- **原理**: 万能密码 SQLi: username=' OR '1'='1 在 Node+SQLite 中有效
- **最小PoC**: 见案例 20260720-digital-wallet-sqli-idor
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: Digital Wallet Lab
### [MISC-03] Boolean-based blind SQLi: 用登录成功/失败作为 Oracle
- **信号**: 见案例
- **原理**: Boolean-based blind SQLi: 用登录成功/失败作为 Oracle
- **最小PoC**: 见案例 20260720-digital-wallet-sqli-idor
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: Digital Wallet Lab
### [MISC-04] IDOR: RESTful /api/user/:id 常缺权限校验
- **信号**: 见案例
- **原理**: IDOR: RESTful /api/user/:id 常缺权限校验
- **最小PoC**: 见案例 20260720-digital-wallet-sqli-idor
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: Digital Wallet Lab
### [MISC-05] 业务逻辑: 负金额转账可绕过余额检查
- **信号**: 见案例
- **原理**: 业务逻辑: 负金额转账可绕过余额检查
- **最小PoC**: 见案例 20260720-digital-wallet-sqli-idor
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: Digital Wallet Lab
### [MISC-06] sqlite_master 可枚举所有表和结构
- **信号**: 见案例
- **原理**: sqlite_master 可枚举所有表和结构
- **最小PoC**: 见案例 20260720-digital-wallet-sqli-idor
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: Digital Wallet Lab
### [MISC-07] pragma_table_info('table') 可枚举列名
- **信号**: 见案例
- **原理**: pragma_table_info('table') 可枚举列名
- **最小PoC**: 见案例 20260720-digital-wallet-sqli-idor
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: Digital Wallet Lab
### [MISC-08] 文件扩展名不可信 (PNG 实为 JPEG)
- **信号**: 见案例
- **原理**: 文件扩展名不可信 (PNG 实为 JPEG)
- **最小PoC**: 见案例 20260720-fouji-tech-zwc
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: 否极科技 (Fouji Tech)
### [MISC-09] 1×1 像素图片高度可疑 → 使用 binwalk 检测
- **信号**: 见案例
- **原理**: 1×1 像素图片高度可疑 → 使用 binwalk 检测
- **最小PoC**: 见案例 20260720-fouji-tech-zwc
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: 否极科技 (Fouji Tech)
### [MISC-10] Zero-Width 字符隐写：U+200B/U+200C/U+200D 编码二进制
- **信号**: 见案例
- **原理**: Zero-Width 字符隐写：U+200B/U+200C/U+200D 编码二进制
- **最小PoC**: 见案例 20260720-fouji-tech-zwc
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: 否极科技 (Fouji Tech)
### [MISC-11] binwalk 可以检测内嵌文件 (ZIP/ELF/等)
- **信号**: 见案例
- **原理**: binwalk 可以检测内嵌文件 (ZIP/ELF/等)
- **最小PoC**: 见案例 20260720-fouji-tech-zwc
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: 否极科技 (Fouji Tech)

---
## 2026-07-21

### [MISC-01] PHP扩展.so文件可能包含完整源码逻辑
- **信号**: 见案例
- **原理**: PHP扩展.so文件可能包含完整源码逻辑
- **最小PoC**: 见案例 20260720-echoes-of-heap
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: Echoes of Heap
### [MISC-02] 反汇编PHP扩展: zif_函数名 + objdump -d + strings
- **信号**: 见案例
- **原理**: 反汇编PHP扩展: zif_函数名 + objdump -d + strings
- **最小PoC**: 见案例 20260720-echoes-of-heap
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: Echoes of Heap
### [MISC-03] PHP返回IS_FALSE = type_info=0x2, IS_TRUE=0x3
- **信号**: 见案例
- **原理**: PHP返回IS_FALSE = type_info=0x2, IS_TRUE=0x3
- **最小PoC**: 见案例 20260720-echoes-of-heap
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: Echoes of Heap
### [MISC-04] zend_mm allocator: small bins 8-2048, slab 256KB
- **信号**: 见案例
- **原理**: zend_mm allocator: small bins 8-2048, slab 256KB
- **最小PoC**: 见案例 20260720-echoes-of-heap
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: Echoes of Heap
### [MISC-05] off-by-one检测: 精确bin边界输入 → 响应大小差1字节
- **信号**: 见案例
- **原理**: off-by-one检测: 精确bin边界输入 → 响应大小差1字节
- **最小PoC**: 见案例 20260720-echoes-of-heap
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: Echoes of Heap
### [MISC-06] .bak/.swp/.orig 文件是PHP源码泄露的经典入口
- **信号**: 见案例
- **原理**: .bak/.swp/.orig 文件是PHP源码泄露的经典入口
- **最小PoC**: 见案例 20260720-echoes-of-heap
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 案例: Echoes of Heap
