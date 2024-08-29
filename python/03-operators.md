# Operators

## Arithmetic operators

| Operator | Description                                                                     | 
|----------|---------------------------------------------------------------------------------|
| +        | Addition: x + y will give the sum of x and y.                                   |
| -        | Subtraction: x - y will subtract y from x.                                      |
| *        | Multiplication: x * y will give the produce of x and y.                         |
| /        | Division: x / y will give the quotient of x divided by y.                       |
| //       | Floor division: x // y will give the (integer) floor of the quotient            |
| %        | Modulus: x % y will give the remainder of x divided by y.                       |
| **       | Exponent: x ** y will raise x to the power of y.                                |
| =        | Assignment: x = y -> x takes the value of y.                                      |
```python

# assignment
x = 10
y = 5

print (x + y)
print (x * y)
# same for the others

print (x + y * 3) # The order of operations is the one you'd expect. * is evaluated first.
print ((x + y) * 3) # You can use paranthesis to change the order of operations, or to make it less ambiguous.
```

## Comparison operators

| Operator | Description                                                                               | 
|----------|-------------------------------------------------------------------------------------------|
| ==       | Equals: x == y is true if both x and y hold the same values. Works for numbers, strings, objects, lists                              |
| !=       | Not Equals: x != y is true if x and y hold different values.                              |
| >        | Greater than: x > y true if x holds a greater value than y.                               |
| <        | Lower than: x < y true if x holds a lower value than y.                                   |
| >=       | Greater than or equal to: x >= y true if x holds a greater value than y or if x equals y. |
| <=       | Lower than or equal to: x <= y true if x holds a lower value than y or if x equals y.     |                   

```python

x = 10
y = 5

print (x > y)
# same for the others
```

## Assignment operators

| Operator | Description                                                             | 
|----------|-------------------------------------------------------------------------|
| +=       | Addition: x += y will assign x the sum of x and y.                      |
| -=       | Subtraction: x -= y will assign x the subtraction of y from x           |
| *=       | Multiplication: x *= y will assign x the produce of x and y.            |
| /=       | Division: x /= y will assign x the quotient of x divided by y.          |
| %=       | Modulus: x %= y will assign x the reminder of x divided by y.           |
| **=      | Exponent: x **= y will assign x the value of x risen to the power of y. |
```python

# basic assignment
x = 10
y = x

# the assignment operator can be combined with the arithmetic operators:
z = 10
z += y # this expands to z = z + x, z will hold 20
print (z)
```

## The walrus operator
# :=

It's also called an assignment expression.

It's a way to shorten this:
```python
a = True
b = a
print(b)
```

into this:
```python
a = True
print(b:=a)

```

It assigns the right hand side to the left hand side, and returns the value. It's confusing for beginners, but you should know what it is in case you see it out there.  
Fun fact: It also caused Guido van Rossum(the guy who invented Python) to step down from his possition as the Benevolent Dictator For Life of Python.

## Boolean operators

| Operator | Description                                            | 
|----------|--------------------------------------------------------|
| not      | Logical NOT: not false is true.                        |
| or       | Logical OR: x or y is true if either x or y is true.   |
| and      | Logical AND: x and y is true if either x or y is true. |
```python

x = True
y = False

print (x and  y)
print (x or  y)
print (not x)
```

## Membership operators
We can test if a value is part of a sequence in python.

| Operator | Description                                                                      | 
|----------|----------------------------------------------------------------------------------|
| in       | x in y is true if x is in y, where y can be a list, tuple, dictionary or string  |
| not in   | x not in y is true if x is not in y                                              |
```python

x = [1, 2, 3]           # same if x is tuple
y = 2
z = 4

print (y in x)
print (z not in x)
# print (x not in z)    # error !

print ('p' in "python3")# True

dict = {'a': 1, 'b': 2} # for dictionaries, the `in` operator tests if the left hand side is a key in the dictionary

print('a' in dict) # True
print(1 in dict) # False
```

## Practice
You have the following variables:  
xs = [1, 2, 3]  
a = 20  
b = 30  

Without using loops, print the sum of the squares of the 3 elements of xs

Using a third variable of your choice, swap the values of `a` and `b`

Without using a third variable, swap the values of `a` and `b` Hint: use addition and subtraction. [(spoiler alert) solution](https://www.geeksforgeeks.org/swap-two-numbers-without-using-temporary-variable/)

Without using a third variable or arithmetics, swap the values of `a` and `b` using `=`. Hint: use multiple assignment from 02-variables. [(spoiler alert) solution](https://stackoverflow.com/questions/14836228/is-there-a-standardized-method-to-swap-two-variables-in-python)