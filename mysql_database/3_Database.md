|  No.  | Databse                                |
| :---: | -------------------------------------- |
|       | [Create Database?](#create-database)   |
|       | [Show Databases?](#show-databases)     |
|       | [SELECT Databases?](#select-database-) |
|       | [DROP Databases?](#drop-database-)     |

### Create Database
```sql
CREATE DATABASE employeesdb;
```

### Show Databases
```sql
show databases;
OR
SHOW SCHEMAS;

+---------------------+
| Database            |
+---------------------+
| employeesdb         |
| phpmyadmin          |
| profile_fastapi     |
| test                |
+---------------------+
```

### SELECT Database:-
```sql
USE database_name;  
```

### DROP Database:-
```SQL
DROP DATABASE database_name;
OR
DROP SCHEMA database_name;
```