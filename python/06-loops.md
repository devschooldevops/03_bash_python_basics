# Loops in python

There are 2 main types of loops in python: `while` loops and `for` loops.
You use `while` loops when you want to repeat until a certain condition is met.
You use `for` for everything else.

Here's a while loop in action:
```python
index = 0
while index < 5: # Anything you put in here should result in a boolean value.
    print("This is index " + str(index)) # Note: we use str(index) to transform the number into a string, so that it may be concatenated. Numbers and strings can't be added together as is.
    index += 1

```

`while` loops are cool for doing stuff where you don't exactly know when you'll stop, but know how to check.
In the above example we know from the start when we'll be stopping. Here's a more relevant example:

```python
num = int(input("Enter a number:")) # Note: we use int(input(...)) to transform the string input into a number.
while num != 3:
    print("Wrong number, try again!")
    num = int(input("Enter a number:"))
```

Make sure your while loop can end.

## The for loop

The for loop is used to iterate over `list`, `tuple`, `dictionary`, `set`, `string` or other iterable objects.
Python's for is different to other languages' for loops. There's no `for (int i = 0; i < n; i++)` here.
In other languages, python's for would be called `foreach`

for example, we can iterate over a list like so:

```python
animals = ["cat", "dog", "kangaroo", "shark"]
for animal in animals:
    print("The zoo has a " + animal)
```

You can also iterate over a range of numbers:
```python
for i in range(100):
    print("This is the number " + str(i)) 
# This will print 100 lines, from 0 to 99
```

You can also use `ranges` to iterate over lists, while keeping track of the index:
```python
letters = ['a', 'b', 'c']
for i in range(len(letters)): # len(x) is the length of x, where x can be a list, string, tuple, dict etc...
    print(letters[i] + " is at index " + str(i))
```

This is not very pythonic, since it requires you to index into the letters list.
Here's another, more pythonic way to do the same thing:
```python
letters = ['a', 'b', 'c']
for idx, letter in enumerate(letters): # enumerate returns a list of pairs, where the first element is the index and the second element is the value: [(1, 'a'),(2, 'b'),(3, 'c')]
    print(letter + " is at index " + str(idx))
```

This works just as well for tuples:
```python
letters = ('a', 'b', 'c')
for idx, letter in enumerate(letters):
    print(letter + " is at index " + str(idx))
```

Dictionaries are a bit different since they are collections of pairs:
```python
dict = {'cat': 'meow', 'dog': 'bark', 'cow': 'moo'}
for key in dict:
    print(key)
# This will print cat, dog, cow on separate lines. By default, dictionaries iterate over keys. You can also explicitly iterate keys by using dict.keys()
```

```python
dict = {'cat': 'meow', 'dog': 'bark', 'cow': 'moo'}
for value in dict.values():
    print(value)
# This will print meow, bark, moo on separate lines. 
```

You can use `dict.items()` to iterate through keys and values together:
```python
dict = {'cat': 'meow', 'dog': 'bark', 'cow': 'moo'}
for animal, sound in dict.items():
    print(animal + " says " + sound)
# This will print cat says meow etc. 
```


You can break out of any types of loop early by using the `break` keyword.
```python
attendants = ["Alice", "Bob", "Fido", "Trudy"]
for attendant in attendants:
    print(attendant + " is entering the building")
    if attendant == "Fido":
        print("No dogs allowed, closing the doors!")
        break # Since we're breaking out here, Trudy will not have a chance to enter the building.
```

You can also skip an iteration by using the `continue` keyword.
```python
attendants = ["Alice", "Bob", "Fido", "Trudy"]
for attendant in attendants:
    if attendant == "Fido":
        print("No dogs allowed!")
        continue
    print(attendant + " is entering the building") # This does not execute for Fido
```

Here's a pretty neat way of iterating the lines of a file:
```python
with open("file.txt") as file:
    for line in file:
        print("this is the line: " + line)
```


## Practice
In a file called 06.py, do the following:

1. Read a number from stdin.  
Print the number of divisors that number has(except 1 and itself).  X is divisible by Y if X % Y is 0.  
Hint: the range() function can take 2 arguments -> range(2,10) will go from 2 to 9

2. Read a number from stdin.  
Print the number of divisors of every number from 2 to itself.

## Homework

Make a command line app that requires a password.  
Ask the user for a password.  
If the password is wrong, print "Try again."  
After 3 wrong attempts, print "Program closing" to stderr.  
If the password is right, print "Access granted"