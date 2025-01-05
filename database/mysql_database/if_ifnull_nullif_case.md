### IF()
```sql
SELECT IF(200>350,'YES','NO');  

Output:- NO
```
```sql
SELECT IF(251 = 251,' Correct','Wrong');  

Output:- Correct
```
* If **both** the **string** is the **same**, it returns Correct. Otherwise, the IF function returns Wrong output.
```sql
SELECT IF(STRCMP('Rinky Ponting','Yuvraj Singh')=0, 'Correct', 'Wrong');
```

```sql
SELECT salary, IF(salary>3000,"Mature","Immature") As Result FROM employee;

+---------+----------+
| salary  | Result   |
+---------+----------+
| 1700.00 | Immature |
| 2550.00 | Immature |
| 2750.00 | Immature |
| 2957.00 | Immature |
| 3100.00 | Mature   |
| 3100.00 | Mature   |
| 6000.00 | Mature   |
| 6000.00 | Mature   |
+---------+----------+
```

### IFNULL()
* If the first expression is not NULL, it will return the first expression, which is 'Hello' value.
```sql
SELECT IFNULL("Hello", "javaTpoint");  

Output:- Hello
```
```sql
SELECT IFNULL(NULL,5);  

Output:- 5
```

```sql
+-----------+-----------+-----------+
| emp_name  | cellphone | homephone |
+-----------+-----------+-----------+
| mohit     | 2531452   |  NULL     |
| Krishna   | NULL      | 345634634 |
| shivani   | 551113    | NULL      |
| akshra    | NULL      | 6574576   |
| abhinav   | NULL      | 674576457 |
+-----------+-----------+-----------+

SELECT emp_name, IFNULL(cellphone, homephone) phone  
FROM  student_contact;

+-----------+-----------+
| emp_name  | phone     |
+-----------+-----------+
| mohit     | 2531452   |
| Krishna   | 345634634 |
| shivani   | 551113    |
| akshra    | 6574576   |
| abhinav   | 674576457 |
+-----------+-----------+
```

### NULLIF()
* The NULLIF function accepts two expressions, and if the first expression is equal to the second expression, it returns the NULL. Otherwise, it returns the first expression.
```sql
SELECT NULLIF("javaTpoint", "javaTpoint");  

Output:- NULL
```
```sql
SELECT NULLIF("Hello", "404");  

Output:- Hello
```
```sql
CREATE TABLE customer (
  customer_id INT UNSIGNED NOT NULL AUTO_INCREMENT,
  cust_name VARCHAR(45) NOT NULL,
  occupation VARCHAR(45) NOT NULL,
  income VARCHAR(15) NOT NULL,
  qualification VARCHAR(45) NOT NULL,
  PRIMARY KEY (customer_id)
);

INSERT INTO customer (cust_name, occupation, income, qualification) VALUES ('John Miller', 'Developer', '20000', 'Btech');  
INSERT INTO customer (cust_name, occupation, income, qualification) VALUES ('Mark Robert', 'Engineer', '40000', 'Btech');  
INSERT INTO customer (cust_name, occupation, income, qualification) VALUES ('Reyan Watson', 'Scientist', '60000', 'MSc');  
INSERT INTO customer (cust_name, occupation, income, qualification) VALUES ('Shane Trump', 'Businessman', '10000', 'MBA');  
INSERT INTO customer (cust_name, occupation, income, qualification) VALUES ('Adam Obama', 'Manager', '80000', 'MBA');  
INSERT INTO customer (cust_name, occupation, income, qualification) VALUES ('Rincky Ponting', 'Cricketer', '200000', 'Btech');  

+-------------+----------------+-------------+--------+---------------+
| customer_id | cust_name      | occupation  | income | qualification |
+-------------+----------------+-------------+--------+---------------+
|           1 | John Miller    | Developer   | 20000  | Btech         |
|           2 | Mark Robert    | Engineer    | 40000  | Btech         |
|           3 | Reyan Watson   | Scientist   | 60000  | MSc           |
|           4 | Shane Trump    | Businessman | 10000  | MBA           |
|           5 | Adam Obama     | Manager     | 80000  | MBA           |
|           6 | Rincky Ponting | Cricketer   | 200000 | Btech         |
+-------------+----------------+-------------+--------+---------------+


SELECT cust_name, occupation, qualification, NULLIF (qualification,"Btech") result FROM customer;

Output:-
+----------------+-------------+---------------+--------+
| cust_name      | occupation  | qualification | result |
+----------------+-------------+---------------+--------+
| John Miller    | Developer   | Btech         | NULL   |
| Mark Robert    | Engineer    | Btech         | NULL   |
| Reyan Watson   | Scientist   | MSc           | MSc    |
| Shane Trump    | Businessman | MBA           | MBA    |
| Adam Obama     | Manager     | MBA           | MBA    |
| Rincky Ponting | Cricketer   | Btech         | NULL   |
+----------------+-------------+---------------+--------+
```
