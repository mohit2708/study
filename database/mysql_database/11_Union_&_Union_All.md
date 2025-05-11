**[⬆ Back to Top](#table-of-contents)**
### Ques. What Is Union & Union All?
* Both UNION and UNION ALL Operator combine rows from result sets into a single result set.
  
#### UNION
* The union operator combines the results of two or more select statements by removing duplicate rows.
* The columns and the data types must be the same in select statements.
```sql
Select Column1, Column2, Column3 from Table A
UNION
Select Column1, Column2, Column3 from Table B
```

### UNION ALL
* The UNION operator selects only distinct values by default. To allow duplicate values, use UNION ALL
```sql
Select Column1, Column2, Column3 from Table A
UNION ALL
Select Column1, Column2, Column3 from Table B
```

**[⬆ Back to Top](#table-of-contents)**
### **Ques. Difference between Union & Union All?**
| Union                                                     | Union All                                     |
| :-------------------------------------------------------- | :-------------------------------------------- |
| Union removes duplicate rows.                             | Union All does not remove the duplicate rows. |
| Union uses a distinct sort                                | Union All does not use a distinct sort        |
| Union can’t work with a column that has a text data type. | Union All can work with all data type column. |
