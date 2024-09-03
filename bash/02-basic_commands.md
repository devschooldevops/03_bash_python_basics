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
total 48K
drwx------  8 root root 4.0K Sep  3 10:22 .
drwxr-xr-x 19 root root 4.0K Aug  2 07:17 ..
-rw-------  1 root root   20 Nov 13  2022 .bash_history
-rw-r--r--  1 root root 3.2K Aug  2 07:17 .bashrc
-rw-r--r--  1 root root  161 Dec  5  2019 .profile
drwx------  2 root root 4.0K Aug  2 07:15 .ssh
-rw-r--r--  1 root root  109 Aug  2 07:17 .vimrc
drwxr-xr-x  2 root root 4.0K Sep  3 10:22 Documents
drwxr-xr-x  2 root root 4.0K Sep  3 10:22 Downloads
drwxr-xr-x  2 root root 4.0K Sep  3 10:22 Pictures

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
- `grep [word-to-search] [filename]`: The grep command searches the given files for lines containing a match to a given pattern list.
  - `cat [file] | grep [keyword]`: Search for lines containing a match to [keyword].

Example:
```bash
$ nano file.txt

Hello, World!
# Ctrl + O to save the file, Ctrl + X to exit and save

$ cat file.txt
Hello, World!

$ less file.txt
```
