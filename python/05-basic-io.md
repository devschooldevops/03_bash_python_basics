# Basic IO operations

## Working with stdin, stdout, stderr

Reading from stdin is as simple as using the `input` function.

```python
x = input()
print(x)
```

Do take note that `input()` will give you back a string. If you're looking for a number, you can use `int(input())`. This can, however, throw an error. We'll learn how to deal with those in the python automation course.  
`input()` can also take a string argument which will be printed before waiting for user input.

```python
x = int(input("Please enter a number:"))
print(x)
```

We've been writing to `stdout` all this time. It's simply the `print` function.
To write to `stderr`, you'll first need to import `sys` to have access to the file, then pass `sys.stderr` to the print function:

```python
import sys

print("Missing ; on line 3", file=sys.stderr)

```

## Command line args

To get the command line args, it's as simple as accessing `sys.argv`. It's a list of strings having the entire command line used to run the script. The first element in `argv` is always the script name.

```python
import sys

print(sys.argv)
```

Try putting the above lines in a script.py file and run the file with some arguments.
```bash
$ python3 script.py arg1 arg2 arg3
```

## Opening files

Command line is cool, but you can't get thousands or millions of lines of data that way.
Files are better suited for this task.

This is the classical way to open a file in read mode(more info on file modes [here](https://docs.python.org/3/library/functions.html#open)):
```python
f = open("file.txt", "r")
# do stuff with the file
f.close()
```

And here is the more `pythonic` way of doing the same thing:
```python
with open("file.txt", "r") as f:
    # do stuff with the file
# when you tab back, the file is automatically closed
```

Using this syntax, you no longer have to remember to close the file, which is convenient.

### Reading from a file

Here's a piece of code to read the entire content of a file:
```python
with open("file.txt") as f: # if absent, the mode is 'r' by default
    content = f.read()
    print(content)
```

A little bit more useful is the function that reads all lines of a file and returns a list:

```python
with open("file.txt") as f:
    lines = f.readlines()
    print(lines)
```

In the loops lesson, we'll learn an even better way to work with the lines of a file.

### Writing to a file

The file object also has a `write()` method that can be called (successfully) if the file was opened in write mode:
```python
with open("file.txt", "w") as f:
    f.write("Hello, World!")
```
Note: the actual writing to the file is usually done when f.close() is called. That's why the `with` syntax is so useful here.


## Practice
Write a 05.py with the following behaviour:

You take two file names from arvg (in_file and out_file; create the 2 files in bash and put a greeting in the in_file).  
You ask for a name from stdin.  
You read the content of the in_file.  
You concatenate the name from stdin to the content of in_file and write the resulting string to the out_file.  