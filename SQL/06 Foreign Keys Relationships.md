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
Got it. Here’s a **focused, clean note** you can drop straight into your SQL notes.
Nothing extra. Only what matters.

---

### ON UPDATE RESTRICT / ON DELETE CASCADE

Usage Syntax
```sql
FOREIGN KEY (child_column)
REFERENCES parent_table(parent_column)
ON UPDATE RESTRICT
ON DELETE CASCADE
```


Example
```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name TEXT NOT NULL
);

CREATE TABLE orders (
    id SERIAL PRIMARY KEY,
    user_id INT NOT NULL,

    FOREIGN KEY (user_id)
        REFERENCES users(id)
        ON UPDATE RESTRICT
        ON DELETE CASCADE
);
```

How it behaves
```sql
-- Insert data
INSERT INTO users (name) VALUES ('Alice');
INSERT INTO orders (user_id) VALUES (1);
```

```sql
-- Try to update parent key
UPDATE users SET id = 2 WHERE id = 1;
-- ❌ Blocked due to ON UPDATE RESTRICT
```

```sql
-- Delete parent row
DELETE FROM users WHERE id = 1;
-- ✅ Related rows in orders are deleted automatically
```

