# 数据库

标签（空格分隔）： 计算机基础

---

数据的基地

## 分类

* 卡片式数据库：将一条数据存储到一张卡片上，各卡片间无关联关系
* 关系型数据库：数据被拆分整理到多张表中，同时记录表与表之间的关系

### 关系型数据库

* 表：被整理成表格形式的数据
* 行：记录，表中的每一行数据
* 列：字段，构成一条记录中的各个数据项，包括字段名和数据类型
* 拆表：将一张大表分割成多张小表，然后再在小表之间建立关系，避免重复存储相同的数据
* 主键：唯一地标识表中的一条记录，绝不能存储相同的值
* 外键：其他表的主键，通过主键与外键在表间建立关系
* 表关系：一对一、一对多、多对多，多对多可以加一个连接表分解成两个一对多的关系
* 索引：提升数据检索和排序速度的内部机制，可以在字段上设置索引
* 索引表：字段设置索引后，DBMS就会自动为这个字段创建索引表，存储字段数据和记录位置
* 建立索引：每次添加或删除记录时需要同步更新索引表，所以只为频繁检索、排序的字段建立索引

## 系统

![数据库系统](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/database-system.png)

* 数据文件：数据库的实质
* DBMS: Database Management System（数据库管理系统），如SQL Server、Oracle、DB2等，应用程序和数据文件的中介
* 应用程序：通过DBMS读写数据文件+

### 独立型

![独立型数据库系统](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/database-independent.png)

### 文件共享型

![文件共享型数据库系统](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/database-shared.png)

### 客户端/服务器型

![客户端/服务器型数据库系统](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/database-cs.png)

### Web型

![Web型数据库系统](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/database-web.png)

## 操作

CRUD，增删改查

* `CREATE`: 添加
* `REFER`: 获取
* `UPDATE`: 更新
* `DELETE`: 删除

## 事务

对数据库一系列相关操作的集合

* 开启事务
* 一组数据库操作
 * 成功，提交事务
 * 失败，回滚事务
