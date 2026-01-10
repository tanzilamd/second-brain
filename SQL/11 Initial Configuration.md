### PostgreSQL Initial Configuration on Linux Mint

Here’s the practical setup you should do _after_ installing PostgreSQL on Linux Mint. 

---

#### 1. Check that PostgreSQL is running

Postgres runs as a background service.

```bash
sudo systemctl status postgresql
```

If it’s not active:

```bash
sudo systemctl start postgresql
```

This confirms the database server is actually running.

---

#### 2. Access PostgreSQL as the admin user

Linux creates a system user called `postgres`. By default, this user can access Postgres without a password.

```bash
sudo -u postgres psql
```

This drops you into the `psql` shell as a superuser.

---

#### 3. Understand default authentication (peer)

On Linux Mint, local connections use **peer authentication**.

What this means:

- Linux username must match PostgreSQL username
    
- Otherwise, authentication fails
    

Config file:

```text
/etc/postgresql/<version>/main/pg_hba.conf
```

You’ll usually see:

```text
local   all   all   peer
```

---

#### 4. (Recommended) Set a password for `postgres`

Useful for GUI tools and VS Code.

```sql
ALTER USER postgres PASSWORD 'strong_password';
```

---

#### 5. Create your own database user

Avoid using `postgres` for daily work.

```sql
CREATE USER tanzil WITH PASSWORD 'user_password';
```

---

#### 6. Create a database and assign ownership

```sql
CREATE DATABASE my_database OWNER tanzil;
```

This keeps permissions clean and predictable.

---

#### 7. Enable password-based login (if needed)

Edit `pg_hba.conf` and change:

```text
local   all   all   peer
```

to:

```text
local   all   all   md5
```

Then restart PostgreSQL:

```bash
sudo systemctl restart postgresql
```

---

#### 8. Test the connection

```bash
psql -U tanzil -d my_database
```

If this works, your setup is complete.

---

**Summary:**  
PostgreSQL on Linux Mint is secure by default. Most “auth errors” come from peer authentication. Once users, passwords, and `pg_hba.conf` are configured, Postgres behaves normally with editors and GUI tools.