
|  No.  | Tables                                                             |
| :---: | ------------------------------------------------------------------ |
|       | [Create TABLE?](#create-table)                                     |
|       | [ALTER Table?](#alter-table)                                       |
|       | [Change Datatype from alter cmd?](#change-datatype-from-alter-cmd) |
|       | [DROP column in table?](#drop-column-in-table)                     |
|       | [RENAME column in table?](#rename-column-in-table)                 |
|       | [RENAME table name?](#rename-table-name)                           |
|       | [TRUNCATE table?](#truncate-table)                                 |


### CREATE TABLE
```sql
use database_name;
```
```sql
CREATE TABLE employee_table(  
    id int NOT NULL AUTO_INCREMENT,  
    name varchar(45) NOT NULL,  
    occupation varchar(35) NOT NULL,  
    age int NOT NULL,  
    PRIMARY KEY (id)  
);  
```
```sql
# show tables
+-----------------------+
| Tables_in_employee123 |
+-----------------------+
| employee_table        |
+-----------------------+
```

#### See the table structure:-
```sql
DESCRIBE employee_table;
+------------+-------------+------+-----+---------+----------------+
| Field      | Type        | Null | Key | Default | Extra          |
+------------+-------------+------+-----+---------+----------------+
| id         | int(11)     | NO   | PRI | NULL    | auto_increment |
| name       | varchar(45) | NO   |     | NULL    |                |
| occupation | varchar(35) | NO   |     | NULL    |                |
| age        | int(11)     | NO   |     | NULL    |                |
+------------+-------------+------+-----+---------+----------------+
```

### ALTER Table
```sql
# syntex
ALTER TABLE table_name  
ADD new_column_name column_definition  
[ FIRST | AFTER column_name ];  
```

* ADD a column in the table
```sql
ALTER TABLE employee_table ADD cus_age varchar(40) NOT NULL;  

DESCRIBE employee_table;
+------------+-------------+------+-----+---------+----------------+
| Field      | Type        | Null | Key | Default | Extra          |
+------------+-------------+------+-----+---------+----------------+
| id         | int(11)     | NO   | PRI | NULL    | auto_increment |
| name       | varchar(45) | NO   |     | NULL    |                |
| occupation | varchar(35) | NO   |     | NULL    |                |
| age        | int(11)     | NO   |     | NULL    |                |
| cus_age    | varchar(40) | NO   |     | NULL    |                |
+------------+-------------+------+-----+---------+----------------+
```

* Add column after occupation
```sql
ALTER TABLE employee_table ADD after_occupation varchar(40) NOT NULL AFTER occupation;

+------------------+-------------+------+-----+---------+----------------+
| Field            | Type        | Null | Key | Default | Extra          |
+------------------+-------------+------+-----+---------+----------------+
| id               | int(11)     | NO   | PRI | NULL    | auto_increment |
| name             | varchar(45) | NO   |     | NULL    |                |
| occupation       | varchar(35) | NO   |     | NULL    |                |
| after_occupation | varchar(40) | NO   |     | NULL    |                |
| age              | int(11)     | NO   |     | NULL    |                |
| cus_age          | varchar(40) | NO   |     | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+
```

* Add column first occupation
```sql
ALTER TABLE employee_table ADD COLUMN unique_id INT(11) NOT NULL FIRST;

+------------------+-------------+------+-----+---------+----------------+
| Field            | Type        | Null | Key | Default | Extra          |
+------------------+-------------+------+-----+---------+----------------+
| unique_id        | int(11)     | NO   |     | NULL    |                |
| id               | int(11)     | NO   | PRI | NULL    | auto_increment |
| name             | varchar(45) | NO   |     | NULL    |                |
| occupation       | varchar(35) | NO   |     | NULL    |                |
| after_occupation | varchar(40) | NO   |     | NULL    |                |
| age              | int(11)     | NO   |     | NULL    |                |
| cus_age          | varchar(40) | NO   |     | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+
```
* Add multiple columns in the table
```sql
ALTER TABLE employee_table 
    ADD COLUMN unique_id1 INT(11) NOT NULL FIRST,
    ADD COLUMN unique_id2 INT(11) NOT NULL FIRST;

+------------------+-------------+------+-----+---------+----------------+
| Field            | Type        | Null | Key | Default | Extra          |
+------------------+-------------+------+-----+---------+----------------+
| unique_id2       | int(11)     | NO   |     | NULL    |                |
| unique_id1       | int(11)     | NO   |     | NULL    |                |
| unique_id        | int(11)     | NO   |     | NULL    |                |
| id               | int(11)     | NO   | PRI | NULL    | auto_increment |
| name             | varchar(45) | NO   |     | NULL    |                |
| occupation       | varchar(35) | NO   |     | NULL    |                |
| after_occupation | varchar(40) | NO   |     | NULL    |                |
| age              | int(11)     | NO   |     | NULL    |                |
| cus_age          | varchar(40) | NO   |     | NULL    |                |
+------------------+-------------+------+-----+---------+----------------+
```


### Change Datatype from alter cmd
```sql
ALTER TABLE employee_table MODIFY unique_id4 VARCHAR(40) NULL;
OR
ALTER TABLE employee_table MODIFY COLUMN unique_id4 VARCHAR(40) NULL;
```

### DROP column in table
```sql
ALTER TABLE employee_table DROP COLUMN unique_id4;
```

### RENAME column in table
* syntex
```sql
ALTER TABLE table_name  
CHANGE COLUMN old_name new_name   
column_definition  
[ FIRST | AFTER column_name ] 
```
```sql
ALTER TABLE employee_table CHANGE COLUMN name first_name varchar(20) NOT NULL;
```

### RENAME table name
```sql
ALTER TABLE employee_table RENAME TO emp_table;
OR
RENAME table emp_tables TO employee_tables;
```