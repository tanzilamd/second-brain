### Variables

```bash
NAME="Tanzil"
echo $NAME
```

- No spaces around `=` in Bash.
    
- `$VARIABLE` accesses the value.
    

### User Input

```bash
read NAME
echo "Hello $NAME!"
```

### Command Output in Variables

```bash
CURRENT_DATE=$(date)
echo "Today is $CURRENT_DATE"
```

### Special Variables

```bash
$?   # Exit status of last command
$*   # All command-line arguments
$#   # Number of arguments
$@   # All arguments individually
```
