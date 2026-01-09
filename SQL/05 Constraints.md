### Set Primary Key

```sql
ALTER TABLE table_name ADD PRIMARY KEY(column_name);
```

### Make Column Unique

```sql
ALTER TABLE table_name ADD UNIQUE(column_name);
```

### Prevent NULL Values

```sql
ALTER TABLE table_name ALTER COLUMN column_name SET NOT NULL;
```

### Delete Constraint

```sql
ALTER TABLE table_name DROP CONSTRAINT constraint_name;
```
