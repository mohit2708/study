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

* Add column before occupation
```sql

```