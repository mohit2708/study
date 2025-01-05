#### AND Condition
* The MySQL AND Condition (also called the AND Operator) is used to test two or more conditions in a SELECT, INSERT, UPDATE, or DELETE statement.
*  AND condition allows you to test 2 or more conditions.
```sql
WHERE condition1
AND condition2
...
AND condition_n;
```
```sql
SELECT * FROM contacts
WHERE state = 'California'
AND contact_id > 3000;
```