**[⬆ Back to Top](#table-of-contents)**
### What is View?
* A view can contain all rows of a table or select rows from a table. A view can be created from one or many tables which depends on the written SQL query to create a view
* It is a kind of logical table, having no own data.
* A view is a virtual table which consists of a subset of data contained in a table. Views are not virtually present, and it takes less space to store. View can have data of one or more tables combined, and it is depending on the relationship.

__Syntax:-__
```sql
Create view view_name As
Select column1, column2
From  table_name  
Where [condition];
```
__Show view__
```sql
SELECT * FROM view_name;
```

#### Alter view
* CREATE OR REPLACE VIEW Syntax
```sql
CREATE OR REPLACE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

#### deleted view
* A view is **deleted** with the **DROP VIEW statement**.
```sql
DROP VIEW view_name
```
