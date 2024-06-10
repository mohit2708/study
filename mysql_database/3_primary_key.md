### **Ques. What Is Primary Key?**
* The PRIMARY KEY constraint uniquely identifies each record in a database table. It must contain unique values. A Primary Key column cannot have Null values.
* A table can have only one primary key, which may consist of single or multiple fields. When multiple fields are used as a primary key, they are called a composite key.<br>
* **Create Primary Key:-**
```sql
CREATE TABLE emp(
        Emp_ID INT primary key,
        Emp_name Varchar(100),
        Emp_Sal Decimal (10,2)
)
# OR 
CREATE TABLE emp(
        Emp_ID INT,
        Emp_name Varchar(100),
        Emp_Sal Decimal (10,2),
        primary key (emp_id)
)
```
* **Delete primary Key**
```sql
ALTER TABLE CUSTOMERS DROP PRIMARY KEY;
```
* **Add primary Key**
```sql
ALTER TABLE table_name ADD PRIMARY KEY (Id)
```