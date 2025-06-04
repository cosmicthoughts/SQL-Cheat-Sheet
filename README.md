# SQL-Cheat-Sheet

This repository contains a concise and comprehensive SQL cheat sheet based on a structured reference guide. It's designed to help developers, data analysts, and students quickly recall essential SQL syntax, clauses, and operations.

## What is SQL?
SQL stands for Structured Query Language. It is a programming language used to store and manipulate the data in relational databases.

---

## SQL Database
### Create Database
Used to create a new SQL database with specified name
```
CREATE DATABASE database_name;
```
### Drop Database
Used to delete an existing SQL database.
```
DROP DATABASE database_name;
```
### Backup Database
Used to create full back up of an existing sql_database.
```
BACKUP DATABASE database_name TO DISK = 'filepath';
```
### Backup Database with Differential
Used to create a differential back up of an existing SQL database. It backs up only the data that has changed since the last full back up.
```
BACKUP DATABASE database_name TO DISK = 'filepath' WITH DIFFERENTIAL;
```

##  SQL Constraints
SQL Constraints are used to specify the rules for the columns of a table.
- NOT NULL: A column declared with NOT NULL can’t have null values.
- UNIQUE: A column declared as UNIQUE can’t have duplicate values.
- DEFAULT: It specifies the default value for a column if no value is provided.
- PRIMARY KEY: It declares a column as primary key.
- FOREIGN KEY: It declares a column as foreign key.
- CHECK: It ensures that values in a column must satisfy the given condition.

## SQL Operators
### Arithmetic Operators
Add (+), Subtract (-), Multiply (*), Divide (/), Modulus (%)
### Comparison Operators
Equal To (=), Smaller Than (<), Greater Than (>), Smaller than or equal to (<=), Greater than or equal to (>=), Not equal to (<>)
### Compound Operators
Add equals (+=), Subtract equals (-=), Multiply Equals (*=), Divide equals (/=), Modulo equals (%=), Bitwise AND equals (&=), Bitwise OR equals (|=), Bitwise exclusive OR equals (^=)
### Logical Operators
AND, OR, NOT, ALL, ANY, BETWEEN, IN, EXISTS, LIKE, SOME

## SQL Views
SQL views are the virtual tables based on a result set of an SQL statement. It contains rows and columns similar to a real table
### Create View
Used to create a view
```
CREATE VIEW view_name AS SELECT column1, column2 … FROM table_name WHERE condition;
```
### Drop View
Used to delete a view
```
DROP VIEW view_name;
```

## SQL Tables
### Create Table
Used to create a new table in a database
```
CREATE TABLE table_name (column1 datatype, column2 datatype, column3 datatype …);
```
### Insert Into
Used to insert new records into a table
```
INSERT INTO table_name (column1, column2, column3 …) VALUES (value1, value2, value3 …);
```
### Drop Table
Used to delete an existing table in a database.
```
DROP TABLE table_name;
```
### Truncate Table
Used to delete all the data from a table but not the table itself.
```
TRUNCATE TABLE table_name;
```
### ALTER TABLE
Used to add, delete and modify the columns in an existing table.
#### Add Column
```
ALTER TABLE table_name ADD column_name datatype;
```
#### Delete a column from a table
```
ALTER TABLE table_name DROP COLUMN column_name;
```
#### Rename a column of a table
```
RENAME COLUMN old_name TO new_name;
```
#### Change the datatype of a column:
```
ALTER TABLE table_name MODIFY column_name datatype;
```
### Update Table
Used to modify or update table records.
```
UPDATE table_name SET column1 = value1, column2 = value2 … WHERE condition;
```
### Delete Table
Used to delete records from a table
```
DELETE FROM table_name WHERE condition;
```
## SQL Clauses

### Where  
Used to retrieve or update or delete the records based on some condition. This clause can be used with SELECT, UPDATE and DELETE statements.

#### SELECT with WHERE:
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```

#### UPDATE with WHERE:
```sql
UPDATE table_name SET column1 = value1 WHERE condition;
```

#### DELETE with WHERE:
```sql
DELETE FROM table_name WHERE condition;
```

### Order By  
Used to sort the records in ascending or descending order.
```sql
SELECT column1, column2 FROM table_name ORDER BY column_name ASC|DESC;
```

### Group By  
Groups rows that have the same values.
```sql
SELECT column_name, COUNT(*) FROM table_name GROUP BY column_name;
```

### Having  
Used to filter groups based on aggregate functions.
```sql
SELECT column_name, COUNT(*) FROM table_name GROUP BY column_name HAVING COUNT(*) > 1;
```

---

## SQL Joins

### Inner Join  
Returns records with matching values in both tables.
```sql
SELECT column_name(s)
FROM table1
INNER JOIN table2 ON table1.column = table2.column;
```

### Left Join  
Returns all records from the left table, and matched records from the right.
```sql
SELECT column_name(s)
FROM table1
LEFT JOIN table2 ON table1.column = table2.column;
```

### Right Join  
Returns all records from the right table, and matched records from the left.
```sql
SELECT column_name(s)
FROM table1
RIGHT JOIN table2 ON table1.column = table2.column;
```

### Full Outer Join  
Returns all records when there is a match in either left or right table.
```sql
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2 ON table1.column = table2.column;
```

---

## SQL Functions

### COUNT()  
Returns the number of rows matching the condition.
```sql
SELECT COUNT(column_name) FROM table_name WHERE condition;
```

### AVG()  
Returns the average value of a numeric column.
```sql
SELECT AVG(column_name) FROM table_name;
```

### SUM()  
Returns the sum of a numeric column.
```sql
SELECT SUM(column_name) FROM table_name;
```

### MIN() / MAX()  
Returns the smallest/largest value in a column.
```sql
SELECT MIN(column_name), MAX(column_name) FROM table_name;
```

### ROUND()  
Rounds a numeric field to the number of decimals.
```sql
SELECT ROUND(column_name, decimals) FROM table_name;
```

### NOW()  
Returns the current date and time.
```sql
SELECT NOW();
```

---

## SQL Stored Procedures

### Create Stored Procedure  
```sql
CREATE PROCEDURE procedure_name AS
BEGIN
  -- SQL statements
END;
```

### Execute Stored Procedure  
```sql
EXEC procedure_name;
```

---

## SQL Indexes

### Create Index  
```sql
CREATE INDEX index_name ON table_name (column_name);
```

### Drop Index  
```sql
DROP INDEX index_name;
```

---

## SQL Miscellaneous

### AND / OR / NOT  
Used to filter records with multiple conditions.
```sql
SELECT column1, column2 FROM table_name WHERE condition1 AND condition2;
```

### EXISTS  
Tests for existence of any record in a subquery.
```sql
SELECT column_name FROM table_name
WHERE EXISTS (
  SELECT * FROM another_table WHERE condition
);
```

### AS (Alias)  
Gives a temporary name to columns or tables.
```sql
SELECT column_name AS alias_name FROM table_name;
SELECT * FROM table_name AS t;
```

### LIKE  
Searches for a pattern in a column.
```sql
SELECT column_name FROM table_name WHERE column_name LIKE '%pattern%';
```

### IN  
Matches a value against a list.
```sql
SELECT * FROM table_name WHERE column_name IN (value1, value2);
```

### BETWEEN  
Selects values within a range.
```sql
SELECT * FROM table_name WHERE column_name BETWEEN value1 AND value2;
```

### IS NULL / IS NOT NULL  
Checks for (non-)null values.
```sql
SELECT * FROM table_name WHERE column_name IS NULL;
SELECT * FROM table_name WHERE column_name IS NOT NULL;
```

## SQL Indexes
SQL Indexes are used to speed up search queries in the database tables.
### Create Index
Used to create indexes on the database tables
```
CREATE INDEX index_name ON table_name (column_name);
```
### Create Unique Index
Ensures all values in the indexed column(s) are distinct.
```
CREATE UNIQUE INDEX index_name ON table_name (column_name);
```
### Drop Index
Deletes an index from the database
[!TIP]
Syntax can vary depending on the database system.
#### For SQL Server
```
DROP INDEX index_name ON table_name;
```
#### For MySQL
```
DROP INDEX index_name ON table_name;
```
#### For PostgreSQL
```
DROP INDEX index_name;
```
### Rename Index
Optional, where supported
```
ALTER INDEX old_index_name RENAME TO new_index_name;
```
