## **User Management**

### **Create User:-**
```sql
CREATE USER username@hostname IDENTIFIED BY 'password';  

* The hostname is optional then
CREATE USER username IDENTIFIED BY 'password'; 
```

#### **Show Users:-**
```sql
select user from mysql.user;
+---------+
| User    |
+---------+
| root    |
| mohits4 |
+---------+
```
* Show Current User
```sql
SELECT USER();
OR
Select current_user();
```

#### Grant Privileges to the MySQL New User:-
1. **ALL PRIVILEGES**: It permits all privileges to a new user account.
2. **CREATE**: It enables the user account to create databases and tables.
3. **DROP**: It enables the user account to drop databases and tables.
4. **DELETE**: It enables the user account to delete rows from a specific table.
5. **INSERT**: It enables the user account to insert rows into a specific table.
6. **SELECT**: It enables the user account to read a database.
7. **UPDATE**: It enables the user account to update table rows.

* If you want to give all privileges to a newly created user, execute the following command.
```sql
GRANT ALL PRIVILEGES ON * . * TO username@hostname;
```

* If you want to give specific privileges to a newly created user, execute the following command.
```sql
GRANT CREATE, SELECT, INSERT ON * . * TO username@hostname;
``` 

#### Show Privileges
```sql
SHOW GRANTS for mohits4;
```

#### REVOKE Privileges
```sql
REVOKE ALL PRIVILEGES ON *.* FROM 'mohits4'@'hostname';
```
* If you want to remove specific privileges to a newly created user
```sql
REVOKE SELECT ON *.* FROM 'mohits4'@'hostname';
```
* Revoke **SELECT privilege** on a **specific** **table**:
```sql
REVOKE SELECT ON database_name.table_name FROM 'mohits4'@'hostname';
```
* Revoke **all privileges** on a specific **database**:
```sql
REVOKE ALL PRIVILEGES ON database_name.* FROM 'mohits4'@'hostname';
```


- [ ] Note:- Sometimes, you want to flush all the privileges of a user account for changes occurs immediately
```sql
FLUSH PRIVILEGES;  
```

#### User Password Change
```sql
SET PASSWORD FOR 'mohits4'@'hostname' = PASSWORD('jtp12345');  
OR
ALTER USER mohits4@hostname IDENTIFIED BY 'jtp123';
```


#### Drop User
```sql
DROP USER mohits4@localhost;  
```
* can also be used to remove more than one user accounts at once.
```sql
DROP USER john@localhost, peter@localhost;  
```



