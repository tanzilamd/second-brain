### Shebang

Specifies the interpreter for your script. Usually at the first line:

```bash
#!/bin/bash
```

- `/usr/bin/bash` or `/bin/bash` are common locations.
    
- Makes sure your script runs with Bash, not another shell.
    

### Creating and Running Scripts

```bash
# Create a new script file
touch script.sh

# Run using sh
sh script.sh

# Run using bash directly
bash script.sh

# Make it executable and run
chmod +x script.sh
./script.sh
```

### Finding Bash Location

```bash
which bash
```

### Listing Files

```bash
ls -l
```

- Shows permissions: `-rw-r--r--`
    
    - `r` = read, `w` = write, `x` = execute
        
- First character indicates type: `-` regular file, `d` directory.
    