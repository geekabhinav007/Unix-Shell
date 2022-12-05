# The Unix Shell

The Unix shell has been around longer than most of its users have been alive. It has survived because it’s a powerful tool that allows users to perform complex and powerful tasks, often with just a few keystrokes or lines of code. It helps users automate repetitive tasks and easily combine smaller tasks into larger, more powerful workflows.

Use of the shell is fundamental to a wide range of advanced computing tasks, including high-performance computing. These lessons will introduce you to this powerful tool.

## Introducing the Shell and Navigating Files and Directories
 
```bash	
$ ls
```
ls : list Command ==> List  information  about  the FILEs in Current Directory.

```bash
$ pwd
```
pwd : current working directory (Present working directory).

```bash
$ man [Command Name]
```
man cammand is use for manual displaying of any command.

```bash
$ cd
```
1. cd : Change the shell working directory.
1. cd . : stands for the current directory.
1. cd / : stands for the root directory.
1. cd ../.. : this command goes up two levels.
1. cd ~ : stands for the user’s home directory.
1. cd : shortcut to go back to the user’s home directory.
1. cd .. : goes up one level.


- The file system is responsible for managing information on the disk.

- Information is stored in files, which are stored in directories (folders).

- Directories can also store other directories, which then form a directory tree.

- `pwd` prints the user’s current working directory.

- `ls [path]` prints a listing of a specific file or directory; `ls` on its own lists the current working directory.

- `cd [path]` changes the current working directory.

- Most commands take options that begin with a single `-`.

- Directory names in a path are separated with `/` on Unix, but `\` on Windows.

- `/` on its own is the root directory of the whole file system.

- An absolute path specifies a location from the root of the file system.

- A relative path specifies a location starting from the current location.

- `.` on its own means ‘the current directory’; `..` means ‘the directory above the current one’.

![pic for General Syntax](https://swcarpentry.github.io/shell-novice/fig/shell_command_syntax.svg) 
```bash
$ mkdir [File Name]
```
mkdir : Create the DIRECTORY(ies), if they do not already exist.

```bash
$ touch my_file.txt
```
touch : The touch command generates a new file called my_file.txt in your current directlsory. You can observe this newly generated file by typing ls at the command line prompt. my_file.txt can also be viewed in your GUI file explorer.

```bash
cp [OPTION] Source Destination
cp shell.md /home/geek/Documents

```

cp : “cp” command is used to copy files and directories. It requires at least two arguments.

```bash

$ mv [Option] source destination
$ mv shell.md /home/geek/Document

```

mv : “mv” command is used to move or rename files and directories. It also requires at least two arguments.

```bash
$ rm -i shell.md
rm: remove regular file 'shell.md'? 
```
rm -i : The -i option will prompt before (every) removal (use Y to confirm deletion or N to keep the file). The Unix shell doesn’t have a trash bin, so all the files removed will disappear forever. By using the -i option, we have the chance to check that we are deleting only the files that we want to remove.






