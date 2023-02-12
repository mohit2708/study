### **Mysql cmd:-**
1. connect database
```sql
mysql -u user_name  -p
password:
```

2. SHOW DATABASES;
3. use databses_name;
4. show tables;
5. Delete table from the databses
```sql
DROP TABLE table_name;
```

6. Show the datatype in table
```sql
SHOW COLUMNS FROM table_name;
```

7. Import database:-
```sql
mysql -u user_name -p database_name < var/www/html/db/table.sql;
```

8. Export Databse:-
```sql
mysqldump -u user_name -p database_name --ignore-table=job_equipment.job_equipment > /var/www/html/db/table.sql
```

9. delete the folder or file:-
```sql
rm -rf /var/www/example
```

10. Unzip The folder
```sql
unzip file_name.zip
```


sudo chmod -R 777 /var/www/html/routes/web.php
