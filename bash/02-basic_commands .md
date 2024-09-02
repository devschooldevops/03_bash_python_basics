# Basic Bash Commands

## Navigating Directories
- `pwd`: Print working directory.
- `ls`: List files and directories 
  - `-l`:use a long listing format
  - `-a, --all`: show hidden files and entries starting with .
  - `-h, --human-readable`: with -l, print sizes in human readable format (ex. 1024K, 256M, 2G)

- `cd [directory]`: Change directory.
  - `cd ~`

Example:
```bash
$ pwd
/home/user

$ ls
Documents  Downloads  Pictures

$ ls -lah
Documents  Downloads  Pictures

$ cd Documents
$ pwd
/home/user/Documents
```

## Manipulating Files
- `touch [file]`: Create an empty file.
- `mkdir [directory]`: Create a new directory.
- `cp [source] [destination]`: Copy a file or directory.
- `mv [source] [destination]`: Move or rename a file or directory.
- `rm [file]`: Remove a file.

Example:
```bash
$ touch file.txt
$ mkdir new_folder
$ cp file.txt new_folder/
$ mv new_folder/file.txt file2.txt
$ rm file2.txt
```

## Viewing and Editing Files
- `cat [file]`: Display the content of a file.
- `nano [file]`: Edit a file using the Nano text editor.
- `less [file]`: View the content of a file page by page.

Example:
```bash
$ cat file.txt
Hello, World!

$ nano file.txt
# (edit and save the file)

$ less file.txt
```