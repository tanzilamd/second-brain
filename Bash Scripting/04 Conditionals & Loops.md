### Integer Comparison

Inside `[[ ]]`:

- `-eq` → equal
    
- `-ne` → not equal
    
- `-lt` → less than
    
- `-le` → less or equal
    
- `-gt` → greater than
    
- `-ge` → greater or equal
    

### If Statement

```bash
if [[ $a -gt $b ]]
then
    echo "a is greater"
else
    echo "b is greater or equal"
fi
```

### For Loop

```bash
for (( i=10; i>0; i-- ))
do
    echo $i
done
```

### Until Loop

```bash
count=1
until [[ $count -gt 5 ]]
do
    echo $count
    ((count++))
done
```
