### Ques. What Is Joins?
* A JOIN is a method used to combine rows from two or more tables based on a related column between them.
* MySQL JOINS are used with SELECT statement.

#### Many types of MySQL joins:
1. Self Join
2. Inner Join
3. Left JOIN
4. Right JOIN
5. Full Join
6. Outer Join
7. Cross Join 


### Self Join
* A self join connects a table to itself. Used when you want to compare rows within the same table.
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

-- Example
SELECT c1.NAME AS Customer1, c2.NAME AS Customer2, c1.SALARY FROM Customers c1
JOIN Customers c2 ON c1.SALARY = c2.SALARY AND c1.ID < c2.ID;
-- Output:
+------------+------------+----------+
| Customer1  | Customer2  | SALARY   |
+------------+------------+----------+
| Ramesh     | kaushik    | 2000.00  |
+------------+------------+----------+
```

### INNER JOIN:-
* The MySQL Inner Join is used to returns only those results from the tables that **match** the specified condition and hides other rows and columns.
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

### Left JOIN:-
* The LEFT JOIN keyword returns all records from the left table (table1), and the matching records (if any) from the right table (table2).
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

SQL> SELECT  ID, NAME, AMOUNT, DATE FROM CUSTOMERS LEFT JOIN ORDERS
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

### Right JOIN:-
* The RIGHT JOIN keyword returns all records from the right table (table2), and the matching records (if any) from the left table (table1).
```sql
-- Customers Table
+----+----------+
| ID | NAME     |
+----+----------+
|  1 | Ramesh   |
|  2 | Khilan   |
|  3 | Kaushik  |

-- Orders Table
+----------+------------+
| OrderID  | CustomerID |
+----------+------------+
|   101    |     2      |
|   102    |     3      |
|   103    |     4      |
+----------+------------+

-- RIGHT JOIN Result
SELECT Customers.NAME, Orders.OrderID FROM Customers RIGHT JOIN Orders 
ON Customers.ID = Orders.CustomerID;
+----------+------------+
| NAME     | OrderID    |
+----------+------------+
| Khilan   |   101      |
| Kaushik  |   102      |
| NULL     |   103      |
+----------+------------+

```

### Outer join
* Returns all rows from both tables, Matching and non-matching rows.
* NULL values where no match exists
```sql
SELECT column_list
FROM table1
FULL OUTER JOIN table2 ON table1.column = table2.column;
```

```sql
# Example query
employees:

| employee_id | employee_name | department_id |
| ----------- | ------------- | ------------- |
| 1           | John Smith    | 101           |
| 2           | Mary Johnson  | 102           |
| 3           | Sam Brown     | 103           |

departments:

| department_id | department_name |
| ------------- | --------------- |
| 101           | HR              |
| 102           | Finance         |
| 104           | Marketing       |

SELECT employees.employee_id, employees.employee_name, departments.department_name
FROM employees
FULL OUTER JOIN departments ON employees.department_id = departments.department_id;

| employee_id | employee_name | department_name |
| ----------- | ------------- | --------------- |
| 1           | John Smith    | HR              |
| 2           | Mary Johnson  | Finance         |
| 3           | Sam Brown     | NULL            |
| NULL        | NULL          | Marketing       |
```

#### When you would use it
1. **Merging data**: When you need to combine data from two tables into a single result set while preserving all records.
2. **Handling missing data**: In scenarios where data might be missing or incomplete in one or both tables.
3. **Comparing data**: For data analysis, auditing, or quality control to compare and identify differences between two data sources.
4. **Reporting exceptions**: To identify and report data discrepancies or anomalies across tables.









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