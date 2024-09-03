# Bash Control Structures

### Conditional Statements
Conditional statements allow you to perform actions based on certain conditions.

#### `if` Statements
```bash
#!/bin/bash
if [ condition ]; then
  # code to execute if condition is true
fi
```

#### `if-else` Statements
```bash
#!/bin/bash
if [ condition ]; then
  # code to execute if condition is true
else
  # code to execute if condition is false
fi
```

Example:
```bash
#!/bin/bash
# Simple if statement

if [ $1 -gt 100 ]; then
  echo "The number $1 is greater than 100"
else
  echo "The number $1 is 100 or less"
fi
```

#### `case` Instruction
The `case` statement compares a variable against a list of values and executes corresponding commands.
```bash
case $variable in
  value1)
    # commands ;;
  value2)
    # commands ;;
  *)
    # default commands ;;
esac
```

### Loops
Loops allow you to repeat a block of code multiple times.

#### `for` Loop
```bash
#!/bin/bash
# Loop through a list of items

for item in apple banana cherry; do
  echo "I like $item"
done
```

### `while` Loop
```bash
#!/bin/bash
# Print numbers 1 to 5

count=1
while [ $count -le 5 ]; do
  echo "Count: $count"
  ((count++))
done
```

