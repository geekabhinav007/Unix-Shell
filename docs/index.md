[Regular Expresssion](regex.md) | [SDE](sde.md) | [AWK](awk.md)

# The Unix Shell

The Unix shell has been around longer than most of its users have been alive. It has survived because it’s a powerful tool that allows users to perform complex and powerful tasks, often with just a few keystrokes or lines of code. It helps users automate repetitive tasks and easily combine smaller tasks into larger, more powerful workflows.

Use of the shell is fundamental to a wide range of advanced computing tasks, including high-performance computing. These lessons will introduce you to this powerful tool.

## Introducing the Shell and Navigating Files and Directories
 
```bash	
$ ls
```
`ls` : list Command ==> List  information  about  the FILEs in Current Directory.

```bash
$ pwd
```
`pwd` : current working directory (Present working directory).

```bash
$ man [Command Name]
```
`man` cammand is use for manual displaying of any command.

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
`mkdir` : Create the DIRECTORY(ies), if they do not already exist.

```bash
$ touch my_file.txt
```
`touch` : touch is used to change file timestamps. Update the access and modification times of each FILE to the current time.

```bash
$ cp [OPTION] Source Destination
$ cp shell.md /home/geek/Documents
```

- `cp` : `cp` command is used to copy files and directories. It requires at least two arguments.
- while copying a Folder/directory we should use `-r` flag so that evey folders and file are recursevily copied to the new destination.
- Copy with Multiple directory and files to abc folder.

```bash
$ cp -r 1/2 sub1/subsub1 abc/
```

```bash
$ mv [Option] source destination
$ mv shell.md /home/geek/Document
```

- `mv` : `mv` command is used to move or rename files and directories. It also requires at least two arguments.
- We can rename files and folders by `cp` and `mv` commands.

```bash
$ rm -i shell.md
rm: remove regular file 'shell.md'? 
```
- `rm -i` : The `-i` option will prompt before (every) removal (use Y to confirm deletion or N to keep the file). The Unix shell doesn’t have a trash bin, so all the files removed will disappear forever. By using the -i option, we have the chance to check that we are deleting only the files that we want to remove.

## Working With Files and Directories

### want to create a subdirectory in a single command?
```bash
$ mkdir -p sub1/subsub1 sub2/subsub1/subsubsub1 sub2/subsub2
```
- we can create file using many editors some of them are:
	- nano
	- vi (visual editor)
	- gedit
	- vim (visual editor improved)
	- Notepad e.t.c

- `-i` flag use for interactiveness use `-i` flag if you are doing some essential things such as deleting.

### Using wildcards for accessing multiple files at once

1. `*` :- It is a wildcard, which matches zero or more characters.
1. `?` : It is also a wildcard, but it matches exactly one character.


### points:

- `cp [old] [new]` copies a file.

- `mkdir [path]` creates a new directory.

- `mv [old] [new]` moves (renames) a file or directory.

- `rm [path]` removes (deletes) a file.

- `*` matches zero or more characters in a filename, so `*.txt` matches all files ending in `.txt`.

- ? matches any single character in a filename, so `?.txt` matches `a.txt` but not `any.txt`.

- The shell does not have a trash bin: once something is deleted, it’s really gone.

- Most files’ names are `something.extension`. The extension isn’t required, and doesn’t guarantee anything, but is normally used to indicate the type of data in the file.

- Depending on the type of work you do, you may need a more powerful text editor than Nano.

## Pipes and Filters

`wc` - `wc` is the ‘word count’ command: it counts the number of lines, words, and characters in files (from left to right, in that order).

```bash
geek@g3:~/test$ wc test.txt 
 12 103 596 test.txt
 
geek@g3:~/test$ wc *.txt
  4  12  48 test2.txt
 12 103 596 test.txt
 16 115 644 total
```
- We can use following flag with `wc` command to display words, characters. and line specificly.
	- `-m` for characters.
	- `-l` for lines.
	- `-w` for words.

```bash
geek@g3:~/test$ wc -m *.txt
 48 test2.txt
588 test.txt
636 total

geek@g3:~/test$ wc -l *.txt
  4 test2.txt
 12 test.txt
 16 total
 
geek@g3:~/test$ wc -w *.txt
 12 test2.txt
103 test.txt
115 total
```

### Capturing output from commands

- `>` is used to redirect file output.
- `wc -l *.txt > lengths.txt` this command will right all the output to the file name `lengths.txt` instead of printing on the screeen.
- if `length.txt` exit it is overwritten.
- if we had a 6000 file with name `.txt` then `cat` command will display data in very bad manner so use `less` command.
- `cat` has the disadvantage that it always dumps the whole file onto your screen. More useful in practice is the command `less`, which you use with `less lengths.txt`. This displays a screenful of the file, and then stops. You can go forward one screenful by pressing the spacebar, or back one by pressing b. Press q to quit.

- `sort` vs `sort -n` 
- We will also use the `-n` option to specify that the sort is numerical instead of alphanumerical. 
- `head -n 2 length.txt` will display first 2 line of file `length.txt`.
- similrly `tail -n 2 length.txt` will display lst 2 line of file `length.txt`.

```bash
geek@g3:~/test$ head sorted.txt 
  0 length.txt
  0 test3.txt
 12 test2.txt
103 test.txt
115 total

geek@g3:~/test$ head -n 2 sorted.txt   
0 length.txt
0 test3.txt
  
geek@g3:~/test$ tail -n 2 sorted.txt 
103 test.txt
115 total
```
- `>` and `>>` are different in manner of overwriting.

```bash
geek@g3:~/test$ echo I am abhi > test01.txt
geek@g3:~/test$ echo I am abhi > test01.txt

geek@g3:~/test$ echo I am abhi >> test02.txt
geek@g3:~/test$ echo I am abhi >> test02.txt

geek@g3:~/test$ cat test01.txt 
I am abhi

geek@g3:~/test$ cat test02.txt 
I am abhi
I am abhi
geek@g3:~/test$ 
```
### Passing output to another command

- The vertical bar, |, between the two commands is called a pipe. It tells the shell that we want to use the output of the command on the left as the input to the command on the right.

```bash
geek@g3:~/test$ cat length.txt 
  0 length.txt
 12 test2.txt
  0 test3.txt
103 test.txt
115 total

geek@g3:~/test$ sort -n length.txt | head -n 2
  0 length.txt
  0 test3.txt
```
```bash
geek@g3:~/test$ wc *.txt > data_unsort.txt | sort -n data.txt | head -n 4
  0   0   0 data.txt
  0   0   0 test3.txt
  1   1   6 testfile.txt
  1   3  10 test01.txt
  
geek@g3:~/test$ wc *.txt | sort -n | head -n 4
   0    0    0 test3.txt
   1    1    6 testfile.txt
   1    3   10 test01.txt
   2    6   20 test02.txt
```

![redirection and pipes](https://swcarpentry.github.io/shell-novice/fig/redirects-and-pipes.svg)


1. `wc` counts lines, words, and characters in its inputs.

1. `cat` displays the contents of its inputs.

1. `sort` sorts its inputs.

1. `head` displays the first 10 lines of its input.

1. `tail` displays the last 10 lines of its input.

1. `command > [file]` redirects a command’s output to a file (overwriting any existing content).

1. `command >> [file]` appends a command’s output to a file.

1. `[first] | [second]` is a pipeline: the output of the first command is used as the input to the second.

1. The best way to use the shell is to use pipes to combine simple single-purpose programs (filters).

```bash
geek@g3:~/test$ cat data.csv 
2012-11-05,deer,5
2012-11-05,rabbit,22
2012-11-05,raccoon,7
2012-11-06,rabbit,19
2012-11-06,deer,2
2012-11-06,fox,4
2012-11-07,rabbit,16
2012-11-07,bear,1

geek@g3:~/test$ cut -d , -f 2 data.csv
deer
rabbit
raccoon
rabbit
deer
fox
rabbit
bear
```

1. `cut` command and its use `-d` is used for delimeter where as `,` is delimeter and -f option to specify that we want to extract the second field (column).

1. use of `uniq` command.
1. The `uniq` command has a `-c` option which gives a count of the number of times a line occurs in its input.

```bash
geek@g3:~/test$ cut -d, -f 2 data.csv 
deer
rabbit
raccoon
rabbit
deer
fox
rabbit
bear

geek@g3:~/test$ cut -d, -f 2 data.csv | sort
bear
deer
deer
fox
rabbit
rabbit

geek@g3:~/test$ cut -d, -f 2 data.csv | sort | uniq -c
      1 bear
      2 deer
      1 fox
      3 rabbit
      1 raccoon
      
geek@g3:~/test$ cut -d, -f 2 data.csv | sort | uniq -c | wc -l
5
```
## Loops

### Syntax of loop in bash.

```bash
for thing in list_of_things
do
    operation_using $thing    # Indentation within the loop is not required, but aids legibility
done
```
example:

```bash
geek@g3:~/test$ for filename in test01.txt test2.txt test.txt test3.txt 
> do
> head -n 2 $filename
> done
I am abhi
 vdnv d
 adv dav
- `rm [path]` removes (deletes) a file.
```

1. A `for` loop repeats commands once for every thing in a list.

1. Every `for` loop needs a variable to refer to the thing it is currently operating on.

1. Use `$name` to expand a variable (i.e., get its value). `${name}` can also be used.

1. Do not use spaces, quotes, or wildcard characters such as ‘*’ or ‘?’ in filenames, as it complicates variable expansion.

1. Give files consistent names that are easy to match with wildcard patterns to make it easy to select them for looping.

1. Use the up-arrow key to scroll up through previous commands to edit and repeat them.

1. Use `Ctrl+R` to search through the previously entered commands.

1. Use `history` to display recent commands, and `![number]` to repeat a command by number.

## Shell Script and Finding things.

- Save commands in files (usually called shell scripts) for re-use.

- `bash [filename]` runs the commands saved in a file.

```bash
geek@g3:~/test$ grep abhi test02.txt 
I am abhi
I am abhi

geek@g3:~/test$ grep deer data.csv 
2012-11-05,deer,5
2012-11-06,deer,2

$grep -w "The" data.csv
```
- `-w` flg is used to limit matches to word boundaries.
- `-n` flag used to print line number along with line.
- use the option `-i` to make our search case-insensitive:

```bash
geek@g3:~/test$  grep -n "it" grepTest.txt
5:With searching comes loss
9:Yesterday it worked
10:Today it is not working

geek@g3:~/test$ grep -nw "it" grepTest.txt 
9:Yesterday it worked
10:Today it is not working
```
```bash
geek@g3:~/test$ grep -nwi "the" grepTest.txt 
1:The Tao that is seen
2:Is not the true Tao, until
6:and the presence of absence:

geek@g3:~/test$ grep -nw "the" grepTest.txt 
2:Is not the true Tao, until
6:and the presence of absence:
```
- we want to use the option `-v` to invert our search.
- If we use the `-r` (recursive) option, grep can search for a pattern recursively through a set of files in subdirectories.
```bash
geek@g3:~/test$ grep -r abhi
test01.txt:I am abhi
test02.txt:I am abhi
test02.txt:I am abhi
test2.txt:I am abhinav
```
- `grep --help`
- `grep` real power comes with wildcard not with option.
- `The technical name for these is regular expressions, which is what the ‘re’ in ‘grep’ stands for.`
```bash
geek@g3:~/test$ wc -m $(find -name "*.txt")
 560 ./data.txt
  18 ./testfile01.txt
 588 ./test.txt
 218 ./grepTest.txt
  66 ./length.txt
   0 ./test3.txt
  10 ./test01.txt
  20 ./test02.txt
   6 ./testfile.txt
 312 ./data_unsort.txt
  48 ./test2.txt
  66 ./sorted.txt
1912 total
```
# THANK YOU
# Question from Seminar?
- what is Unix
- what is shell
- Gnu and Unix 
- Gnu Linux operating 
- What is freecad
- What is difference between `-` ans `--` before flag?
- what is the actual used of `touch` command?
- Does -M in wc count space
- `>` And `>>` operator 
- More and less difference 
- Use of sort with uniq

[Regular Expresssion](regex.md) | [SDE](sde.md) | [AWK](awk.md)

