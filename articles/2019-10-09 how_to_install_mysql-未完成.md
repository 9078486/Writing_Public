TITLE:如何安装和使用MySQL

*本文主要涉及Python和MySQl的内容*

市场的数据库林林种种，有关系数据库，比如本文中提及的MySQL，Oracle、SQL Server。
有NoSQL（Not Only SQL）的，比如mongodb,redis,hbase。

# 常用SQL语句类型

## DDL 数据定义语言 如'CREATE'

## TPL 事务处理语言 

## DCL 数据控制语言 

## DML 数据操作语言 如'SELECT', 'INSERT', 'UPDATE', 'DELETE'

# Join从句

## 1.内连接（INNER）

内连接Inner join基于连接谓词将两张表（如A和B）的列表组合在一起，产生新的结果表

```
SELECT <select_list>
FROM TableA A
INNER JOIN TableB B
ON A.Key = B.Key
```

```
SELECT a.'user_name',a.'over',b.'over'
FFROM user1 a
INNER JOIN user2 b
ON a.'user_name'=b.'user_name'
```

## 2.全外连接（FULL OUTER）

## 3.左外连接（LEFT OUTER）

```
SELECT <select_list>
FROM TableA A
LEFT JOIN TableB B
ON A.Key = B.Key
```

## 4.右外连接（RIGHT OUTER）

## 5.交叉连接（CROSS）


# MySQL命令

## 数据库

- 创建新数据库

 `create databse databasename;`

 - 删除数据库

 `DROP DATABASE databasename;`

 - 返回数据库的版本号

 `SELECT VERSION();`

- 显示数据库

`SHOW DATABASES;`

- 选择要操作的Mysql数据库

`use databesname;`

## 表

- 创建表

```
CREATE TABLE tablename
(
name varchar(30)
);
```

数据类型 | 描述 
:------:| :--:
<br>integer(size)<br>int(size)<br>smallint(size)<br>tinyint(size) | 仅容纳整数。在括号内规定数字的最大位数。
<br>decimal(size,d)<br>numeric(size,d) | <br>容纳带有小数的数字。<br>"size" 规定数字的最大位数。"d" 规定小数点右侧的最大位数。
char(size) | <br>容纳固定长度的字符串（可容纳字母、数字以及特殊字符）。<br>在括号中规定字符串的长度。
varchar(size) | <br>容纳可变长度的字符串（可容纳字母、数字以及特殊的字符）。<br>在括号中规定字符串的最大长度。
date(yyyymmdd) | 容纳日期。

- 显示指定数据库的所有表(使用该命令前需要使用 use 命令来选择要操作的数据库。)

`SHOW TABLES;`

- 显示数据表的属性，属性类型，主键信息 ，是否为 NULL，默认值等其他信息。

`SHOW COLUMNS FROM Tablename;` 

或 `desc Tablename;`

- 显示创建表的SQL语句

`SHOW CREATE TABLE students;`

- 删除表

`drop table tablename;`

- 显示表里的所有数据

`select * from tablename;`

## 服务器

 - 返回服务器的连接数

 `select connection_id();`

 # 如何用pymysql连接MySQL数据库

 ```
 # 导入pymysql库
 import pymysql

 # 打开数据库连接
db = pymysql.Connect(
    host='localhost',
    port=3306,
    user='root',
    passwd='158216dl',
    db='sakila',
    charset='utf8'
)

# 使用 cursor() 方法创建一个游标对象 cursor
cursor = db.cursor()

# 提交到数据库执行
db.commit()

# 执行数据库操作（需要研究）

# 关闭数据库连接
cursor.close()
db.close()
 ```



