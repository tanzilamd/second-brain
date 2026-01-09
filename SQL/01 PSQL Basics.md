### PostgreSQL Login

```bash
# Full form
psql --username=tanzilamd --dbname=postgres

# Short form
psql -U tanzilamd -d postgres
```

_Connect to a database using your username._

### List Databases

```sql
\l
```

_Shows all databases in the PostgreSQL server._

### List Tables

```sql
\dt *
```

_Lists all tables across all databases._

```sql
\dt
```

_Lists tables in the currently connected database._

### Connect to a Database

```sql
\c dbname
```

_Switch to another database._

### Describe Table

```sql
\d table_name
```

_Shows table structure: columns, data types, indexes, constraints._

### Terminal Prompt Notes

- `second_database=>` : You’re connected to `second_database` and ready for a new command.
    
- `second_database->` : PostgreSQL is waiting for the current command to finish (your previous input is incomplete).
    
- Escape stuck command: `Ctrl + C`