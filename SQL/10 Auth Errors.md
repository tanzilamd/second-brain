### PostgreSQL Auth Errors on Linux (Short Note)

On Linux, PostgreSQL uses **peer authentication** by default. This means PostgreSQL does not check a password. It checks whether the **Linux user name** matches the **PostgreSQL user name**. If they don’t match, authentication fails.

Example problem:
```bash
psql -U postgres -d my_database
```

Fails because:

-  Linux user: `tanzilamd`
    
- PostgreSQL user: `postgres`
    
- Names don’t match → error
    

---

### Ways to fix / work around it

**Option 1 (without changing config):**

```bash
sudo -i -u postgres
psql -U postgres -d my_database
```

-  Switches Linux user to `postgres`
    
- Peer authentication succeeds
    
- Works immediately, but requires `sudo` every time
    

**Option 2 (recommended):**

Edit `/etc/postgresql/16/main/pg_hba.conf` and change:*
```bash
local   all   postgres   peer
```

to

```bash
local   all   postgres   md5
```

*Optionally, change **all local connections**:*
```bash
local   all   all   md5
```

Restart PostgreSQL:
```bash
sudo service postgresql restart
```

Set a password for `postgres`:
```bash
sudo -u postgres psql
\password postgres
```

Now you can connect easily:
```bash
psql -U postgres -d my_database
```


**Note:** This auth problem can affect setting up database extensions in VS Code, since they need proper password authentication.