# Introduction

## What is Python?

Python is a high-level, interpreted, multi paradigm, general purpose, dynamically typed programming language.
- High level -> you're not forced to work with pointers / bits / machine code
- Interpreted -> source code is run line by line by an interpreter
- Multi paradigm -> supports multiple programming styles (_imperative_, object oriented, functional)
- General purpose -> Turing complete
- Dynamically typed -> Types are known only at run time; there's no static type checking (by default)

## Things you should know about python
- usually when you say python, you mean python3. Python2 is still around, but we won't be diving into it today.
- where other languages use curly braces `{}` for scopes, python uses whitespace. Make sure you are consistent when using tabs or spaces and that the tabwidwh is always the same.
- there are no `;` in python scripts
- python is generally a very readable language.
- python has some design guidelines that render code pythonic or unpythonic. Try typing `import this` into a repl to see what they're about

[The python style guide](https://peps.python.org/pep-0008/)

## Setup

```bash
$ python3 --version
$ pip3 --version

```

If you get errors on the above steps, install Python with your package manager of choice or download from the site or compile from source etc...

```bash
$ sudo apt install python3 python3-pip
# or
$ sudo yum install python3, python3-pip
#
...
```

## Test it out

```bash
$ python3
>>> from datetime import date
>>> print(date.today())
2024-09-03
# (Ctr + D or exit() to quit)
>>> exit()

```

Or run it as a script:

Create a file called script.py with the following content:

```python
from datetime import date

print(date.today())

```

And run it like so:

```bash
$ python3 script.py
```

## Try out pip
We'll need the `requests` module later, so let's try to install it now
```bash
$ pip3 install requests
```
If that fails, or you get errors, you may need to add some flags. Ask your trainer for guidance.

## Text editor

You'll also need a text editor. VSCode with the Python extension works great.
If you have a copilot, it would be recommended to disable it for this lab.

