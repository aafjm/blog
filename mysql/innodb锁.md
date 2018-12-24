类型| innodb | MyISAM | 
---|---|---
count(*) | 不存储 | 存储
全文索引 | 5.6之前不支持 | 支持
==事务== | 支持 | 不支持
外键 | 支持 | 不支持
锁 | 支持==行锁== | 只支持表锁


### InnoDB的mvcc设计
- ==redo==：修改行为先写到redo日志里，再定期刷到磁盘上。（随即写优化为顺序写）
- ==undo==：有修改行为时，旧版本放到undo日志里，回滚用的undo日志
- ==回滚段==：存放unido日志的地方

> innodb支持高并发的原因：mvcc的设计，实现了快照读（一致性不加锁）

### select
- select * from t where id>2; 不加锁
- select * from t where id>2 lock in share mode; 加锁
- select * from t where id>2 for update; 加锁

### innodb七种锁
- 自增锁（有自增列的表的插入）（表）
- 共享锁（读）  排他锁（修改删除）（行）
- 意向锁（共享&排他）（表）为了表锁获取，快速避免冲突
- 插入意向锁（没有自增列的插入的前置锁）
- 记录锁（select * from t where id=1 for update;）(行)
- 间隙锁（锁索引记录的间隔）防止幻读 （行）
- 临建锁（记录锁+间隙锁）防止幻读（行）

### show engine innodb status;查看死锁



