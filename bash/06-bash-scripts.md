# Bash Scripts

## What is a Bash Script?

A Bash script is a file containing a series of commands that are executed in sequence by the Bash shell. Scripts can automate tasks, simplify complex operations, and enhance productivity.

### Creating a Script
1. Open a text editor (e.g., `nano`, `vim`, or any IDE).
2. Write your script.
3. Save the file with a `.sh` extension.


## Example Scripts
### Hello script
A simple Bash script to greet the user
```bash
#!/bin/bash
echo "Enter your name:"
read name
echo "Hello, $name! Welcome to Bash scripting."
```

### Making the Script Executable
Before running a script, you need to make it executable:

```bash
chmod +x script_name.sh
```

### Running the Script
To execute the script, use:

```bash
./script_name.sh
```
## Script Structure

A typical Bash script includes:

1. **Shebang**: **`#!`** (`#!/bin/bash`) - Indicates the script should be run using Bash.
2. **Comments**: Lines starting with `#` are comments.
3. **Commands**: The core actions the script performs.



## Even more examples:

### Backup Script
This script creates a backup of a directory.

```bash
#!/bin/bash
# Backup script

SOURCE_DIR="/home/user/Documents"
BACKUP_DIR="/home/user/Backup"
DATE=$(date +%Y-%m-%d)

if [ ! -d "$BACKUP_DIR" ]; then
  mkdir -p "$BACKUP_DIR"
fi

tar -czf "$BACKUP_DIR/backup-$DATE.tar.gz" "$SOURCE_DIR"

echo "Backup of $SOURCE_DIR completed!"
```


### System Information Script
This script displays basic system information, such as the username, the machine's hostname, and the current date.

```bash
#!/bin/bash
# System Information Script

echo "Username: $USER"
echo "Hostname: $(hostname)"
echo "Date: $(date)"
echo "Uptime: $(uptime -p)"
echo "Kernel Version: $(uname -r)"
```

#### Explanation
- `$(hostname)`: Gets the hostname of the machine.
- `$(date)`: Prints the current date and time.
- `$(uptime -p)`: Shows how long the system has been running in a human-readable format.
- `$(uname -r)`: Displays the kernel version of the operating system.