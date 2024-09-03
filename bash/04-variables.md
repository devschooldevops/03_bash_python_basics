# Bash Variables

## What are Variables?

Variables in Bash allow you to store and manipulate data within your scripts and commands.
A variable represents a memory area where data is stored, accessible by a name. 
Variables are used in Linux/Unix command lines to store data that commands or scripts can use.

### Creating Variables

A variable is defined by assigning it a value:
```bash
$ VAR=value
```
Variables are case-sensitive, meaning `VAR` and `Var` are different. When a variable's value consists of multiple words, it should be enclosed in quotes.


### Accessing Variables

To read the value stored in a variable, prefix its name with `$`:
```bash
$ echo $VAR
```

### Example
```bash
name="Razvan"
echo "Hello, $name!"
```

## Environment Variables
Environment variables are special variables that influence the behavior of your shell and system processes.

### Common Environment Variables

- **`HOME`**: The path to the current user's home directory.
- **`PATH`**: Defines the directories where the shell looks for executables.
- **`USER`**: The name of the current user.
- **`PS1`**: Determines the command prompt appearance (stands for Prompt Shell 1)

### Viewing Environment Variables
```bash
$ echo "Your home directory is: $HOME"
$ echo "Your username is: $USER"
```
The **`PS1`** variable can be configured (create the prompt at https://ezprompt.net):
```bash
$ export PS1="\[\e[33;40m\]\A\[\e[m\]|\[\e[31;40m\]\u\[\e[m\]@\[\e[36m\]\s\[\e[m\][\[\e[35m\]\w\[\e[m\]]\\$ "
```

### Displaying and Deleting Variables

Use the `set` command to display all defined variables and their values. 
```bash
$ set
BASH=/bin/bash
BASH_ALIASES=()
BASH_ARGC=([0]="0")
BASH_ARGV=()
BASH_CMDS=()
[...]
```
To delete a variable, use the `unset` command:
```bash
$ unset VAR
$ echo $VAR
$
```

## Using Variables in Scripts

Variables can be used to store user input, command output, or any other data needed within a script.

```bash
$ nano hello.sh

#!/bin/bash
name="Alice"
echo "Hello, $name!"
```


## Summary
Understanding how to create and manipulate variables in Bash is essential for storing and using data within your commands and scripts.
