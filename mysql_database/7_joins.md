## Ques. **What Is Joins?**
* It is used to retrieve data from multiple tables. It is performed whenever you need to fetch records from two or more tables.
* MySQL JOINS are used with SELECT statement.

#### Many types of MySQL joins:
### **INNER JOIN:-**  
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

### **Left JOIN:-** 
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

### **Right JOIN:-** The RIGHT JOIN keyword returns all records from the right table (table2), and the matching records (if any) from the left table (table1).
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