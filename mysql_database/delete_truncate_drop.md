**[⬆ Back to Top](#table-of-contents)**
### **Ques. Difference between Delete, Truncate & Drop?**
| Delete                                                | Truncate                                                       | Drop                  |
| :---------------------------------------------------- | :------------------------------------------------------------- | :-------------------- |
| Delete is a DML command                               | Truncate is DDL command                                        |                       |
| We can use where clause in delete command             | We cannot use where clause with truncate                       |                       |
| Delete statement is used to delete a row from a table | Truncate statement is used to remove all the row from a table  | Remove table and data |
| You can rollback data after using delete statement    | It is not possible to rollback after using TRUNCATE statement. | Can’t rollback        |
| Delete is slower                                      | Truncate is faster                                             |                       |