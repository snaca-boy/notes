# 创建数据库
```sql
CREATE DATABASE databaseName
ON PRIMARY
(
NAME = 'databaseName_data',
FILENAME = 'D:\SQL SERVER\databaseName_data.mdf',
SIZE = 3MB,
MAXSIZE = UNLIMITED,
FILEGROWTH = 1MB
),
FILEGROUP stu_gp   /*创建另一个文件组stu_gp, 并存放文件student_data2*/
(
NAME = 'databaseName_data2',
FILENAME = 'D:\SQL SERVER\databaseName_data2.ndf',
SIZE = 3MB,
MAXSIZE = 20MB,
FILEGROWTH = 1MB
)
LOG ON
(
NAME = 'databaseName_log',
FILENAME = 'D:\SQL SERVER\databaseName_log.ldf',
SIZE = 3MB,
MAXSIZE = 20MB,
FILEGROWTH = 1MB
)
```

# 修改数据库
- 添加数据文件
```sql
ALTER DATABASE databaseName
ADD FILE
(
NAME = 'databaseName_data3',
FILENAME = 'D:\SQL SERVER\databaseName_data3.ndf',
SIZE = 3MB,
MAXSIZE = 20MB,
FILEGROWTH = 1MB
)
```
- 添加日志文件
```sql
ALTER DATABASE databaseName
ADD LOG FILE
(
NAME = 'databaseName_log2',
FILENAME  = 'D:\SQL SERVER\databaseName_log2.ldf',
SIZE = 1MB,
MAXSIZE = 10MB,
FILEGROWTH = 10%
)
```
- 删除文件
```sql
ALTER DATABASE databaseName
REMOVE FILE databaseName_data3
```
- 修改文件属性
```sql
ALTER DATABASE databaseName
MODIFY FILE
(
NAME = 'databaseName_data',
FILENAME = 'D:\databaseName_data.mdf',
SIZE = 4MB,
MAXSIZE = 10MB,
FILEGROWTH = 2MB
)
```
- 重命名数据库
```sql
ALTER DATABASE databaseName
MODIFY NAME = newDatabaseName
```

# 删除数据库
```sql
DROP DATABASE databaseName
```
