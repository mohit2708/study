### Table of Contents

|  No.  | Questions                                                          |
| :---: | ------------------------------------------------------------------ |
|       | [Table Create?](#create-table)                                     |
|       | [Drop Table?](#DROP-TABLE)                                         |
|       | [Rename Table?](#RENAME-TABLE)                                     |
|       | [Copy Table?](#COPY-TABLE)                                         |
|       | [Delete Table?](#DELETE-TABLE)                                     |
|       | [Delete Duplicate Records?](#delete-duplicate-records)             |
|       | [Add foreign key?](#add-foreign-key)                               |
|       | [Highest Salary Department wise?](#highest-salary-department-wise) |



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

### RENAME TABLE?
* We want to change the name of the table in the SQL database.
```sql
RENAME old_table _name To new_table_name;
OR
ALTER TABLE old_table_name RENAME TO new_table_name;
```

### **Copy Table?**
* if we want to copy the data of one SQL table into another SQL table in the same SQL server.



### DELETE TABLE?
* The DELETE statement is used to delete rows from a table. If you want to remove a **specific row** from a table you should use WHERE condition.
```sql
DELETE FROM table_name [WHERE condition];  
```
* But if you do not specify the WHERE condition it will remove **all the rows** from the table.
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





### Add foreign key?
```sql
ALTER TABLE `bookings` ADD CONSTRAINT `advance_bookings_user_id_foreign` FOREIGN KEY (`user_id`) REFERENCES `users` (`id`) ON DELETE CASCADE ON UPDATE CASCADE
```


## Highest Salary Department wise
```sql
Create table If Not Exists Employee (id int, name varchar(255), salary int, departmentId int);
Create table If Not Exists Department (id int, name varchar(255));
Truncate table Employee;
insert into Employee (id, name, salary, departmentId) values ('1', 'Joe', '85000', '1');
insert into Employee (id, name, salary, departmentId) values ('2', 'Henry', '80000', '2');
insert into Employee (id, name, salary, departmentId) values ('3', 'Sam', '60000', '2');
insert into Employee (id, name, salary, departmentId) values ('4', 'Max', '90000', '1');
insert into Employee (id, name, salary, departmentId) values ('5', 'Janet', '69000', '1');
insert into Employee (id, name, salary, departmentId) values ('6', 'Randy', '85000', '1');
insert into Employee (id, name, salary, departmentId) values ('7', 'Will', '70000', '1');
insert into Employee (id, name, salary, departmentId) values ('8', 'Mohit', '90000', '1');
Truncate table Department;
insert into Department (id, name) values ('1', 'IT');
insert into Department (id, name) values ('2', 'Sales');
```
```sql
Employee table:
+----+-------+--------+--------------+
| id | name  | salary | departmentId |
+----+-------+--------+--------------+
| 1  | Joe   | 85000  | 1            |
| 2  | Henry | 80000  | 2            |
| 3  | Sam   | 60000  | 2            |
| 4  | Max   | 90000  | 1            |
| 5  | Janet | 69000  | 1            |
| 6  | Randy | 85000  | 1            |
| 7  | Will  | 70000  | 1            |
+----+-------+--------+--------------+
Department table:
+----+-------+
| id | name  |
+----+-------+
| 1  | IT    |
| 2  | Sales |
+----+-------+
```

### **Ques. Find the Highest Salary of Each Department?**
```sql
select max(employee.salary) AS salery, department.name from employee JOIN department WHERE employee.departmentId = department.id GROUP BY department.name;
+--------+-------+
| salery | name  |
+--------+-------+
| 90000  | IT    |
| 80000  | Sales |
+--------+-------+
```

* Show the highest salary with name
```sql
SELECT department.name AS dep_name, employee.name AS emp_name, employee.salary AS salary 
FROM employee JOIN department 
ON employee.departmentId = department.id
JOIN(
SELECT departmentId, max(salary) AS max_salary 
from employee GROUP BY departmentId
) AS dept_max ON employee.departmentId = dept_max.departmentId AND employee.salary = dept_max.max_salary

+----------+----------+--------+
| dep_name | emp_name | salary |
+----------+----------+--------+
| Sales    | Henry    | 80000  |
| IT       | Max      | 90000  |
| IT       | Mohit    | 90000  |
+----------+----------+--------+

* Using SubQuery
SELECT department.name AS dep_name, employee.name AS emp_name, employee.salary AS salary
FROM employee 
JOIN department ON employee.departmentId = department.id
WHERE (employee.departmentId, employee.salary) IN (
    SELECT departmentId, MAX(salary) 
    FROM employee 
    GROUP BY departmentId
);

+----------+----------+--------+
| dep_name | emp_name | salary |
+----------+----------+--------+
| Sales    | Henry    | 80000  |
| IT       | Max      | 90000  |
| IT       | Mohit    | 90000  |
+----------+----------+--------+
```


### How to find Nth highest salary from a table?
```sql
CREATE TABLE employee (
    emp_name TEXT NOT NULL,
    salary INT NOT NULL
);
INSERT INTO employee VALUES ('Tom',1500000);
INSERT INTO employee VALUES ('Dick',3900000);
INSERT INTO employee VALUES ('Hary',7700000);
INSERT INTO employee VALUES ('Mike',15000000);
INSERT INTO employee VALUES ('Harvey',33300000);
INSERT INTO employee VALUES ('Brush',2500000);
```
#### Using the LIMIT Clause
* Syntex:-
```sql
Select Salary from table_name order by Salary DESC limit n-1,1;
```

* The limit clause has two components, the **First component** is to skip a number of rows from the top and the **second component** is to display the number of rows we want. 
* To find the **4th** Highest salary query will be

```sql
SELECT name, salary FROM `employee` ORDER BY salary DESC
+--------+----------+
| name   | salary   |
+--------+----------+
| Harvey | 33300000 |
| Mike   | 15000000 |
| Hary   | 7700000  |
| Dick   | 3900000  |
| Brush  | 2500000  |
| Tom    | 1500000  |
+----------+--------+






Select emp_sal from Emp order by emp_sal DESC limit 3,1;



```