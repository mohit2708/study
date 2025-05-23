#### What is Index?
* An index is used to enhance the performance of SQL Queries. It allows the database to find data quickly and efficiently by using Row ID, avoiding full table scans.
* Indexes can be created on one or more columns of a table.
* Index allows the database application to find data fast, without reading the whole table.
* An index can be created in a table to find data more quickly and efficiently.
* **How It Works:-** Behind the scenes, an index is usually implemented as a B-tree or similar structure.

### Types of Indexes?
1. **Single-column index:-** on one column
```sql
CREATE INDEX idx_product_id ON Sales (product_id);
```
2. **Composite/Multi-column indexes:** on multiple columns
```sql
CREATE INDEX idx_dept_salary ON employees(department, salary);
```
3. Unique Index:- 
```sql
CREATE UNIQUE INDEX idx_email_unique ON employees(email);
```
4. Full-Text Index :- Designed for efficient text search in large text fields (e.g., for searching keywords in articles, product descriptions, etc.)
```sql
CREATE FULLTEXT INDEX idx_description ON products(description);
```


### Unique Indexes
* A Unique Index is a database index that ensures the uniqueness of values in one or more columns of a database table.
* This index ensures that no two rows in the Employees table have the same employee_id(Colum_name), which maintains data integrity and prevents duplicate entries.
* The SQL Unique Index ensures that no two rows in the indexed columns of a table have the same values (no duplicate values allowed).
```sql
-- Single column unique index
CREATE UNIQUE INDEX idx_email ON users(email);

-- Composite unique index
CREATE UNIQUE INDEX idx_name_age ON employees(last_name, first_name);
```

#### Show Index
```sql
show index from table_name
```

#### Alter/Modify an Index
```sql
-- Rename Index name
ALTER TABLE table_name 
RENAME INDEX old_index_name TO new_index_name;

-- Modify Index name
ALTER TABLE table_name DROP INDEX existing_index,
ADD INDEX new_index (column1, column2);

-- Rebuild Index
ALTER INDEX index_name 
ON table_name REBUILD;

-- Reorganize Index
ALTER INDEX index_name 
ON table_name REORGANIZE;

-- Disable Index
ALTER INDEX index_name 
ON table_name DISABLE;

-- Change Index Properties
ALTER INDEX index_name 
ON table_name 
SET (
    STATISTICS_NORECOMPUTE = OFF,
    ALLOW_ROW_LOCKS = ON,
    ALLOW_PAGE_LOCKS = ON
);
```

#### Drop Index
```sql
Drop index index_name on table_name
(OR) DROP INDEX table_name.index_name;

-- DROP INDEX with IF EXISTS
DROP INDEX IF EXISTS index_name
ON table_name;


ALTER TABLE table_name DROP CONSTRAINT constraint_name;
```

### Types of index
1. **cluster index:-** jab kisi table par hum primary key lagate hai to wo cluster index ban jata hai.
2. **Non cluster index:-** table mai jis column par select command sabse jyda chalte hai to us column par hum non cluster index bna lete hai.


### **Ques. What is the difference between cluster and non cluster index?**
* A clustered index reorders the way records in the table are physically stored. There can be only one clustered index per table. It makes data retrieval faster.
* A non clustered index does not alter the way it was stored but creates a completely separate object within the table. As a result insert and update command will be faster.
