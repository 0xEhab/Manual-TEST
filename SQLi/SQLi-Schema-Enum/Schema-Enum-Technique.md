# Schema Enumeration Technique

## What is a Schema?

A **schema** is the blueprint of a database that defines how data is organized. It contains **tables**, which store data in rows, and **columns**, which define individual fields of that data (e.g., `id`, `username`, `password`).  

In SQL databases, schema information is stored in the special **`INFORMATION_SCHEMA`** database. This makes it a key target during **SQL Injection (SQLi)** or pentesting for database enumeration.

---

## Important Views in `INFORMATION_SCHEMA`

1. **SCHEMATA**  
	Lists all databases (schemas) in the system.  

	*Main Idea*
	```sql
	SELECT SCHEMA_NAME 
	FROM INFORMATION_SCHEMA.SCHEMATA;
	```
2. **TABLES**
Lists all tables in a specific database.

	*Main Idea*
	```
	SELECT TABLE_NAME 
	FROM INFORMATION_SCHEMA.TABLES
	WHERE TABLE_SCHEMA = 'your_database_name';
	```
2. **COLUMNS**
	Lists all columns in a specific table, including their data types.

	*Main Idea*
	```
	SELECT COLUMN_NAME, DATA_TYPE 
	FROM INFORMATION_SCHEMA.COLUMNS
	WHERE TABLE_SCHEMA = 'your_database_name' 
	  AND TABLE_NAME = 'your_table_name';
	```	