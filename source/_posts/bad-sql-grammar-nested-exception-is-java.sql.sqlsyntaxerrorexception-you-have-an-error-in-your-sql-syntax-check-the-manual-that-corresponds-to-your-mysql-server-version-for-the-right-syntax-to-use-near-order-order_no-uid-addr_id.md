---
title: 'bad SQL grammar []; nested exception is java.sql.SQLSyntaxErrorException:
  You have an error in your SQL syntax; check the manual that corresponds to your
  MySQL server version for the right syntax to use near ''order (order_no, `uid`,
  addr_id, '
date: 2020-12-13T16:00:00Z
tags:
- SpringBoot
- 错误记录
categories: ''

---
> 记录专业实践过程中踩的坑

在订单表里添加记录的时候，显示报错如下：

```
cause: java.sql.SQLSyntaxErrorException: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'order (order_no, `uid`, addr_id, 
      amount, `type`, freight, 
      `status`' at line 1
; bad SQL grammar []; nested exception is java.sql.SQLSyntaxErrorException: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'order (order_no, `uid`, addr_id, 
      amount, `type`, freight, 
      `status`' at line 1v
...

```

经过排查，发现`order`是`sql`的保留字段（在排序的时候用到）；

由于订单表的名字也为`order`，再加上mapper是由mybatis自动生成的，所以这个冲突需要手动解决一下。

在`OrderMapper.xml`文件中，找到
```sql
 insert into order (order_no, `uid`, addr_id, 
      amount, `type`, freight, 
      `status`, payment_time, delivery_time, 
      finish_time, close_time, updated, 
      created)
```
将其中的`order`加上` ` `即可
即
```sql
 insert into `order` (order_no, `uid`, addr_id, 
      amount, `type`, freight, 
      `status`, payment_time, delivery_time, 
      finish_time, close_time, updated, 
      created)
```