### Create Relationships (Foreign Keys)

Adding a new column with foreign key:
```sql
ALTER TABLE table_name 
ADD COLUMN column_name DATATYPE CONSTRAINT REFERENCES referenced_table_name(referenced_column_name);
```

Adding foreign key to an existing column:
```sql
ALTER TABLE table_name 
ADD FOREIGN KEY(column_name) REFERENCES referenced_table_name(referenced_column_name);
```

**Types of Relationships**

- One-to-One
    
- One-to-Many
    
- Many-to-Many
    