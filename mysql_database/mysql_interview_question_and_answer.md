### Table of Contents

|  No.  | Questions                                                                                           |
| :---: | --------------------------------------------------------------------------------------------------- |
|       | [What is database?](#ques-What-is-database)                                                         |
|       | [what is sql?](#ques-What-is-Sql)                                                                   |
|       | [What Is DBMS?](#Ques-What-is-DBMS)                                                                 |
|       | [What Is RDBMS?](#Ques-What-is-RDBMS)                                                               |
|       | [What Is RDBMS?](#Ques-What-is-RDBMS)                                                               |
|       | [Difference between DBMS & RDBMS?](#Ques-Difference-between-DBMS-&-RDBMS)                           |
|       | [What Is Primary Key?](#ques-What-Is-primary-Key)                                                   |
|       | [What Is Unique Key?](#ques-What-Is-Unique-Key)                                                     |
|       | [What Is Foreign Key?](#ques-What-Is-Foreign Key)                                                   |
|       | [Difference between Primary Key & Unique Key?](#ques-Difference-between-Primary-Key-&-Unique-Key)   |
|       | [Difference between Primary Key & Foreign Key?](#ques-Difference-between-Primary-Key-&-Foreign-Key) |
|       | [Difference between Delete, Truncate & Drop?](#ques-Difference-between-Delete,-Truncate-&-Drop)     |
|       | [What Is Joins?](#ques-What-Is-Joins)                                                               |
|       | [Types of Joins?](#ques-Types-of-Joins)                                                             |
|       | [What Is Union & Union All?### What is View](#ques-What-Is-Union-&-Union-All)                       |
|       | [What is View?](#ques-What-is-View)                                                                 |
|       | [What is Index?](#ques-What-is-index)                                                               |
|       |


**[⬆ Back to Top](#table-of-contents)**
### **Ques. What is database?**
* A database is an organized collection of data, stored and retrieved digitally from a remote or local computer system. Databases can be vast and complex, and such databases are developed using fixed design and modeling approaches.
* Database is nothing but an organized form of data for easy access, storing, retrieval and managing of data. 
* This is also known as structured form of data which can be accessed in many ways.
**[⬆ Back to Top](#table-of-contents)**

### **Ques. What is Sql?**
* SQL is stands for structure query language. 
* It is a database language used for database creation, deletion, fetching rows and modifying rows etc.
* It is a kind of ANSI standard language, used with all database. 

**[⬆ Back to Top](#table-of-contents)**
### **Ques. What Is DBMS?**
* A database management system is program that control creation, maintenance and use of a database.
* DBMS can be termed as File Manager that manages data in a database rather than saving it in ﬁle systems.

**[⬆ Back to Top](#table-of-contents)**
### **What is RDBMS?**
RDBMS stands for Relational Database Management System. RDBMS store the data into the collection of tables, which is related by common fields between the columns of the table. It also provides relational operators to manipulate the data stored into the tables.


**[⬆ Back to Top](#table-of-contents)**
### **Ques. Difference between DBMS & RDBMS?**
| DBMS                                          | RDBMS                                           |
| :-------------------------------------------- | :---------------------------------------------- |
| DBMS applications store data as file          | RDBMS applications store data in a tabular form |
| Normalization is not present in DBMS          | Normalization is present in RDBMS               |
| DBMS does not support distributed data hnbase | RDBMS support distributed database              |

**[⬆ Back to Top](#table-of-contents)**
### **Ques. What are Constraints in SQL?**
Constraints are used to specify the rules concerning data in the table. It can be applied for single or multiple fields in an SQL table during the creation of the table or after creating using the ALTER TABLE command. The constraints are:<br>
* __NOT NULL__ - Restricts NULL value from being inserted into a column.
* __CHECK__ - Verifies that all values in a field satisfy a condition.
* __DEFAULT__ - Automatically assigns a default value if no value has been specified for the field.
* __UNIQUE__ - Ensures unique values to be inserted into the field.
* __INDEX__ - Indexes a field providing faster retrieval of records.
* __PRIMARY KEY__ - Uniquely identifies each record in a table.
* __FOREIGN KEY__ - Ensures referential integrity for a record in another table.




**[⬆ Back to Top](#table-of-contents)**
### Ques. **What Is Joins?**
* MySQL JOINS are used with SELECT statement.
* It is used to retrieve data from multiple tables. It is performed whenever you need to fetch records from two or more tables.

#### Many types of MySQL joins:
* **INNER JOIN:-**  The MySQL Inner Join is used to returns only those results from the tables that **match** the specified condition and hides other rows and columns.
```sql
Customers table:                                      
+----+----------+-----+-----------+----------+        
| ID | NAME     | AGE | ADDRESS   | SALARY   |        
+----+----------+-----+-----------+----------+        
|  1 | Ramesh   |  32 | Ahmedabad |  2000.00 |        
|  2 | Khilan   |  25 | Delhi     |  1500.00 |        
|  3 | kaushik  |  23 | Kota      |  2000.00 |        
|  4 | Chaitali |  25 | Mumbai    |  6500.00 |        
|  5 | Hardik   |  27 | Bhopal    |  8500.00 |   
|  6 | Komal    |  22 | MP        |  4500.00 |
|  7 | Muffy    |  24 | Indore    | 10000.00 |
+----+----------+-----+-----------+----------+
Order table:
+-----+---------------------+-------------+--------+
|OID  | DATE                | CUSTOMER_ID | AMOUNT |
+-----+---------------------+-------------+--------+
| 101 | 2009-11-20 00:00:00 |           2 |   1560 |
| 103 | 2008-05-20 00:00:00 |           4 |   2060 |
+-----+---------------------+-------------+--------+

SELECT customers.name, customers.age, customers.salary, order.date FROM customers INNER JOIN order ON customers.id = order.CUSTOMER_ID;
+----------+-----+---------+---------------------+
| NAME     | AGE | SALARY  |   DATE              | 
+----------+-----+---------+---------------------+
| Khilan   |  25 | 1500.00 | 2009-11-20 00:00:00 |        
| Chaitali |  25 | 6500.00 | 2008-05-20 00:00:00 |     
+----------+-----+---------+---------------------+
```

* **Left JOIN:-** The LEFT JOIN keyword returns all records from the left table (table1), and the matching records (if any) from the right table (table2).
```sql
CUSTOMERS Table
+----+----------+-----+-----------+----------+ 
| ID | NAME     | AGE | ADDRESS   | SALARY   |
+----+----------+-----+-----------+----------+
|  1 | Ramesh   |  32 | Ahmedabad |  2000.00 |
|  2 | Khilan   |  25 | Delhi     |  1500.00 |
|  3 | kaushik  |  23 | Kota      |  2000.00 |
|  4 | Chaitali |  25 | Mumbai    |  6500.00 |
|  5 | Hardik   |  27 | Bhopal    |  8500.00 |
|  6 | Komal    |  22 | MP        |  4500.00 |
|  7 | Muffy    |  24 | Indore    | 10000.00 |
+----+----------+-----+-----------+----------+

Orders Table
+-----+---------------------+-------------+--------+
| OID | DATE                | CUSTOMER_ID | AMOUNT |
+-----+---------------------+-------------+--------+
| 102 | 2009-10-08 00:00:00 |           3 |   3000 |
| 100 | 2009-10-08 00:00:00 |           3 |   1500 |
| 101 | 2009-11-20 00:00:00 |           2 |   1560 |
| 103 | 2008-05-20 00:00:00 |           4 |   2060 |
+-----+---------------------+-------------+--------+

SQL> SELECT  ID, NAME, AMOUNT, DATEFROM CUSTOMERS LEFT JOIN ORDERS
   ON CUSTOMERS.ID = ORDERS.CUSTOMER_ID;

Result:-
+----+----------+--------+---------------------+
| ID | NAME     | AMOUNT | DATE                |
+----+----------+--------+---------------------+
|  1 | Ramesh   |   NULL | NULL                |
|  2 | Khilan   |   1560 | 2009-11-20 00:00:00 |
|  3 | kaushik  |   3000 | 2009-10-08 00:00:00 |
|  3 | kaushik  |   1500 | 2009-10-08 00:00:00 |
|  4 | Chaitali |   2060 | 2008-05-20 00:00:00 |
|  5 | Hardik   |   NULL | NULL                |
|  6 | Komal    |   NULL | NULL                |
|  7 | Muffy    |   NULL | NULL                |
+----+----------+--------+---------------------+
```

* **Right JOIN:-** The RIGHT JOIN keyword returns all records from the right table (table2), and the matching records (if any) from the left table (table1).
```sql
+-------+----+                  +-------+----+  
| ID    |NAME|                  | ID    |NAME|
+-------+----+
|  1001 | A  |
|  1002 | B  |
|  1003 | C  |
|  1004 | D  |
+-------+----+

```


```sql
Customers table:                                      
+----+----------+-----+-----------+----------+        
| ID | NAME     | AGE | ADDRESS   | SALARY   |        
+----+----------+-----+-----------+----------+        
|  1 | Ramesh   |  32 | Ahmedabad |  2000.00 |        
|  2 | Khilan   |  25 | Delhi     |  1500.00 |        
|  3 | kaushik  |  23 | Kota      |  2000.00 |        
|  4 | Chaitali |  25 | Mumbai    |  6500.00 |        
|  5 | Hardik   |  27 | Bhopal    |  8500.00 |   
|  6 | Komal    |  22 | MP        |  4500.00 |
|  7 | Muffy    |  24 | Indore    | 10000.00 |
+----+----------+-----+-----------+----------+
Order table:
+-----+---------------------+-------------+--------+
|OID  | DATE                | CUSTOMER_ID | AMOUNT |
+-----+---------------------+-------------+--------+
| 102 | 2009-10-08 00:00:00 |           3 |   3000 |
| 100 | 2009-10-08 00:00:00 |           3 |   1500 |
| 101 | 2009-11-20 00:00:00 |           2 |   1560 |
| 103 | 2008-05-20 00:00:00 |           4 |   2060 |
+-----+---------------------+-------------+--------+
```
Now, let us join these two tables in our SELECT statement as follows:
```sql
SQL> SELECT  ID, NAME, AMOUNT, DATE
   FROM CUSTOMERS
   INNER JOIN ORDERS
   ON CUSTOMERS.ID = ORDERS.CUSTOMER_ID;
```
Result:
```sql
+----+----------+-----+--------+
| ID | NAME     | AGE | AMOUNT |
+----+----------+-----+--------+
|  3 | kaushik  |  23 |   3000 |
|  3 | kaushik  |  23 |   1500 |
|  2 | Khilan   |  25 |   1560 |
|  4 | Chaitali |  25 |   2060 |
+----+----------+-----+--------+
```



### **Ques. Types of Joins?**

```sql
SQL> SELECT  ID, NAME, AMOUNT, DATE
   FROM CUSTOMERS
   LEFT JOIN ORDERS
   ON CUSTOMERS.ID = ORDERS.CUSTOMER_ID;
   WHERE orders.AMOUNT IS NOT NULL

Result:-
+----+----------+--------+---------------------+
| ID | NAME     | AMOUNT | DATE                |
+----+----------+--------+---------------------+
|  1 | Ramesh   |   NULL | NULL                |
|  2 | Khilan   |   1560 | 2009-11-20 00:00:00 |
|  3 | kaushik  |   3000 | 2009-10-08 00:00:00 |
|  3 | kaushik  |   1500 | 2009-10-08 00:00:00 |
|  4 | Chaitali |   2060 | 2008-05-20 00:00:00 |
+----+----------+--------+---------------------+
```
* Inner join: Inner join return rows when there is at least one match of rows between the tables.
* Right Join: Right join return rows which are common between the tables and all rows of Right hand side table. Simply, it returns all the rows from the right hand side table even though there are no matches in the left hand side table.
* Full join: return rows when there are matching rows in any one of the tables.
* Self Join:- It is used to join one single table with itself as there were two different tables.
  
* Cross join:- 
  * The CROSS JOIN keyword returns all records from both tables (table1 and table2).
  * This join method compares every single row of a table with every single row of the other table.
```sql
SQL> SELECT  ID, NAME, AMOUNT, DATE
   FROM CUSTOMERS
   CROSS JOIN ORDERS
   ON CUSTOMERS.ID = ORDERS.CUSTOMER_ID;
   
Result:-
+----+----------+--------+---------------------+
| ID | NAME     | AMOUNT | DATE                |
+----+----------+--------+---------------------+
|  1 | Ramesh   |   NULL | NULL                |
|  2 | Khilan   |   1560 | 2009-11-20 00:00:00 |
|  3 | kaushik  |   3000 | 2009-10-08 00:00:00 |
|  3 | kaushik  |   1500 | 2009-10-08 00:00:00 |
|  4 | Chaitali |   2060 | 2008-05-20 00:00:00 |
+----+----------+--------+---------------------+
```




3. **Intersect:-** 
* The intersect opertor returns the common records from two or more select statements.
* These are the records that exist in both Dataset1 and Dataset2.
```sql
SELECT column1, column2 FROM table1
INTERSECT
SELECT column1, column2 FROM table2
```
4. **Minus:-** 
* MINUS operator will return only those rows which are unique in only first SELECT query and not those rows which are common to both first and second SELECT queries.
```sql
SELECT column1 , column2 , ... columnN FROM table_name
MINUS
SELECT column1 , column2 , ... columnN FROM table_name
```




**[⬆ Back to Top](#table-of-contents)**
### **What is Index?**
* An index is used to enhance the performance of SQL Queries.
* It will get the data using Row Id, avoid full table scan.
* A database index is a data structure that improves the speed of operation in a table.
* index can be created one or more columns.
* Index allows the database application to find data fast, without reading the whole table.
* An index can be created in a table to find data more quickly and efficiently.
```sql
CREATE INDEX KAKA 
    ON EMP(EMPNO) 
    SELECT * FROM EMP WHERE EMPNO=7788 (FAST ACCESS)
```
**Types of index**
1. **cluster index:-** jab kisi table par hum primary key lagate hai to wo cluster index ban jata hai.
2. **Non cluster index:-** table mai jis column par select command sabse jyda chalte hai to us column par hum non cluster index bna lete hai.


### **Ques. What is the difference between cluster and non cluster index?**
* A clustered index reorders the way records in the table are physically stored. There can be only one clustered index per table. It makes data retrieval faster.
* A non clustered index does not alter the way it was stored but creates a completely separate object within the table. As a result insert and update command will be faster.


**[⬆ Back to Top](#table-of-contents)**
### **What is Cursor?**
* WHEN WE USE SELECT STMT IN DATABASE(ORACLE/SQLSERVER/MYSQL) ,   it allocate memory for that known as cursor.
* A cursor is a pointer to this context area. PL/SQL controls the context area through a Cursor.
* A Cursor can hold more than one row, but can process only one row at a time. The set of rows the cursor hold is called the active set.
* A cursor is a temporary work area created in the system memory when a SQL statement is executed. A cursor contains information on a select statement and the rows of data accessed by it.
* This temporary work area is used to store the data retrieved from the database and manipulate this data.

#### There are two type of cursor in PL/SQL:-

1. **Implicit cursor:-**
   * These are creating by default when DML statement like, INSERT, UPDATE, and DELETE statement are executed. They are also created when a SELECT statement that returns just one row is executed.
   * Implicit cursors are automatically created by oracle whenever an SQL statement is executed, when there is no explicit cursor for the statement. Programmers cannot control the implicit cursor and the information in it.

**[⬆ Back to Top](#table-of-contents)**
### **What is Trigger?**
* • Trigger  are set of structure Query language (SQL) statement that perform particular task. They invoke specific event (after Insert,u,d – before I,u,d)
* Database triggers are sets of commands that get executed when an event (Before Insert, After Insert, On Update, on delete of a row) occurs on a table.
* Triggers are special type of stored procedures that are defined to execute automatically in place or after data modification.
* Trigger allows you to execute a batch of SQL code an insert, update or delete command is execute against a specific table.
```sql
CREATE OR REPLACE TRIGGERRESTRICT_EMP
BEFORE INSERT ON EMP
BEGIN
RAISE_APPLICATION_ERROR(-20987,’INSERT MAT KAR NAHI HOGA’);
END;
```

### Difference between WHERE and HAVING in SQL?
| Having                                                           | Where                                                                      |
| :--------------------------------------------------------------- | :------------------------------------------------------------------------- |
| Having ke sath GROUP BY use hota hai                             |                                                                            |
| Having post filter hai(data fatch hone ke baad filter lagta hai) | where pre filter hai(isme pahle filter lagta hai phir fatch data hota hai) |
| having can be used only with select command                      | can be used with select update delete                                      |
| HAVING is used for column operations.                            | WHERE is used for row operations                                           |
| having ke aggrigate function sath kar sakte hai                  | where ke sath aggrigate function use nahi kar sakte                        |
```sql
a   c1  40
a   c2  50
b   c3  30
c   c1  20

select std, sum(score) as total from record group by std having total>60;
```

### **Ques. Difference between In and Between Operator in SQL?**
* BETWEEN operator is used to select a range of data between two values while The IN operator allows you to specify multiple values.
* The BETWEEN operator selects a range of data between two values. The values can be numbers, text,etc.
* The IN operator allows you to specify multiple values.
```sql
+----+----------+--------+
| ID | NAME     | mark   |
+----+----------+--------+
|  1 | Ramesh   |   89   |
|  2 | Khilan   |   81   |
|  3 | kaushik  |   73   |
|  3 | kaushik  |   67   |
|  4 | Chaitali |   52   |
+----+----------+--------+

# between
SELECT * FROM emp WHERE marks BETWEEN 50 AND 80
+----+----------+--------+
| ID | NAME     | mark   |
+----+----------+--------+
|  3 | kaushik  |   73   |
|  3 | kaushik  |   67   |
|  4 | Chaitali |   52   |
+----+----------+--------+

# In
SELECT * FROM emp WHERE marks IN (89,73)
+----+----------+--------+
| ID | NAME     | mark   |
+----+----------+--------+
|  1 | Ramesh   |   89   |
|  3 | kaushik  |   73   |
+----+----------+--------+
```



### **List of Mysql storage Engines/Table Type?**
Mysql ne apni requirment ke according alag-alag table type diye hai.
1. MyIsam:-
* Myisam good for select command.
* it support full text searching.
* it support table level locking.
* it support Blob and text column can be indexed.
2. Innodb
* it support for referential integrity.
* it support foreign key constraint.
* it support Row level locking.
* it support for transaction. 
3. CSV
* The CSV storage engine stores data in text file using comma separated values format.
4. Archive
5. memory 
6. black hole
7. merge
8. federated


### **Ques. What is Stored procedure?**
* Stored procedure is a function which cantains a collection of sql quries, the procedure can take inputs, process them and send back output.
* Stored procedure is a database object which is used to perform some specific task.
* Stored procedure is called explicitly.
* Store procedures is set of structure Query language (SQL) statement that perform particular task.
* Store procedures is set of structure Query language (SQL) statement with an assigned name, which are stored in a relation database 
management system as a group, so it can be reused and shered by multipal program.
* Advantage: Stored Procedures are precompiled and stored in the database. This enables the Database to execute the queries much faster. Since many queries can be included in a stored procedure, round trip time to execute multiple queries from source code to
Database and back is avoided.
* A procedure is a group of SQL statement that you can call by name.
* Store procedures is a database object which is used to perform some specific task.

__Advantage__
* Store procedure is reducing the complexity of code in code behind.
* Store procedures have repeatedly having data. It helps to reuse the code.
* It store in precompiled format so execution of speed is much faster than SQL statement.

```
1. Store procedures explicitly call hote hai.
2. Tiger automatic call hote hai.
3. Function inside the sql call hote hai.
```

```sql
create procedure procedure_name as
begain
  select name, age from emp;
end

execute procedure_name
```

```sql
CREATE OR REPLACE PROCEDURE ABCD
IS 
BEGIN
DBMS_OUTPUT.PUT_LINE('JAI PL BABA');
END;
sql>EXECUTE ABCD (sql>set serveroutput on)
```
```sql
ALTER procedure [dbo].[inemp]
@eno int,@enm varchar(20),@sl int
as
begin
insert into emp(EMPNO,ENAME,SAL) values(@eno,@enm,@sl);
end
```

### **Ques. What is the normalization?**
* In database design, we start with one single table, with all possible columns. A lot of redundant data would be present since it’s a single table. The process of removing the redundant data, by splitting up the table in a well deﬁned fashion is called
normalization.
* Normalization is the process of minimizing redundancy and dependency by organizing fields and table of a database. The main aim of Normalization is to add, delete or modify field that can be made in a single table.
* A lot of redundant data would be present since it’s a single table. The process of removing the redundant data, by splitting up the table in a well defined fashion is called normalization.

### **Ques. What are types of normalization?**
1. **First Normal Form (1NF):-** A relation is said to be in ﬁrst normal form if and only if all underlying domains contain atomic values only. After 1NF, we can still have redundant data.
2. **Second Normal Form (2NF):-** A relation is said to be in 2NF if and only if it is in 1NF and every non key attribute is fully dependent on the primary key. After 2NF, we can still have redundant data.
3. **Third Normal Form (3NF):-** A relation is said to be in 3NF, if and only if it is in 2NF and every non key attribute is non-transitively dependent on the primary key.

```
**Types of normalization:**
A. First normal form (1NF): This should remove all the duplicate columns from the table.
Creation of tables for the related data and identification of unique columns.
B. Second normal form (2NF): Meeting all requirements of the first normal form. Placing the
subsets of data in separate tables and Creation of relationships between the tables using
primary keys
C. Third normal form (3NF): This should meet all requirements of 2NF. Removing the columns
0which are not dependent on primary key constraints.
D. Fourth normal form (4NF): Meeting all the requirements of third normal form and it should
not have multi- valued dependencies.
```

### **Ques. What is Json?**
* Json stands for Javascript Object Notation and Json is lightweight data interchange format.
* Json is syntax for storing and exchanging data.
* it is easy for machine to parse and recreates.
* Json is often used when data is sent from a server to a web page.

__JSON Advantage__
* JSON does not have namespace.
* JSON is not extensible.




```sql
CREATE TABLE mohit
       (EMPNO numaric(4) CONSTRAINT pk_emp PRIMARY KEY,
        ENAME VARCHAR(10),
        JOB VARCHAR(9),
        MGR numaric(4),
        HIREDATE DATE,
        SAL numaric(7, 2),
        COMM numaric(7, 2),
        DEPTNO numaric(2) CONSTRAINT fk_emp_dept REFERENCES dept(deptno))
select * from saxena
INSERT INTO saxena VALUES
        (7369, 'SMITH',  'CLERK', 7902,'17-DEC-1980',  800, NULL, 20);
INSERT INTO saxena VALUES
        (7499, 'ALLEN',  'SALESMAN',  7698,'20-FEB-1981',1600,  300, 30);
INSERT INTO saxena VALUES
        (7521, 'WARD',   'SALESMAN',  7698,'22-FEB-1981', 1250,  500, 30);
INSERT INTO saxena VALUES
        (7566, 'JONES',  'MANAGER',   7839,'2-APR-1981', 2975, NULL, 20);
INSERT INTO saxena VALUES
        (7654, 'MARTIN', 'SALESMAN',  7698,'28-SEP-1981', 1250, 1400, 30);
INSERT INTO saxena VALUES
        (7698, 'BLAKE',  'MANAGER',   7839,'1-MAY-1981',  2850, NULL, 30);
INSERT INTO saxena VALUES
        (7782, 'CLARK',  'MANAGER',   7839,'9-JUN-1981', 2450, NULL, 10);
INSERT INTO saxena VALUES
        (7788, 'SCOTT',  'ANALYST',   7566,'09-DEC-1982', 3000, NULL, 20);
INSERT INTO saxena VALUES
        (7839, 'KING',   'PRESIDENT', NULL,'17-NOV-1981', 5000, NULL, 10);
INSERT INTO saxena VALUES
        (7844, 'TURNER', 'SALESMAN',  7698,'8-SEP-1981',  1500,    0, 30);
INSERT INTO saxena VALUES
        (7876, 'ADAMS',  'CLERK',     7788, '12-JAN-1983', 1100, NULL, 20);
INSERT INTO saxena VALUES
        (7900, 'JAMES',  'CLERK',     7698, '3-DEC-1981',   950, NULL, 30);
INSERT INTO saxena VALUES
        (7902, 'FORD',   'ANALYST',   7566, '3-DEC-1981',   3000, NULL, 20);
INSERT INTO saxena VALUES
        (7934, 'MILLER', 'CLERK',7782,'23-JAN-1982', 1300, NULL, 40);
```



# **Sql Query:-**
### **Check version of the sql?**
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

### **Create table**
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

### **Insert table**
```sql
INSERT INTO table_name
(column1,column2,column3,...)
VALUES
('value1','value2','value3',...);
```

### Ques. How to copy a table in another table?
```sql
CREATE TABLE EMP1 AS (SELECT * FROM EMP); //constraint will not copied.
```
### Ques. How to copy structure of a table but not data?
```sql
CREATE TABLE STD AS (SELECT * FROM EMP WHERE EMPNO=-1);
```

### 2nd/3rd/nth highest salary?
* using limit
```sql
select * from emp order by salery desc limit n-1, 1(no of records);
```
* using sub Query
```sql
# 3rd higest salery
SELECT MAX (SAL) FROM EMP WHERE SAL < (SELECT MAX (SAL) FROM EMP WHERE SAL < (SELECT MAX (SAL) FROM EMP))
```



#### 2nd highest salary?
* __Using Subquery:-__
```sql
SELECT salary FROM (SELECT salary FROM employees ORDER BY salary DESC LIMIT 2) AS Emp ORDER BY salary LIMIT 1;
```
* Using Limit:-
```sql
SELECT MAX(salary) FROM employees WHERE salary NOT IN ( SELECT Max(salary) FROM employees); (OR)
SELECT MAX (SAL) FROM EMP WHERE SAL < (SELECT MAX (SAL) FROM EMP);
```

```sql
Using Sub query and < operator instead of IN clause:-
SELECT MAX(salary)
From employees
WHERE salary < ( SELECT Max(salary) FROM employees);
```

#### Ques. Department wise highest Salary?
```sql
+--------+---------+
| deptno | sal     |
+--------+---------+
|  10    | 5000    |
|  30    | 4000    |
|  10    | 2000    |
|  20    | 2000    |
|  20    | 3000    |
|  20    | 1000    |
+--------+---------+

Ans:- 
SELECT Deptno, MAX(Sal) FROM EmpDetails GROUP BY Deptno;
+--------+---------+
| deptno | sal     |
+--------+---------+
|  10    | 5000    |
|  30    | 4000    |
|  20    | 3000    |
+--------+---------+
```


### **Ques. Top Salery?**
```sql
select * from emp where sal = (select max(salery) from emp);
```

### **Ques. Top 5 Salery?**
* Mysql
```sql
SELECT salary  FROM emp ORDER BY salary DESC LIMIT 4
```
* sql
```sql
```
* Oracle
```sql
```

### **Ques. is a blank space or zero the same as a null value in sql?**
No 

### **Current date?**
```sql
select GETDATE();
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
+---------+-----+
```


### **What is Json?**
* Json stands for Javascript Object Notation and Json is lightweight data interchange format.
* Json is syntax for storing and exchanging data.
* it is easy for machine to parse and recreates.
* Json is often used when data is sent from a server to a web page.




MySql Interview Questions



Ques. Difference between inner & self & cross ?
Ans. 
Inner:-
Self:-
Cross:-



Ques. Find Names of students whose age is greater than 21 ?
Ans. Select [student_name] from [student_tbl] where [student_age] < 21


SQL Queries:-
-------?
Oracle
SQL
Top 5 Salary
SELECT SAL FROM(SELECT DISTINCT SAL FROM EMP WHERE SAL IS NOT NULL  ORDER BY SAL DESC)WHERE ROWNUM <6;
select top 5 sal from saxena order by sal desc;
select * from emp order by salery desc limit 5;


Delete table
Delete table_name; (only table data del)drop table persons;
drop table persons;



Insert data in another table

Add column
ALTER TABLE table_name
ADD column_name datatype(size), column_name datatype(size));
ALTER TABLE table_name
ADD column_name datatype



Data insert/update in a column
update emp set city='noida' where lastname='saxena'
update emp set city='noida' where lastname='saxena'

Rename Datatype
ALTER TABLE LALU MODIFY (MOBILE NUMBER(15));







### **Ques. What are the subsets of SQL?**
* Data definition language(DDL)
  * Create
  * Alter
  * Drop
  * Rename
  * Truncate
* Data manipulation language(DML)
  * Insert
  * Update
  * Delete
* Data control language(DCL)
  * Grant: It gives a privilege to user.
  * Revoke: It takes back privileges granted from user.



### **Ques. What is Denormalization?**
DeNormalization is a technique used to access the data from higher to lower normal
forms of database. It is also process of introducing redundancy into a table by
incorporating data from the related tables.




13. What are set operators in SQL?


### **Ques. What is ACID property?**
### **Ques. What is SQL TRANSACTIONS**
* Transactions group a set of tasks into a single execution unit. Each transaction begins with a specific job and ends when all the tasks in the group successfully completed. If any of the tasks fail, the transaction fails. Therefore, a transaction has only two results: success or failure.
* Example of a transaction to transfer $150 from account A to account B:
```php
1. read(A)
2. A:= A – 150
3. write(A)
4. read(B)
5. B:= B + 150
6. write(B)
```
* ACID property is used to ensure that the data transactions are processed reliably in a database system.
* A single logical operation of a data is called transaction.
* ACID is an acronym for Atomicity, Consistency, Isolation, and Durability. 

* **Atomicity: -** 
  * It requires that each transaction is all or nothing. It means if one part of the transaction fails, the entire transaction fails and the database state is left unchanged.
  * A transaction consists of many steps. When all the steps in a transaction get completed, it will get reflected in DB or if any step fails, all the transactions are rolled back.
__Consistency:__
* The consistency property ensures that the data must meet all validation rules. In simple words you can say that your transaction never leaves your database without completing its state.
* The database will move from one consistent state to another, if the transaction succeeds and remain in the original state, if the transaction fails.
Isolation:
 This property ensures that the concurrent property of execution should not be met. The
main goal of providing isolation is concurrency control.
 Every transaction should operate as if it is the only transaction in the system.
Durability:
 Durability simply means that once a transaction has been committed, it will remain so,
come what may even power loss, crashes or errors.
 Once a transaction has completed successfully, the updated rows/records must be
available for all other transactions on a permanent basis

1.  What are types of locks?
2. Sheared lock: When a shared lock is applied on data item, other transactions can only read the
item, but can&#39;t write into it.
1. Exclusive lock: When an exclusive lock is applied on data item, other transactions can&#39;t read or
write into the data item.
1.  How to delete duplicate record from a table?
SQL&gt;DELETE FROM EMP WHERE ROWID NOT IN (SELECT MAX (ROWID) FROM EMP GROUP BY
ROLL)