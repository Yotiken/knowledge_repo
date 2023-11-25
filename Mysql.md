### 什么是触发器

触发器是与表有关的数据库对象，在满足定义条件时触发，并执行触发器中定义的语句集合。`<br>`

- 么条件会触发：I、D、U
- 什么时候触发：在增删改前或者后
- 触发频率：针对**每一行**执行

  触发器是针对每一行的；对增删改非常频繁的表上切记不要使用触发器，因为它会非常消耗资源。`<br>`

### 了解mysql的索引设计吗？

### B+树有什么缺点？

1 写操作开销较大：B+树的插入和删除操作可能会导致树的结构调整，这涉及到节点的分裂和合并，可能导致大量的磁盘I/O操作和数据迁移，从而增加了写操作的开销。`<br>`2 不适合频繁的更新：由于B+树的写操作开销较大，它在频繁的数据更新场景下可能不是最优选择。对于需要大量的插入和删除操作的情况，可能会导致B+树频繁地进行结构调整，影响性能。`<br>`3 难以维护：B+树的结构较为复杂，维护起来相对困难。例如，当磁盘出现故障或数据损坏时，B+树可能需要进行修复，这可能需要较长的时间和计算资源。`<br>`4 不适合高并发写入：由于B+树需要频繁地进行结构调整，当多个事务并发地插入和删除数据时，可能会导致锁竞争，从而影响性能。`<br>`5 查询性能不一定最优：尽管B+树对于范围查询和有序性查找有很好的支持，但在某些特定查询场景下，其他索引结构可能会有更好的性能。例如，对于全文搜索等复杂查询，B+树并不是最优选择。`<br>`

### 什么情况下next-key会退化?

### 数据库redo log 和 undo log