**[⬆ Back to Top](#table-of-contents)**
### **What is Index?**
* An index is used to enhance the performance of SQL Queries.
* It will get the data using Row Id, avoid full table scan.
* A database index is a data structure that improves the speed of operation in a table.
* index can be created one or more columns.
* Index allows the database application to find data fast, without reading the whole table.
* An index can be created in a table to find data more quickly and efficiently.

```sql
CREATE INDEX index_name on table_name (column_name)
CREATE INDEX index_name ON table_name (column1, column2);
```
#### Show Index
```sql
show index from table_name
```
#### drop Index
```sql
drop index index_name on table_name
```

**Types of index**
1. **cluster index:-** jab kisi table par hum primary key lagate hai to wo cluster index ban jata hai.
2. **Non cluster index:-** table mai jis column par select command sabse jyda chalte hai to us column par hum non cluster index bna lete hai.


### **Ques. What is the difference between cluster and non cluster index?**
* A clustered index reorders the way records in the table are physically stored. There can be only one clustered index per table. It makes data retrieval faster.
* A non clustered index does not alter the way it was stored but creates a completely separate object within the table. As a result insert and update command will be faster.
