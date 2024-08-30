## **Shell and Scripting Features**

### **1. Bash Command Interpreter and Its Features**

#### **1.1 Usage and Working Modes**
The Linux/Unix command interpreter (the shell) acts as the interface between the user and the operating system's kernel. It processes command lines received from the user, identifies commands and arguments, and then executes the command with the appropriate options and arguments.

Besides executing commands, the shell offers various features aimed at both making command-line work easier and transforming the shell into a programming environment. These features include:

- **Autocomplete**: Automatically completing command or argument names when pressing the TAB key.
- **Redirections**: Redirecting the output or errors of a command to a file or another command.
- **History**: Keeping a list of executed commands that the user can review and reuse.
- **Aliases**: Defining new commands based on existing ones.
- **Job Control**: Running multiple commands in parallel within a single shell.
- **Variables**: Memory areas that store information and are referenced by name. Variables can set default options for commands or store data processed by shell programs.

#### **1.2 History**
The shell automatically memorizes the user's commands as they are entered. This list of commands is saved in a file designated by the `HISTFILE` variable (default: `~/.bash_history`). The size of this file can be limited by setting the `HISTFILESIZE` and `HISTSIZE` variables.

#### **1.3 Aliases**
An alias is a new command created by assigning a new name to an existing command or a sequence of commands. Aliases are created with the `alias` command and can be deleted with `unalias`. Aliases exist only for the duration of the shell session unless defined in a shell initialization script.
To make an alias permanent, add it to your `~/.bashrc` or `~/.bash_profile`.

**Example:**
```bash
alias ll='ls -alh'
alias alias hey='echo "How are you doing"'
```
This alias allows the user to start Firefox by simply typing `f`.

#### **1.4 Variables**

##### **1.4.1 Generalities and Usage**
A variable represents a memory area where data is stored, accessible by a name. Variables are used in Linux/Unix command lines to store data that commands or scripts can use.

##### **1.4.2 Defining and Modifying Variables**
A variable is defined by assigning it a value:
```bash
HELLO="Hello, World!"
```
Variables are case-sensitive, meaning `VAR` and `Var` are different. When a variable's value consists of multiple words, it should be enclosed in quotes.

##### **1.4.3 Reading Variable Values**
To read the value stored in a variable, prefix its name with `$`:
```bash
echo $HELLO
```

##### **1.4.4 Displaying and Deleting Variables**
Use the `set` command to display all defined variables and their values. 
To delete a variable, use the `unset` command:
```bash
bash$ set
BASH=/bin/bash
BASH_ARGC=()
BASH_ARGV=()
BASH_COMPLETION=/etc/bash_completion
[...]
bash$ unset HELLO
bash$ echo $HELLO
```

##### **1.4.5 Examples of Useful Variables**
- **PS1**: Determines the command prompt appearance.
- **PATH**: Defines the directories where the shell looks for executables.

##### **1.4.6 Variable Scope**
Variables are only visible within the shell in which they are defined. To make a variable available to child processes, it must be exported:
```bash
export HI="What is up doc"
```

#### **1.5 Shell Initialization Files**

##### **1.5.1 Description and Usage**
Shell initialization files are predefined files that the shell automatically executes at startup. They typically define variables, aliases, and functions for the user.

##### **1.5.2 Initialization Files Based on Shell Type**
Different initialization files are executed depending on whether the shell is interactive or non-interactive, login or non-login. For example:
- **Interactive Login Shell**: Executes `/etc/profile` and the first found among `~/.bash_profile`, `~/.bash_login`, `~/.profile`.
- **Non-Login Interactive Shell**: Executes `~/.bashrc`.
- **Non-Interactive Shell**: Executes the file specified by the `BASH_ENV` variable, if it exists.

### **2. Shell Scripting**

#### **2.1 General Information**
A script (similar to a batch file in Windows) is a text file containing commands that the shell can execute. Once written and saved, a script can be reused.

#### **2.2 Writing and Saving the Script**
A script is a plain text file and can be written with any text editor. It does not require a specific file extension, though `.sh` is commonly used.

#### **2.3 Adding Execution Permission**
To execute a script, the user must have read and execute permissions on the file:
```bash
chmod u+rx script_name.sh
```

#### **2.4 Executing the Script**
A script can be executed in several ways:
- **Using the file path**:
  ```bash
  ./script_name.sh
  ```
- **Using `source`**:
  ```bash
  source script_name.sh
  ```
  This runs the script in the current shell, making any variables defined in the script available in the calling shell.

#### **2.5 Basic Elements of a Script**

##### **2.5.1 Comments**
Comments begin with `#` and are ignored by the interpreter.

##### **2.5.2 Specifying the Interpreter**
The first line of a script can specify the interpreter using `#!` (shebang), e.g., `#!/bin/bash`. This tells the system which interpreter to use to run the script.

##### **2.5.3 Common Commands**
- **`echo`**: Used to display a string of characters or the value of variables.
- **`exit`**: Terminates the script and returns a status code.

#### **2.6 General Syntax in Shell Scripts**
Commands do not need to end with a semicolon unless multiple commands are placed on the same line. To split a command across multiple lines, use the backslash (`\`).

### **3. Control Structures**

#### **3.1 Decision-Making Instructions**

##### **3.1.1 Simple `if` Instruction**
The `if` statement evaluates a condition and executes code based on whether the condition is true or false.
```bash
if [ condition ]; then
  # commands
fi
```

##### **3.1.2 `case` Instruction**
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

#### **3.2 Loop Instructions**

##### **3.2.1 `while` and `until` Loops**
The `while` loop executes commands as long as a condition is true, whereas the `until` loop runs until a condition becomes true.

##### **3.2.2 `for` Loop**
The `for` loop iterates over a list of items, executing commands for each item.
```bash
for item in list; do
  # commands
done
```

##### **3.2.3 `break` and `continue`**
- **`break`** exits the loop immediately.
- **`continue`** skips the rest of the current loop iteration and continues with the next iteration.

#### **3.3 User Input**
The `read` command is used to take input from the user:
```bash
read variable_name
```
Options include `-p` for a prompt string and `-t` for a timeout.

### **Bibliography**
- [Bash Reference Manual](https://www.gnu.org/software/bash/manual/)
- [Shell Scripting Tutorial](https://www.shellscript.sh/)