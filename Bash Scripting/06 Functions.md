
```bash
#!/bin/bash

# Function with arguments
greet() {
    local name=$1
    echo "Hello, $name!"
}

greet Tanzil

# Function returning a value using echo
add_numbers() {
    local sum=$(( $1 + $2 ))
    echo $sum
}

result=$(add_numbers 5 7)
echo "Sum is: $result"

# Notes:
# - Arguments: $1, $2 ... $@ (all arguments)
# - local keeps variable inside function
# - Use echo to "return" values
```
