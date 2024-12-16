
|  No.  | Tables                                                                                           |
| :---: | ------------------------------------------------------------------------------------------------ |
|       | [Types of SQL Commands/subsets of SQL?](#types-of-sql-commandssubsets-of-sql)                    |
|       | [Create TABLE?](#create-table)                                                                   |
|       | [ALTER Table?](#alter-table)                                                                     |
|       | [Change Datatype from alter cmd?](#change-datatype-from-alter-cmd)                               |
|       | [DROP column in table?](#drop-column-in-table)                                                   |
|       | [TRUNCATE table?](#truncate)                                                                     |
|       | [RENAME column in table?](#rename-column-in-table)                                               |
|       | [RENAME table name?](#rename-table-name)                                                         |
|       | [What is delete?](#delete)                                                                       |
|       | [Difference between Delete, Truncate & Drop?](#ques-difference-between-delete-truncate--drop)    |
|       | [Difference b/w DROP and TRUNCATE statements?](#ques-difference-bw-drop-and-truncate-statements) |


### Back to Top

### Types of SQL Commands/subsets of SQL?
* DDL (Data Definition Language):
  * **[CREATE:](#create-table)** Creates a new table or database.
  * **[ALTER](#alter-table):** Modifies an existing database object.
  * **[DROP](#drop-column-in-table):** Deletes an entire table, database, or other objects.
  * **[TRUNCATE](#truncate):** Removes all records from a table, deleting the space allocated for the records.

* DML (Data Manipulation Language):
  * **SELECT:** Retrieves data from the database.
  * **INSERT:** Adds new data to a table.
  * **UPDATE:** Modifies existing data within a table.
  * **DELETE:** Removes data from a table.
* DCL (Data Control Language):
  * **GRANT:** Gives users access privileges to the database.
  * **REVOKE:** Removes access privileges given with the GRANT command.
* TCL (Transaction Control Language):
  * **COMMIT:** Saves all changes made in the current transaction.
  * **ROLLBACK:** Restores the database to the last committed state.
  * **SAVEPOINT:** Sets a savepoint within a transaction.
  * **SET TRANSACTION:** Places a name on a transaction.

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

[↑ Back to top](#back-to-top)

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
* Add enum column
```sql
ALTER TABLE table_name ADD field_name enum('0','1') NOT NULL DEFAULT '0' after password;
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

### Truncate
* A truncate SQL statement is used to remove all rows (complete data) from a table.
* TRUNCATE is a DDL(Data Definition Language) command and is used to delete all the rows or tuples from a table. Unlike the DELETE command, the TRUNCATE command does not contain a WHERE clause.
```sql
TRUNCATE TABLE table_name;
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

### **Delete**
* DELETE is a DML(Data Manipulation Language) command and is used when we specify the row (tuple) that we want to remove or delete from the table or relation. The DELETE command can contain a WHERE clause.
```sql
delete from table_name where ID=01;
delete from table_name where ID IN(2,6);
```



### **Ques. Difference between Delete, Truncate & Drop?**
| Delete                                                | Truncate                                                       | Drop                  |
| :---------------------------------------------------- | :------------------------------------------------------------- | :-------------------- |
| Delete is a DML command                               | Truncate is DDL command                                        |                       |
| We can use where clause in delete command             | We cannot use where clause with truncate                       |                       |
| Delete statement is used to delete a row from a table | Truncate statement is used to remove all the row from a table  | Remove table and data |
| You can rollback data after using delete statement    | It is not possible to rollback after using TRUNCATE statement. | Can’t rollback        |
| Delete is slower                                      | Truncate is faster                                             |                       |


### **Ques. Difference b/w DROP and TRUNCATE statements?**
* **Drop Table:-**
  * Table structure will be dropped
  * Relationship will be dropped
  * Integrity constraints will be dropped
  * Access privileges will also be dropped
* **TRUNCATE Table:-**
  * On the other hand when we TRUNCATE a table, the table structure remains the same, so you will not face any of the above problems.