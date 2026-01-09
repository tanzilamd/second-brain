### Create Table

```sql
CREATE TABLE table_name();
```

_Creates an empty table._

### Create Table with Columns

```sql
CREATE TABLE table_name(
    column_name DATATYPE CONSTRAINTS
);
```

_Define columns with types and optional constraints (PRIMARY KEY, UNIQUE, NOT NULL, etc.)._

### Add Column

```sql
ALTER TABLE table_name ADD COLUMN column_name DATATYPE;
```

### Remove Column

```sql
ALTER TABLE table_name DROP COLUMN column_name;
```

### Rename Column

```sql
ALTER TABLE table_name RENAME COLUMN column_name TO new_name;
```

### Delete Table

```sql
DROP TABLE table_name;
```

