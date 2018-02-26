---
layout:         post
title:          inserted deleted 在触发器中的应用举例说明      
card-image:     
date:           2018-2-25 00:20:15
tags:           数据库
post-card-type: article
---


*学到触发器的时候看到有`inserted`以及`deleted`表，不明所以，上网查询之后发现这篇文章通过举例说明来讲解，通俗易懂。稍加整理之后留作以后查阅。*

```
建立4张表，t1,t2,t3,t4。

每张表有相同的字段。

id，主键，int(4)型，标识。

name，varchar(50)，

password，varchar(50)，

age，int(4)，

birthday，datetime,
```

---
## 1. 增加的触发器

###  1. t1，t2同时增加相同的字段的触发器
```sql
CREATE TRIGGER intest1

on t1

for insert

AS  

begin  

insert into t2

SELECT name,password,age,birthday

FROM inserted  

END
```

第一句建立触发器，名字是intest1

第2句是在t1表上建立

as是固定格式。

Bgein,end没有大用处，有没有都行。

inserted是临时表。Insert执行就有个inserted临时表，存放的是insert的记录，同样，delete语句也有个deleted临时表。Update语句可以看成先delete再insert。


### 2.  t1增加一条记录，t3里面相同name的字段，其password，age，birthday，修改成和t1增加记录相同的触发器

```sql
create trigger intest2

on t1

for insert

as

update t3

set password=inserted.password,age=inserted.age,birthday=inserted.birthday

from inserted

where

t3.name=inserted.name
```
当然，如果password想改成固定值，比如改成aaa，可以写成password=’aaa’等等

### 3. t1增加一条记录，t4里面相同name的字段，删除记录的触发器

```sql
create trigger intest3

on t1

for insert

as

delete from t4

where name in

(select name from inserted)
```
---
## 2. 删除的触发器

### 1. t2删除一条字段，t3里面insert刚刚删除t2的字段的触发器
```sql
CREATE TRIGGER detest1

on t2

for delete

AS     

insert into t3

SELECT name,password,age,birthday

FROM deleteed 
```
### 2. t2，删除一条字段，t4里面把相同name的字段的password，age，birthday，修改成和删除记录相同触发器
```sql
create trigger detest2

on t2

for delete

as

update t4

set password=deleted. password,age= deleted.age,birthday= deleted.birthday

from deleted

where

t4.name= deleted.name
```
### 3. 删除一条字段，t1里面把相同name的字段也删除的触发器
```sql
create trigger detest3

on t2

for delete

as

delete from t1

where name in

(select name from deleted)
```
---
## 3. 修改的触发器(修改相当于先删除，后增加)
### 1. 修改t1,则t3增加t1修改后记录的触发器

```sql
create TRIGGER uptest1

ON t1

FOR UPDATE

AS

insert into t3

SELECT name,password,age,birthday

FROM inserted 
```
如果是想要修改t1,则t3增加t1修改前记录的触发器

把最后一句改成FROM deleted

这样就好理解为什么update是相当于先删除，后增加了

### 2. 修改t1，则t2对应（name）的记录也修改成和t1一致的触发器
```
create TRIGGER uptest2

ON t1

FOR UPDATE

AS

update t2 set

name=inserted.name,password=inserted.password,age=inserted.age,birthday=inserted.birthday

from t1,inserted,deleted

where t2.name=deleted.name
```
### 3. 修改t1，则t4对应name的修改前的记录删除的触发器
```
create trigger uptest3

on t1

for update

as

delete from t4

where name in

(select name from deleted)
```
同理，如果是修改t1,则t4对应name的修改后的记录删除的触发器

则把最后一句改成select name from inserted

### 4. t3里面有两个字段，比如第一个字段name=aaa，password=已用，第二个字段name=bbb，password=未用；
t4里面有一个字段name=aaa；

现在如果要把t4中的那个name=aaa的字段，改成name=bbb；则t3里面对应的name=aaa的字段password=未用，name=bbb的字段password=已用

这样需要2个触发器
```
create TRIGGER uptest4

ON t4

FOR UPDATE

AS

update t3 set

password=’已用’

from t4,inserted,deleted

where t3.name=inserted.name
```
 
```
create TRIGGER uptest5

ON t4

FOR UPDATE

AS

update t3 set

password=’未用’

from t4,inserted,deleted

where t3.name=deleted.name
```
