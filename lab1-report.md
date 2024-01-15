# Lab 1 Report

## `cd` commands:
```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$
```
There is no obvious output when running `cd` with no arguments because when running with no argument you are just put back into the home directory. By starting in the lecture1 directory and then running `cd`, you are changing your directory back into the home directory. this output is not an error.

```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
For `cd` with a directory argument, there is no specific output however, the beginning of the terminal line changes to show you that you are now in the lecture1 directory. When the command was first run, I was in the home directory, and after running I was in the lecture1 directory. The output is not an error.

```
[user@sahara ~]$ cd Hello.class
bash: cd: Hello.class: No such file or directory
```
I am currently in the home directory. When running `cd` with a file argument, you get an error message back saying that there is no such file or directory. Although you may have a file with the name you put when using `cd`, you are trying to change the directory you are in so using a file argument will not work.

## `ls` commands:
```
[user@sahara ~]$ ls
lecture1
```
I am currently in the home directory. When running `ls` with no arguments your output is the folders that are in the directory you are currently in. In this case, in the home directory, there is only one folder, lecture1, so that is what is printed out. This output is not an error.

```
[user@sahara ~]$ ls lecture1/
Hello.class Hello.java messages README
```
I am currently in the home directory. When running `ls` with a directory as an argument, the output is the folders and files that reside in the directory that is your argument. This output is not an error.

```
[user@sahara ~/lecture1]$ ls README
README
```
I am currently in the lecture1 directory. When running `ls` with a file as an argument, the output is just the file name that is your inputted argument. This output is not an error.

## `cat` commands:
```
[user@sahara ~]$ cat
hi
hi
```
I am currently in the home directory. When the `cat` command is run with no arguments, it reads from standard input. For example, in the code block above, the user typed "hi" so the `cat` command printed out the same thing. This goes on until the user hard stops the command. This output is not an error.

```
[user@sahara ~]$ cat lecture1/
cat: lecture1/: Is a directory
```
I am currently in the home directory. When running `cat` with a directory as the argument, the output is an error message stating that the argument is a directory. This output is an error because the `cat` command is used to read the contents of a specified file, or files, not a directory.

```
[user@sahara ~/lecture1]$ cat README
To use this program:

javac Hello.java
java Hello messages/en-us.txt
```
I am currently in the lecture1 directory. When running `cat` with a file argument, the output is the contents inside the file. If you were to have multiple file arguments, the output would be the contents inside each of the files printed one after another. This output is not an error.

