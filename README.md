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
