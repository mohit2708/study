|  No.  | Questions                                                                                         |
| :---: | ------------------------------------------------------------------------------------------------- |
|       | [Primary Key?](#primary-key)                                                                      |
|       | [Add primary Key?](#add-primary-key)                                                              |
|       | [Delete primary Key?](#delete-primary-key)                                                        |
|       | [Foreign Key?](#foreign-key)                                                                      |
|       | [Foreign Key ALTER?](#defining-foreign-key-using-alter)                                           |
|       | [DROP Foreign Key?](#drop-a-foreign-key-from-the-table)                                           |
|       | [Unique Key?](#unique-key)                                                                        |
|       | [ALTER unique key?](#alter-unique-key)                                                            |
|       | [Drop unique key?](#drop-unique-key)                                                              |
|       | [Composite Key?](#composite-key)                                                                  |
|       | [Difference between Primary Key & Unique Key?](#ques-difference-between-primary-key--foreign-key) |
|       | [Difference between Primary Key & Foreign Key?](#ques-difference-between-primary-key--unique-key) |



## Primary Key?
### **Ques. What Is Primary Key?**
* The PRIMARY KEY constraint uniquely identifies each record in a database table. It must contain unique values. 
* A Primary Key column cannot have Null values.
* A table can have only one primary key, which may consist of single or multiple fields. When multiple fields are used as a primary key, they are called a composite key.
* **Create Primary Key:-**
```sql
CREATE table Employee ( 
 Employee_ID INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
 Employee_Name VARCHAR(30) NOT NULL,
 Employee_License INT NOT NULL,
 Employee_Department VARCHAR(15) NOT NULL DEFAULT 0
);

# OR
CREATE table Employee (
 Employee_ID INT NOT NULL AUTO_INCREMENT,
 Employee_Name VARCHAR(30) NOT NULL,
 Employee_License INT NOT NULL,
 Employee_Department VARCHAR(15) NOT NULL DEFAULT 0,
 PRIMARY KEY (Employee_ID) 
);

# For multiple column
CREATE table Employee (
 Employee_ID INT NOT NULL AUTO_INCREMENT,
 Employee_Name VARCHAR(30) NOT NULL,
 Employee_License INT NOT NULL,
 Employee_Department VARCHAR(15) NOT NULL DEFAULT 0,
 PRIMARY KEY (Employee_ID ,Employee_License)
 );
```

### **Add primary Key**
* if primary key doesn’t exists in the created table
```sql
ALTER TABLE table_name ADD PRIMARY KEY (Id)
```
* For multiple column
```sql
ALTER table Employee ADD constraints PK_Employee PRIMARY KEY (column name1, column name 2);
```

### **Delete primary Key**
```sql
ALTER TABLE CUSTOMERS DROP PRIMARY KEY;
```
* For multiple column
```sql
ALTER TABLE Employee DROP CONSTRAINT PK_Employee;
```

**[⬆ Back to Top](#table-of-contents)**

## Foreign Key?
### **Ques. What Is Foreign Key?**
* A foreign key is a key used to link two tables together. This is something called a reference key.
* Foreign key is a column or a combination of columns whose values match a primary key in a different table.
* The relationship between two tables matches the primary key in one of the tables with a foreign key in the second table.

  * We have two tables that are Employee and Department table. 
```sql
CREATE TABLE Department( department_id INT PRIMARY KEY, department_name VARCHAR(25));
```
```sql
CREATE table Employee (
 Employee_ID INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
 department_id INT,
 Employee_Name VARCHAR(30) NOT NULL,
 Employee_License INT NOT NULL,
 Employee_Department VARCHAR(15) NOT NULL DEFAULT 0,
 FOREIGN KEY(department_id) REFERENCES Department(department_id)
 );

# Here department_id is the foreign key in the employee table while it is primary key in the department table.
```

* To allow naming of a Foreign Key constraint, and for defining a Foreign Key on multiple columns,
```sql
CREATE table Employee (
 Employee_ID INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
 department_id INT,
 Employee_Name VARCHAR(30) NOT NULL,
 Employee_License INT NOT NULL,
 Employee_Department VARCHAR(15) NOT NULL DEFAULT 0,
 CONSTRAINT FK_dept_id FOREIGN KEY(department_id) REFERENCES Department(department_id)
);
```

### Defining Foreign Key using ALTER?
* if primary key doesn’t exists in the created table
```sql
ALTER TABLE Employee ADD FOREIGN KEY (department_id) REFERENCES Department(department_id);
```
* For multiple column
```sql
ALTER TABLE Employee 
ADD CONSTRAINT FK_dept_id FOREIGN KEY (department_id) REFERENCES Department(department_id);
```

### DROP a Foreign Key from the table
* For single column
```sql
ALTER TABLE Employee DROP FOREIGN KEY FK_dept_id;
```
* For multiple column
```sql
ALTER TABLE Employee DROP CONSTRAINT FK_dept_id;
```





## Unique Key?
### **Ques. What Is Unique Key?**
* A unique key is a set of one or more than one fields/columns of a table that uniquely identify each record in a database table.
* The Unique and Primary Key constraints both provide a guarantee for a column or set of columns.
* A Primary Key consist automatically has a unique constraint define on it.
  * Defining unique key
```sql
CREATE table Employee (
 Employee_ID INT NOT NULL UNIQUE,
 Employee_Name VARCHAR(30) NOT NULL,
 Employee_License INT NOT NULL,
 Employee_Department VARCHAR(15) NOT NULL DEFAULT 0
);
```
* If you wish to define more than one Unique Key within a table you can use the following syntax:
```sql
CREATE TABLE <table_name>
(
Column_name1 datatype(),
Column_name2 datatype(),…
Column_namen datatype(),
UNIQUE (column_name1, column_name2)
);
```

### ALTER unique key
```sql
ALTER table Employee ADD UNIQUE(column name);
``` 

### Drop unique key
```sql
ALTER TABLE Employee DROP CONSTRAINT Employee_ID ;
```

## Composite Key?
### **Ques. What is Composite Key?**
* Composite key is combination of two or more columns that can uniquely identify each row in the table.
* composite key is also a primary key, but the difference is that it is made by the combination of more than one column to identify the particular row in the table.
* A composite key cannot be null.
```sql
CREATE TABLE student
(rollNumber INT, 
name VARCHAR(30), 
class VARCHAR(30), 
section VARCHAR(1), 
mobile VARCHAR(10),
PRIMARY KEY (rollNumber, mobile));
```

**[⬆ Back to Top](#table-of-contents)**

## **Ques. Difference between Primary Key & Unique Key?**
| Primary Key                                            | Unique Key                                                           |
| :----------------------------------------------------- | :------------------------------------------------------------------- |
| A table can have only one primary key                  | A table can have more than one unique key                            |
| It does not allow null values                          | Allows null values                                                   |
| Primary key Can be made foreign key into another table | In SQL server, unique key Can be made foreign key into another table |
| By default it adds a clustered index                   | By default it adds a unique non-clustered index                      |
| Primary key support auto increment value.              | Unique constraint does not support auto increment value.             |



**[⬆ Back to Top](#table-of-contents)**

## **Ques. Difference between Primary Key & Foreign Key?**
| Primary Key                                            | Foreign Key                                                              |
| :----------------------------------------------------- | :----------------------------------------------------------------------- |
| A table can have only one primary key                  | A table can have more than one foreign key                               |
| Primary key uniquely identified  a record in the table | Foreign key is a field in the table that is primary key in another table |
| It does not allow null values                          | Allows null values                                                       |
| Duplicate not allowed                                  | Duplicate allowed                                                        |
| Primary key support auto increment value               | Foreign key do not automatically create an index.                        |