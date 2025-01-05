### **Ques. IN and NOT IN Operator?**
* **IN Operator**
  * The IN operator is a shorthand for multiple OR conditions, It reduces the use of multiple OR conditions in SELECT, INSERT, UPDATE, and DELETE queries.
  * The IN operator is used to retrieves results when the specified value matches any value in a set of values or is returned by a subquery. 
  * This operator allows us to specify multiple values along with the WHERE clause. 
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
* **NOT IN Operator**
  * selects all customers that are located in "Texas", or "New York":
```sql
SELECT * FROM Customers WHERE city NOT IN ('Texas', 'New York');

Output:-
+----+----------+-----+-----------+-----------+
| cust_id | cust_name | city      | occupation|
+---------+-----------+-----------+-----------+
|  1      | Peter     | Londen    | Business  |
|  3      | Mark      | New Delhi | Engineer  |        
|  5      | Alexander | Maxico    | Student   |
+---------+-----------+-----------+-----------+

```

### **Ques. BETWEEN Operator?**
* The BETWEEN operator selects values within a given range. The values can be numbers, text, or dates.
* The BETWEEN operator is inclusive: begin and end values are included.
```sql
SELECT column_name(s) FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

* **NOT BETWEEN Example**
  * To display the products outside the range of the previous example, use NOT BETWEEN:
```sql
SELECT column_name(s) FROM table_name
WHERE column_name NOT BETWEEN value1 AND value2;
```


### Ques. What is difference between in and exists?

* **EXISTS Operator**
  * 