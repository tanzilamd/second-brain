### Login Postgres
```bash
psql --username=tanzilamd --dbname=postgres
```
*Short version*
```bash
psql -U tanzilamd -d postgres
```

**List databases**
```bash
\l
```

All Table list
```bash
\dt *
```

Table list of a database
```bash
\dt
```

connect to a database
```
\c dbname
```

**describe tables**
```bash
\d dbname
```


Create Database
```
CREATE DATABASE db_name;
```

Create Table
```
CREATE TABLE table_name();
```

Create Table with column
```sql
CREATE TABLE table_name(column_name DATATYPE CONSTRAINTS);
```

Add column
```sql
ALTER TABLE table_name ADD COLUMN column_name DATATYPE;
```

Remove Column
```sql
ALTER TABLE table_name DROP COLUMN column_name;
```

Rename Column
```sql
ALTER TABLE table_name RENAME COLUMN column_name TO new_name;
```

Standard way of insert

```sql
INSERT INTO table_name(column_1, column_2) VALUES(value1, value2);
```

View Table
```sql
SELECT * FROM table_name;
```

Delete a row
```sql
DELETE FROM table_name WHERE condition;
```

Delete Table
```sql
DROP TABLE table_name;
```

Rename Database
```sql
ALTER DATABASE database_name RENAME TO new_database_name;
```

Delete Database
```sql
DROP DATABASE database_name;
```

Update Data
```sql
UPDATE table_name SET column_name=new_value WHERE condition;
```

Show Data by Order
```sql
SELECT columns FROM table_name ORDER BY column_name;
```

Show Specific Data
```sql
SELECT columns FROM table_name WHERE condition;
```

Set Primary Key
```sql
ALTER TABLE table_name ADD PRIMARY KEY(column_name);
```

Delete Constraint
```sql
ALTER TABLE table_name DROP CONSTRAINT constraint_name;
```

Creating Relationships Between Tables (Foreign Keys) - add new column
```sql
ALTER TABLE table_name ADD COLUMN column_name DATATYPE CONSTRAINT REFERENCES referenced_table_name(referenced_column_name);
```
Creating Relationships Between Tables (Foreign Keys) - column already exists
```sql
ALTER TABLE table_name ADD FOREIGN KEY(column_name) REFERENCES referenced_table(referenced_column);
```
- *one-to-one*
- *one-to-many*
- *many-to-many*

Making a Column Unique
```sql
ALTER TABLE table_name ADD UNIQUE(column_name);
```

Preventing NULL Values in a Column
```sql
ALTER TABLE table_name ALTER COLUMN column_name SET NOT NULL;
```

Merging Tables: Horizontally and Vertically
```sql
SELECT columns FROM table_1 FULL JOIN table_2 ON table_1.primary_key_column = table_2.foreign_key_column;
```

Using a Junction Table with FULL JOIN to Combine Multiple Tables
```sql
SELECT columns FROM junction_table
FULL JOIN table_1 ON junction_table.foreign_key_column = table_1.primary_key_column
FULL JOIN table_2 ON junction_table.foreign_key_column = table_2.primary_key_column;
```


### Data Type
VARCHAR, INT, DATE

### Terminal Commands clarifications

`second_database=>`
This means:
-  You’re connected to `second_database`
-  `psql` is ready for a **new command**

`second_database->`
This means:
- `psql` is **waiting for you to finish** a command
- Your previous input is incomplete

**How to escape if you’re stuck**
`Ctrl + C`



Note:
-A common data type is `VARCHAR`. It's a short string of characters.