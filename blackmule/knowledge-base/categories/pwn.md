# PWN - 渗透技巧

---
## 2026-07-21

### [PWN-01] PHP zend_mm Off-by-one 堆溢出
- **信号**: X-PHP-Version header 存在, debug输出 input_len 或 strlen 信息, 自定义 .so PHP扩展
- **原理**: PHP自定义扩展中使用 _emalloc(n) 但实际写入 n+1 字节，
导致 null byte 溢出到相邻 heap chunk 的 metadata。
在PHP 8.1 zend_mm allocator中可导致free list corruption。

- **最小PoC**: 见技术卡 php-zendmm-offbyone
- **绕过与变体**: 待补充
- **修复**: 待补充
- **来源**: 技术卡: php-zendmm-offbyone
