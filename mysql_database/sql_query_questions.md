### Table of Contents

|  No.  | Questions                                                                                                                                  |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------ |
|       | [How to add users in MySQL?](#ques-how-to-create-a-new-mysql-user-account-in-mysql)                                                        |
|       | [Check version of the sql?](#ques-check-version-of-the-sql)                                                                                |
|       | [Create database?](#create-database)                                                                                                       |
|       | [Rename database?](#rename-database)                                                                                                       |
|       | [Delete database?](#delete-database)                                                                                                       |
|       | [Table Create?](#create-table)                                                                                                             |
|       | [Drop Table?](#DROP-TABLE)                                                                                                                 |
|       | [Rename Table?](#RENAME-TABLE)                                                                                                             |
|       | [How to copy a table in another table?](#ques-how-to-copy-a-table-in-another-table)                                                        |
|       | [How to copy structure of a table but not data?](#ques-how-to-copy-structure-of-a-table-but-not-data)                                      |
|       | [Delete Table?](#DELETE-TABLE)                                                                                                             |
|       | [Delete Duplicate Records?](#delete-duplicate-records)                                                                                     |
|       | [Add foreign key?](#add-foreign-key)                                                                                                       |
|       | [Highest Salary Department wise?](#highest-salary-department-wise)                                                                         |
|       | [Highest Salary Department wise with name?](#ques-find-the-highest-salary-of-each-department-with-name)                                    |
|       | [How to find Nth highest salary from a table?](#ques-how-to-find-nth-highest-salary-from-a-table)                                          |
|       | [Replace a Column Values from 'male' to 'female' and 'female' to 'male'?](#replace-a-column-values-from-male-to-female-and-female-to-male) |



### Demo data for execute the query
```sql
CREATE TABLE employee (
    emp_id INT PRIMARY KEY,
    emp_name VARCHAR(50),
    job_name VARCHAR(50),
    manager_id INT,
    hire_date DATE,
    salary DECIMAL(10, 2),
    commission DECIMAL(10, 2),
    dep_id INT
);

INSERT INTO employee (emp_id, emp_name, job_name, manager_id, hire_date, salary, commission, dep_id)
VALUES
    (68319, 'KAYLING', 'PRESIDENT', NULL, '1991-11-18', 6000.00, NULL, 1001),
    (66928, 'BLAZE', 'MANAGER', 68319, '1991-05-01', 2750.00, NULL, 3001),
    (67832, 'CLARE', 'MANAGER', 68319, '1991-06-09', 2550.00, NULL, 1001),
    (65646, 'JONAS', 'MANAGER', 68319, '1991-04-02', 2957.00, NULL, 2001),
    (67858, 'SCARLET', 'ANALYST', 65646, '1997-04-19', 3100.00, NULL, 2001),
    (69062, 'FRANK', 'ANALYST', 65646, '1991-12-03', 3100.00, NULL, 2001),
    (63679, 'SANDRINE', 'CLERK', 69062, '1990-12-18', 900.00, NULL, 2001),
    (64989, 'ADELYN', 'SALESMAN', 66928, '1991-02-20', 1700.00, 400.00, 3001),
    (65271, 'WADE', 'SALESMAN', 66928, '1991-02-22', 1350.00, 600.00, 3001),
    (66564, 'MADDEN', 'SALESMAN', 66928, '1991-09-28', 1350.00, 1500.00, 3001),
    (68454, 'TUCKER', 'SALESMAN', 66928, '1991-09-08', 1600.00, 0.00, 3001),
    (68736, 'ADNRES', 'CLERK', 67858, '1997-05-23', 1200.00, NULL, 2001),
    (69000, 'JULIUS', 'CLERK', 66928, '1991-12-03', 1050.00, NULL, 3001),
    (69324, 'MARKER', 'CLERK', 67832, '1992-01-23', 1400.00, NULL, 1001);


+--------+----------+-----------+------------+------------+---------+------------+--------+
| emp_id | emp_name | job_name  | manager_id | hire_date  | salary  | commission | dep_id |
+--------+----------+-----------+------------+------------+---------+------------+--------+
|  63679 | SANDRINE | CLERK     |      69062 | 1990-12-18 |  900.00 |       NULL |   2001 |
|  64989 | ADELYN   | SALESMAN  |      66928 | 1991-02-20 | 1700.00 |     400.00 |   3001 |
|  65271 | WADE     | SALESMAN  |      66928 | 1991-02-22 | 1350.00 |     600.00 |   3001 |
|  65646 | JONAS    | MANAGER   |      68319 | 1991-04-02 | 2957.00 |       NULL |   2001 |
|  66564 | MADDEN   | SALESMAN  |      66928 | 1991-09-28 | 1350.00 |    1500.00 |   3001 |
|  66928 | BLAZE    | MANAGER   |      68319 | 1991-05-01 | 2750.00 |       NULL |   3001 |
|  67832 | CLARE    | MANAGER   |      68319 | 1991-06-09 | 2550.00 |       NULL |   1001 |
|  67858 | SCARLET  | ANALYST   |      65646 | 1997-04-19 | 3100.00 |       NULL |   2001 |
|  68319 | KAYLING  | PRESIDENT |       NULL | 1991-11-18 | 6000.00 |       NULL |   1001 |
|  68454 | TUCKER   | SALESMAN  |      66928 | 1991-09-08 | 1600.00 |       0.00 |   3001 |
|  68736 | ADNRES   | CLERK     |      67858 | 1997-05-23 | 1200.00 |       NULL |   2001 |
|  69000 | JULIUS   | CLERK     |      66928 | 1991-12-03 | 1050.00 |       NULL |   3001 |
|  69062 | FRANK    | ANALYST   |      65646 | 1991-12-03 | 3100.00 |       NULL |   2001 |
|  69324 | MARKER   | CLERK     |      67832 | 1992-01-23 | 1400.00 |       NULL |   1001 |
+--------+----------+-----------+------------+------------+---------+------------+--------+
```



### **Ques. How to create a new MySQL user account in MySQL?**
```sql
CREATE USER 'testuser' IDENTIFIED BY 'sample password';
```
* grant all **privileges** of the database for a newly created user
```sql
GRANT ALL PRIVILEGES ON * . * TO 'testuser'@'localhost';
```
* For changes to take effect immediately **flush** these privileges by typing in the command:
```sql
FLUSH PRIVILEGES;
```
* to **withdraw** all privileges for our non-root user we should use:
```sql
REVOKE ALL PRIVILEGES ON * . * FROM 'testuser'@'localhost';
```
* Also, replace the **PERMISSION_TYPE** value with the kind of access you want to grant to your new user account.
  * CREATE — enable users to create a database or table
  * SELECT — permit users to retrieve data
  * INSERT — let users add new entries in tables
  * UPDATE — allow users to modify existing entries in tables
  * DELETE — enable users to erase table entries
  * DROP — let users delete entire database tables
```sql
GRANT CREATE, SELECT ON * . * TO 'testuser'@'localhost';
```
* **Display** MySQL user **account privileges**
```sql
SHOW GRANTS FOR 'local_user'@'localhost';
```
* you can entirely **delete** an existing user account by using the following command:
```sql
DROP USER 'testuser'@'localhost';
```
* **Change** a MySQL user account **password**
```sql
ALTER USER 'testuser'@'localhost' IDENTIFIED BY 'new_password';
```

### **Ques. Check version of the sql?**
```sql
select version()
```

### **Create database**
```sql
create database <databse_name>
```

### **Rename database**
```sql
ALTER DATABASE old_datbase MODIFY = new_database
```

### **Delete database**
```sql
drop database database_name;
```


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
```sql
CREATE TABLE table_name
(
id int AUTO_INCREMENT primary key, 
column_name1 data_type(size),
column_name2 data_type(size),
column_name3 data_type(size),
..
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

### **Insert table**
```sql
INSERT INTO table_name
(column1,column2,column3,...)
VALUES
('value1','value2','value3',...);
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

### Ques. How to copy a table in another table?
```sql
CREATE TABLE EMP1 AS (SELECT * FROM EMP); //constraint will not copied.
```

### Ques. How to copy structure of a table but not data?
```sql
CREATE TABLE STD AS (SELECT * FROM EMP WHERE EMPNO=-1);
```



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


### Highest Salary Department wise
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
| 8  | Mohit | 90000  | 1            |
+----+-------+--------+--------------+
Department table:
+----+-------+
| id | name  |
+----+-------+
| 1  | IT    |
| 2  | Sales |
+----+-------+
```

#### **Ques. Find the Highest Salary of Each Department?**
```sql
# for single table
SELECT dep_id, max(salary) FROM `employee` GROUP BY dep_id;
+--------+-------------+
| dep_id | max(salary) |
+--------+-------------+
|   1001 |     6000.00 |
|   2001 |     3100.00 |
|   2244 |     6000.00 |
|   3001 |     2750.00 |
+--------+-------------+

# for two table
select max(employee.salary) AS salery, department.name from employee JOIN department WHERE employee.departmentId = department.id GROUP BY department.name;
+--------+-------+
| salery | name  |
+--------+-------+
| 90000  | IT    |
| 80000  | Sales |
+--------+-------+
```

#### **Ques. Find the Highest Salary of Each Department with name?**
```sql
# for one table
 SELECT dep_id, emp_name, salary FROM employee WHERE (dep_id,salary) IN (SELECT dep_id, MAX(salary) FROM employee GROUP BY dep_id);
+--------+----------+---------+
| dep_id | emp_name | salary  |
+--------+----------+---------+
|   2244 | Mohit    | 6000.00 |
|   3001 | BLAZE    | 2750.00 |
|   2001 | SCARLET  | 3100.00 |
|   1001 | KAYLING  | 6000.00 |
|   2001 | FRANK    | 3100.00 |
+--------+----------+---------+

# for two table
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


### Ques. How to find Nth highest salary from a table?
```sql
select emp_name, salary from employee order by Salary DESC;
+----------+---------+
| emp_name | salary  |
+----------+---------+
| KAYLING  | 6000.00 |
| SCARLET  | 3100.00 |
| FRANK    | 3100.00 |
| JONAS    | 2957.00 |
| BLAZE    | 2750.00 |
| CLARE    | 2550.00 |
| ADELYN   | 1700.00 |
| TUCKER   | 1600.00 |
| MARKER   | 1400.00 |
| MADDEN   | 1350.00 |
| WADE     | 1350.00 |
| ADNRES   | 1200.00 |
| JULIUS   | 1050.00 |
| SANDRINE |  900.00 |
+----------+---------+
```

#### Using the LIMIT Clause
* Syntex:-
```sql
Select Salary from table_name order by Salary DESC limit n-1,1;
```

* The limit clause has two components, the **First component** is to skip a number of rows from the top and the **second component** is to display the number of rows we want. 
* To find the **4th** Highest salary query will be

```sql
Select emp_name, salary from Employee order by salary DESC limit 3,1;
+----------+---------+
| emp_name | salary  |
+----------+---------+
| JONAS    | 2957.00 |
+----------+---------+

```
* using sub Query
```sql
# 3rd higest salery
SELECT MAX(salary) FROM Employee WHERE salary < (SELECT MAX(salary) FROM Employee WHERE salary < (SELECT MAX(salary) FROM Employee));
+-------------+
| MAX(salary) |
+-------------+
|     2957.00 |
+-------------+
```

### Ques. Top 5 Salery?
```sql
select emp_name, salary from employee order by Salary DESC;
+----------+---------+
| emp_name | salary  |
+----------+---------+
| KAYLING  | 6000.00 |
| SCARLET  | 3100.00 |
| FRANK    | 3100.00 |
| JONAS    | 2957.00 |
| BLAZE    | 2750.00 |
| CLARE    | 2550.00 |
| ADELYN   | 1700.00 |
| TUCKER   | 1600.00 |
| MARKER   | 1400.00 |
| MADDEN   | 1350.00 |
| WADE     | 1350.00 |
| ADNRES   | 1200.00 |
| JULIUS   | 1050.00 |
| SANDRINE |  900.00 |
+----------+---------+
```
* Using limit
```sql
SELECT salary FROM employee ORDER BY salary DESC LIMIT 4
+----------+---------+
| emp_name | salary  |
+----------+---------+
| KAYLING  | 6000.00 |
| FRANK    | 3100.00 |
| SCARLET  | 3100.00 |
| JONAS    | 2957.00 |
| BLAZE    | 2750.00 |
+----------+---------+
```
* Using sub Query
```sql

```


### **Ques. Top Salery?**
```sql
select emp_name, salary from employee order by Salary DESC;
+----------+---------+
| emp_name | salary  |
+----------+---------+
| Mohit    | 6000.00 |
| KAYLING  | 6000.00 |
| FRANK    | 3100.00 |
| SCARLET  | 3100.00 |
| JONAS    | 2957.00 |
| BLAZE    | 2750.00 |
| CLARE    | 2550.00 |
| ADELYN   | 1700.00 |
| TUCKER   | 1600.00 |
| MARKER   | 1400.00 |
| MADDEN   | 1350.00 |
| WADE     | 1350.00 |
| ADNRES   | 1200.00 |
| JULIUS   | 1050.00 |
| SANDRINE |  900.00 |
+----------+---------+
```
```sql
select emp_name, salary from employee where salary = (select max(salary) from employee);
+----------+---------+
| emp_name | salary  |
+----------+---------+
| Mohit    | 6000.00 |
| KAYLING  | 6000.00 |
+----------+---------+
```


### **How to Find Duplicate values in a Table?**
```sql
+----+---------+
| Id | Email   |
+----+---------+
| 1  | a@b.com |
| 2  | c@d.com |
| 3  | a@b.com |
+----+---------+

select Email, count(Email) as num from Person group by Email;
+---------+-----+
| Email   | num |
+ ------- + --- +
| a@b.com | 2   |
| c@d.com | 1   |
+---------+-----+

select Email, count(Email) as num from Person group by Email HAVING COUNT(Email) > 1;
+---------+-----+
| Email   | num |
+ ------- + --- +
| a@b.com | 2   |
+---
```

### **Replace a Column Values from 'male' to 'female' and 'female' to 'male'**
```sql
CREATE TABLE EMPDATA
(
EMPNAME VARCHAR(25),
GENDER VARCHAR(6),
DEPT VARCHAR(20),
CONTACTNO BIGINT NOT NULL,
CITY VARCHAR(15)
);

INSERT INTO EMPDATA
VALUES ('VISHAL','MALE','SALES',9193458625,'GHAZIABAD'),
('DIVYA','FEMALE','MANAGER',7352158944,'BAREILLY'),
('REKHA','FEMALE','IT',7830246946,'KOLKATA'),
('RAHUL','MALE','MARKETING',9635688441,'MEERUT'),
('SANJAY','MALE','SALES',9149335694,'MORADABAD'),
('ROHAN','MALE','MANAGER',7352158944,'BENGALURU'),
('RAJSHREE','FEMALE','SALES',9193458625,'VODODARA'),
('AMAN','MALE','IT',78359941265,'RAMPUR'),
('RAKESH','MALE','MARKETING',9645956441,'BOKARO'),
('MOHINI','FEMALE','SALES',9147844694,'Delhi')

select * from empdata;
+----------+--------+-----------+-------------+-----------+
| EMPNAME  | GENDER | DEPT      | CONTACTNO   | CITY      |
+----------+--------+-----------+-------------+-----------+
| VISHAL   | FEMALE | SALES     |  9193458625 | GHAZIABAD |
| DIVYA    | MALE   | MANAGER   |  7352158944 | BAREILLY  |
| REKHA    | MALE   | IT        |  7830246946 | KOLKATA   |
| RAHUL    | FEMALE | MARKETING |  9635688441 | MEERUT    |
| SANJAY   | FEMALE | SALES     |  9149335694 | MORADABAD |
| ROHAN    | FEMALE | MANAGER   |  7352158944 | BENGALURU |
| RAJSHREE | MALE   | SALES     |  9193458625 | VODODARA  |
| AMAN     | FEMALE | IT        | 78359941265 | RAMPUR    |
| RAKESH   | FEMALE | MARKETING |  9645956441 | BOKARO    |
| MOHINI   | MALE   | SALES     |  9147844694 | Delhi     |
+----------+--------+-----------+-------------+-----------+
```
```sql
UPDATE empdata
SET GENDER = CASE
    WHEN GENDER='male' THEN 'female'
    WHEN GENDER='female' THEN 'male'
    END;

OR
             
UPDATE EMPDATA 
SET gender = CASE 
    gender WHEN 'male' THEN 'female' 
            WHEN 'female' THEN 'male'
    ELSE gender
END;


+----------+--------+-----------+-------------+-----------+
| EMPNAME  | GENDER | DEPT      | CONTACTNO   | CITY      |
+----------+--------+-----------+-------------+-----------+
| VISHAL   | male   | SALES     |  9193458625 | GHAZIABAD |
| DIVYA    | female | MANAGER   |  7352158944 | BAREILLY  |
| REKHA    | female | IT        |  7830246946 | KOLKATA   |
| RAHUL    | male   | MARKETING |  9635688441 | MEERUT    |
| SANJAY   | male   | SALES     |  9149335694 | MORADABAD |
| ROHAN    | male   | MANAGER   |  7352158944 | BENGALURU |
| RAJSHREE | female | SALES     |  9193458625 | VODODARA  |
| AMAN     | male   | IT        | 78359941265 | RAMPUR    |
| RAKESH   | male   | MARKETING |  9645956441 | BOKARO    |
| MOHINI   | female | SALES     |  9147844694 | Delhi     |
+----------+--------+-----------+-------------+-----------+
```