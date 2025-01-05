|  No.  | [Database](#database)                  |
| :---: | -------------------------------------- |
|       | [Show Database](#show-database)        |
|       | [Create Databse](#create-databse)      |
|       | [Rename Database](#rename-database)    |
|       | [Drop/Delete Database](#drop-database) |
|       | [Select Database](#select-database)    |


### Show Database
```sql
SHOW DATABASES;
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

### Create Databse
```sql
CREATE DATABASE databasename;
```

### Rename Database
```sql
RENAME DATABASE old_database_name TO new_database_name
(OR)
ALTER DATABASE old_datbase MODIFY = new_database
```

### Drop Database
```sql
DROP DATABASE databasename;
OR
DROP SCHEMA database_name;
```

### Select Database
```sql
USE YourDatabaseName;
```