### Create Table
* SQL CREATE TABLE statement is used to create table in a database.
```sql
SQL> CREATE TABLE STUDENTS(
id INT NOT NULL,  
first_name VARCHAR (20) NOT NULL,
age INT NOT NULL,  
address CHAR (25),  
PRIMARY KEY (id)  
);  
```
* Create table with **primary key**
```sql
CREATE TABLE Employee(  
EmployeeID NOT NULL,  
FirstName varchar(255) NOT NULL,  
LastName varchar(255),  
City varchar(255),  
PRIMARY KEY (EmployeeID)  
); 
```

### DROP TABLE?
* A SQL DROP TABLE statement is used to delete a table definition and all data from a table.
```sql
DROP TABLE "table_name";
```

### DELETE TABLE?
* The DELETE statement is used to delete rows from a table. If you want to remove a specific row from a table you should use WHERE condition.
```sql
DELETE FROM table_name [WHERE condition];  
```
* But if you do not specify the WHERE condition it will remove all the rows from the table.
```sql
DELETE FROM table_name;
```

### Delete Duplicate Records?
```sql
CREATE TABLE employee (
    id INT,
    customer_name VARCHAR(255),
    email VARCHAR(255)
);
INSERT INTO employee (id, customer_name, email)
VALUES
    (1, 'John Doe', 'john.doe@example.com'),
    (2, 'Jane Doe', 'jane.doe@example.com'),
    (3, 'Muzamil Amin', 'Muzamilaminitoo@gmail.com'),
    (1, 'John Doe', 'john.doe@example.com'), 
    (4, 'Alice Johnson', 'alice.johnson@example.com'),
    (2, 'Jane Doe', 'jane.doe@example.com');

mysql> DELETE FROM employee WHERE id IN ( SELECT id FROM employee GROUP BY id HAVING COUNT(*) > 1 )
```