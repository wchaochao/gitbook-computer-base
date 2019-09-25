# SQL

标签（空格分隔）： 计算机基础

---

Structural Query Language，结构化查询语言，用于访问和处理数据库的标准的计算机语言

* 不区分大小写
* 以分号为结尾

## select

查询

```sql
# 选取一个字段
select column_name from table_name;

# 选取多个字段
select column_name, column_name from table_name;

# 选取表中所有字段
select * from table_name;

# 字段去重
select distinct column_name from table_name;
```

示例

```sql
SELECT name, country FROM Websites;
SELECT * FROM Websites;
SELECT DISTINCT country FROM Websites;
```

### where

过滤

```sql
# 按条件过滤
select column_name, column_name from table_name where column_name operator value;

# 条件与
select column_name, column_name from table_name where column_name operator value and column_name operator value;

# 条件或
select column_name, column_name from table_name where column_name operator value or column_name operator value;
```

运算符

| 运算符 | 描述 |
| --- | --- |
| =	| 等于 |
| <> | 不等于 |
| >	| 大于 |
| <	| 小于 |
| >= | 大于等于 |
| <= | 小于等于
| between | 在某个范围内 |
| like | 搜索 |
| in | 可能值 |

示例

```sql
SELECT * FROM Websites WHERE country='CN';
SELECT * FROM Websites WHERE id=1;
SELECT * FROM Websites WHERE country='CN' AND alexa > 50;
SELECT * FROM Websites WHERE country='USA' OR country='CN';
SELECT * FROM Websites WHERE alexa > 15 AND (country='CN' OR country='USA');
```

### order by

排序，默认升序

```sql
# 按一个或多个字段升序或降序排列
select column_name, columen_name from table_name order by column_name, column_name asc | desc;
```

示例

```sql
SELECT * FROM Websites ORDER BY alexa;
SELECT * FROM Websites ORDER BY alexa DESC;
SELECT * FROM Websites ORDER BY country,alexa;
```

## insert

插入

```sql
# 不指定字段
insert into table_name values (value1, value2, value3, ...);

# 指定字段
insert into table_name (column1, column2, column3, ...) values (value1, value2, value3, ...);
```

示例

```sql
INSERT INTO Websites VALUES ('百度','https://www.baidu.com/','4','CN');
INSERT INTO Websites (name, url, country) VALUES ('stackoverflow', 'http://stackoverflow.com/', 'IND');
```

## update

更新

```sql
# 更新所有记录
update table_name set column1=value1, column2=value2, ...;

# 更新某些记录
update table_name set column1=value1, column2=value2, ... where some_column=some_value;
```

示例

```sql
UPDATE Websites SET alexa='5000', country='USA' WHERE name='菜鸟教程';
```

## delete

删除

```sql
# 删除所有记录
delete from table_name

# 删除某些记录
delete from table_name where some_column=some_value;
```

示例

```sql
DELETE FROM Websites WHERE name='百度' AND country='CN';
```
