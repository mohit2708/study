### Ques. What is difference between in and exists?
* **IN Operator**
  * The IN operator is used to retrieves results when the specified value matches any value in a set of values or is returned by a subquery. 
  * This operator allows us to specify multiple values along with the WHERE clause. 
  * It reduces the use of multiple OR conditions in SELECT, INSERT, UPDATE, and DELETE queries.
```sql
select * from customers
+----+----------+-----+-----------+-----------+
| cust_id | cust_name | city      | occupation|
+---------+-----------+-----------+-----------+
|  1      | Peter     | Londen    | Business  |
|  2      | Joseph    | Texas     | Doctor    |
|  3      | Mark      | New Delhi | Engineer  |        
|  4      | Michael   | New York  | Scientist |
|  5      | Alexander | Maxico    | Student   |
+---------+-----------+-----------+-----------+
mysql> SELECT * FROM customer WHERE occupation IN ('Doctor', 'Scientist', 'Engineer');

+----+----------+-----+-----------+-----------+
| cust_id | cust_name | city      | occupation|
+---------+-----------+-----------+-----------+
|  2      | Joseph    | Texas     | Doctor    |
|  3      | Mark      | New Delhi | Engineer  |        
|  4      | Michael   | New York  | Scientist |
+---------+-----------+-----------+-----------+
```
* **EXISTS Operator**
  * 