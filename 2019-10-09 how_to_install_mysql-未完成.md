TITLE:如何安装和使用MySQL

*本文主要涉及Python和MySQl的内容*

市场的数据库林林种种，有关系数据库，比如本文中提及的MySQL，Oracle、SQL Server。
有NoSQL（Not Only SQL）的，比如mongodb,redis,hbase。

# MySQL命令

- 显示数据库

`SHOW DATABASES;`

- 选择要操作的Mysql数据库

`use databesname;`

- 显示指定数据库的所有表(使用该命令前需要使用 use 命令来选择要操作的数据库。)

`SHOW TABLES;`

- 显示数据表的属性，属性类型，主键信息 ，是否为 NULL，默认值等其他信息。

`SHOW COLUMNS FROM Tablename`

- 创建新数据库

 `create databse databasename`

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

# 执行数据库操作（需要研究）

# 关闭数据库连接
cursor.close()
db.close()
 ```



