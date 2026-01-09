### Merge Tables Horizontally (JOIN)

```sql
SELECT columns 
FROM table_1 
FULL JOIN table_2 
ON table_1.primary_key_column = table_2.foreign_key_column;
```

### Merge Multiple Tables via Junction Table

```sql
SELECT columns 
FROM junction_table
FULL JOIN table_1 ON junction_table.foreign_key_column = table_1.primary_key_column
FULL JOIN table_2 ON junction_table.foreign_key_column = table_2.primary_key_column;
```
