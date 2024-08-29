# Control flow

Control flow is the order of execution of the lines/statements/expressions/function calls in your script.  
Unless otherwise altered, lines are executed top to bottom.

## The `if` statement

Allows you to execute code only if a certain condition is met.

syntax:
```python
if <condition>:
    <statements>
elif <other_condition>:
    <statements>
else:
    <statements>
```

example:

```python
name = "John"

if name == "Andrew":
    print("Hi Andrew")
elif name == "Michael":
    print("Hello Michael")
else:
    print("Hello stranger")
```

You can chain as many `elif` as you like.

## The ternary operator

Similar to the `?` operator in C.  
Can be used like a one line if statement that has a return value

syntax:
```python
variable = <value1> if <condition> else <value2>
```

example:
```python
num = 4
parity = "even" if num % 2 == 0 else "odd"
print(parity)
```

## Switch-cases

Allow you to test against multiple values.

```python
response_code = 201
match response_code:
    case 200:
        print("OK")
    case 201:
        print("Created")
    case 300:
        print("Multiple Choices")
    case 307:
        print("Temporary Redirect")
    case 404:
        print("404 Not Found")
    case 500:
        print("Internal Server Error")
    case 502:
        print("502 Bad Gateway")
```

You can also group cases together:

```python
colour = "red"
match colour:
    case "red" | "orange":
        print("warm")
    case "blue" | "green":
        print("cold")
```

You can also add a default value:

```python
colour = "red"
match colour:
    case "red" | "orange":
        print("warm")
    case "blue" | "green":
        print("cold")
    case _:
        print("unknown colour")
```

There are more options to alter control flow that won't be explored here. Feel free to take a look at the [cheatsheet](https://www.pythoncheatsheet.org/cheatsheet/control-flow)


## Practice
this bit of code will generate a random number between 0 and 9(inclusive):
```python
from random import randrange
num = randrange(10)

```

write a 04-script.py that has the following behaviour:  
Generates a random number.  
If the number is divisible by 4, print "Divisible by 4".   
If the remainder of dividing by 4 is 1, print "Remainder is one".  
If the remainder of dividing by 4 is 2, print "Remainder is two".  
If the remainder of dividing by 4 is 3, print "Remainder is three".  

The output of your program should be a single printed line.

Use a mix of ternary, if and switch statements.
Try to use string concatenation to avoid duplicating the "Remainder is" text.