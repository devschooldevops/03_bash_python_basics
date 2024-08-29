# Variables
```python
# basic variables
integer = 100
number = 1000.0
string = "John"

print (integer)
print (number)
print (string)

# multiple assignment, this is very useful
a, b, c = 1, 2, "john"
```

## Numbers
In python, we have number types int, float and complex.
```python
integer = 1
floating_point = 2.0
complex_number = complex(1, 2)
pretty_complex_number = 1 + 2j
num = int("123", 10)

print(integer)
print(floating_point)
print(complex_number)
print(num)
```

## Boleans
There's 2 of them: `True` and `False`. Mind the capitalization
```python
is_python_fun = True
```
## String
Strings in Python are identified as a contiguous set of characters represented in the quotation marks. 
Subsets of strings can be taken using the slice operator ([ ] and [:] ) 
with indexes starting at 0 in the beginning of the string and working their 
way from -1 to the end.
```python
hello = 'Hello World!' #Note: you can use both ' and " for strings

print(hello)          # Prints complete string
print(hello[0])       # Prints first character of the string
print(hello[-1])      # Prints last character of the string
print(hello[2:4])     # Prints characters starting from 3rd to 4th
print(hello[1:])      # Prints string starting from 2nd character ('e')
print(hello * 2)      # Prints string two times
print(hello + "TEST") # Prints concatenated string

# triple quote
long_string = """
very
very
long
string
"""
print (long_string)

print(len(hello))
```

## Lists
A list contains items separated by commas and enclosed within square brackets. Each element can be of any type (even another list). 
```python
sample_list = [ 'a', 22 , 'h', 3.14, 'asdf', [2, 3] ]

print(sample_list)                        # Prints complete list
print(sample_list[0])                     # Prints first element of the list
print(sample_list[-1])                    # Prints last element of the list
# You can also take slices of the list like so:
print(sample_list[1:3])                   # Prints elements starting from 2nd till 3rd 
print(sample_list[2:])                    # Prints elements starting from 3rd element
# Some operators also have meaning for lists:
print(sample_list * 2)                    # Prints list two times
print(sample_list[0:3] + sample_list[5:]) # Prints concatenated lists

sample_list[1] = 21
print(sample_list[1])    # 21, not 22, this is an update

del sample_list[1]
print(sample_list[1])    # prints h, 21 has been removed

sample_list.append('abcd') #append adds to the end of the list
print(sample_list[-1])   # abcd

sample_list.insert(1, 22)
print(sample_list[1])    # 22 is back !!

sample_list.reverse()
sample_list.reverse()    # double reverse, same list

sample_list.remove(22)
print(sample_list)       # removed 22
```
## List comprehensions

If you want to create a list that can be easily described (eg. all even numbers <=100), you can use list comprehensions:
```python
even_numbers = [x * 2 for x in range(51)] # ranges are exclusive. We'll talk more about ranges in 06-loops.
print(even_numbers)

# You can also have conditions in list comprehensions:
my_numbers = [x * 2 for x in range(51) if x % 3 == 0]
print(my_numbers)
```

## Tuples
The main difference between lists and tuples are − Lists are enclosed in brackets ( [ ] ) and their elements and size can be changed, 
while tuples are enclosed in parentheses ( ( ) ) and cannot be updated. 
Tuples can be thought of as read-only lists.
```python
sample_tuple = ( 'a', 22 , 'h', 3.14, 'asdf', [2, 3] )

print(sample_tuple)                         # Prints complete tuple
print(sample_tuple[0])                      # Prints first element of the tuple
print(sample_tuple[-1])                     # Prints last element of the tuple
print(sample_tuple[1:3])                    # Prints elements starting from 2nd till 3rd 
print(sample_tuple[2:])                     # Prints elements starting from 3rd element
print(sample_tuple * 2)                     # Prints tuple two times
print(sample_tuple[0:3] + sample_tuple[5:]) # Prints concatenated tuple

sample_tuple[0] = 'b'                        # will generate error
del sample_tuple[0]                          # same, not possible

print(len(sample_tuple))                     # 6 elements
```

## Dictionary
Dictionaries hold pairs of key -> value type. Keys are usually numbers or strings (or [other types, with restrictions](https://wiki.python.org/moin/DictionaryKeys)) and values can be literally anything.
```python

my_dict = {'a': 2, 'b': 6}
my_dict.clear()              # clear all pairs

my_dict['a'] = 2
my_dict['one'] = "asdf"
my_dict[2] = "abcd"
my_dict[223] = [1, 2, 3, 4]

print(my_dict['one'])       # Prints value for 'one' key
print(my_dict[2])           # Prints value for 2 key
print(my_dict)              # Prints complete dictionary
print(my_dict.keys())       # Prints all the keys
print(my_dict.values())     # Prints all the values
print(my_dict[123])         # Generates error

print(len(my_dict))
print('a' in my_dict)        # True

another_dict = {'b': 3}
my_dict.update(another_dict)
print('b' in my_dict)        # True
```

## Practice
In a file called 02.py:

1. Create a variable and give it a value.  
Print your variable.  
Create 2 variables on the same line.

2. Create a list of animal names.  
Print the first element of the list.  
Print the last element of the list.  
Add a new animal to the list.  
Using slices, print the elements from 2 to 5.  
Using slices, print the elements from 2 to the end of the list.

3. Print a list containing all the square numbers between 0 and 100 (inclusive)

4. Create a dictionary that represents how much money people have in the bank:  
Alice has 100.  
Bob has 10.  
Trudy has 0.  
Print the amount of money Bob has by using the dictionary.  
Update Trudy's balance.  
Add a new person to the bank's ledger

## Homework

Use a dictionary to figure out if assignment in Python is a shallow or deep copy
Create a dictionary having a single key value pair {'a' : 1} and assign it to a variable named `original`. 
Create a new variable called `copy` and assign `original` to it.  
Using the `original` variable, change the value assigned to `'a'`.  
Print the `copy` dictionary. 
If the value has changed, Python does (super)shallow copies of dictionaries. If it has not, Python does deep copies.
 ([More info on copying objects in python](https://realpython.com/copying-python-objects/))

Do the same exercise, but with a number instead of a dict.