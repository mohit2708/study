**[⬆ Back to Top](#table-of-contents)**
### **Delete**
* DELETE is a DML(Data Manipulation Language) command and is used when we specify the row (tuple) that we want to remove or delete from the table or relation. The DELETE command can contain a WHERE clause.
```sql
delete from table_name where ID=01;
delete from table_name where ID IN(2,6);
```

### **Truncate**
* A truncate SQL statement is used to remove all rows (complete data) from a table.
* TRUNCATE is a DDL(Data Definition Language) command and is used to delete all the rows or tuples from a table. Unlike the DELETE command, the TRUNCATE command does not contain a WHERE clause.
```sql
TRUNCATE TABLE table_name;
```


### **Ques. Difference between Delete, Truncate & Drop?**
| Delete                                                | Truncate                                                       | Drop                  |
| :---------------------------------------------------- | :------------------------------------------------------------- | :-------------------- |
| Delete is a DML command                               | Truncate is DDL command                                        |                       |
| We can use where clause in delete command             | We cannot use where clause with truncate                       |                       |
| Delete statement is used to delete a row from a table | Truncate statement is used to remove all the row from a table  | Remove table and data |
| You can rollback data after using delete statement    | It is not possible to rollback after using TRUNCATE statement. | Can’t rollback        |
| Delete is slower                                      | Truncate is faster                                             |                       |


### **Ques. Difference b/w DROP and TRUNCATE statements?**
* **Drop Table:-**
  * Table structure will be dropped
  * Relationship will be dropped
  * Integrity constraints will be dropped
  * Access privileges will also be dropped
* **TRUNCATE Table:-**
  * On the other hand when we TRUNCATE a table, the table structure remains the same, so you will not face any of the above problems.