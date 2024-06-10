### **Ques. What is Composite Key?**
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