### Table of Contents

|  No.  | Questions                                                                                            |
| :---: | ---------------------------------------------------------------------------------------------------- |
|       | [What is database?](#ques-What-is-database)                                                          |
|       | [what is sql?](#ques-what-is-sql)                                                                    |
|       | [What Is DBMS?](#Ques-What-is-DBMS)                                                                  |
|       | [What Is RDBMS?](#what-is-rdbms)                                                                     |
|       | [Difference between DBMS & RDBMS?](#ques-difference-between-dbms--rdbms)                             |
|       | [Optimizing SQL Queries for Faster Performance](#ques-optimizing-sql-queries-for-faster-performance) |


**[⬆ Back to Top](#table-of-contents)**
### Ques. What is database?
* A database is an organized collection of data, stored and retrieved digitally from a remote or local computer system. Databases can be vast and complex, and such databases are developed using fixed design and modeling approaches.
* Database is nothing but an organized form of data for easy access, storing, retrieval and managing of data. 
* This is also known as structured form of data which can be accessed in many ways.
**[⬆ Back to Top](#table-of-contents)**

### Ques. What is Sql?
* SQL is stands for structure query language. 
* It is a database language used for database creation, deletion, fetching rows and modifying rows etc.
* It is a kind of ANSI standard language, used with all database. 

**[⬆ Back to Top](#table-of-contents)**
### Ques. What Is DBMS?
* A database management system is program that control creation, maintenance and use of a database.
* DBMS can be termed as File Manager that manages data in a database rather than saving it in ﬁle systems.

**[⬆ Back to Top](#table-of-contents)**
### What is RDBMS?
RDBMS stands for Relational Database Management System. RDBMS store the data into the collection of tables, which is related by common fields between the columns of the table. It also provides relational operators to manipulate the data stored into the tables.


**[⬆ Back to Top](#table-of-contents)**
### Ques. Difference between DBMS & RDBMS?
| DBMS                                          | RDBMS                                           |
| :-------------------------------------------- | :---------------------------------------------- |
| DBMS applications store data as file          | RDBMS applications store data in a tabular form |
| Normalization is not present in DBMS          | Normalization is present in RDBMS               |
| DBMS does not support distributed data hnbase | RDBMS support distributed database              |


### Ques. Difference between **CHAR** and **VARCHAR** data types?
* Both of these data types are used for characters.
* **CHAR data** type is used to store **fixed-length** character strings. When VARCHAR data type is used to store **variable-length** character strings.
* char occupies all the space and if space is remaining, then it fill all the blank space with "space". But in case of varchar, It takes only the required length & release remaining.
```sql
Char -> 10      | R | A | M | space | space | sapce | space | space | space | space |
Varchar -> 10   | R | A | M |   |   |   |   |   |   |   |
| R | A | M |
```
* varchar is better than Char in term of space. 
* char perform is better than varchar.
* Char max 256 characters, varchar 65535 characters.


### Ques. Optimizing SQL Queries for Faster Performance
1. Minimize the use of wildcard characters
   * The use of wildcard characters, such as % and _, in SQL queries, can slow down query performance. When using wildcard characters, the database has to scan the entire table to find the relevant data. To optimize SQL queries, it is important to minimize the use of wildcard characters and to use them only when absolutely necessary.
```sql
SELECT * FROM customers WHERE last_name_city LIKE 'P%';
```
* This query will use the index on the last name column and will be faster than the previous query.
```sql
SELECT * FROM customers WHERE last_name_city >= 'P' AND last_name < 'Q';
```

2. Increase Query Performance with Indexes
3. Use appropriate data types
4. Avoid subqueries
5. Avoid using SELECT *
```sql
SELECT * FROM customers WHERE customer_id = 1;
```
```sql
SELECT name, email FROM customers WHERE customer_id = 1;
```
6. Use stored procedures
7. 


### What is the difference between CHAR and VARCHAR?


### What is MySQL?Explain the differences between **SQL** and **MySQL**?In which language has MySQL been written?How to create a database in MySQL?.What is the MySQL server’s default port?  ->3306



