# Lab 1 Report

## `cd` commands:
```
[user@sahara ~]$ cd
[user@sahara ~]$
```
no output, when running this command the user is in the home directory.
There is no output for running `cd` with no arguments because when running `cd` you are changing the directory you are in.
With being in the home directory and then running `cd`, you are not changing the directory because you are already in the first directory.
Having no output in this case is not an error.

putting you back to the home directory
There is no obvious output, in this case, when running cd with no arguments because when running with no argument cd just puts you back to the home directory.

```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
For `cd` with a directory argument, there is no specific output however, the beginning of the terminal line changes to show you that you are now in the lecture1 directory. When the command was first run, I was in the home directory, and after running I was in the lecture1 directory.
The output is not an error.

```
[user@sahara ~]$ cd Hello.class
bash: cd: Hello.class: No such file or directory
```
I am currently in the home directory. When running `cd` with a file argument, you get an error message back saying that there is no such 
file or directory. Although you may have a file with the name you put, when using `cd`, you are trying to change the directory you
are in so using a file argument will not work.

## `ls` commands:
```
[user@sahara ~]$ ls
**lecture1**
```
I am currently in the home directory. When running `ls` with no arguments your output is the folders that are in the main home directory.
In the home directory, there is only one folder, lecture1, so that is what is printed out. This output is not an error.

```
[user@sahara ~]$ ls lecture1/
Hello.class Hello.java **lecture1** README
```
I am currently in the home directory. When running `ls` with a directory as an argument, your output is the folders and files that reside
in the directory that is your argument. This output is not an error.

```
[user@sahara ~]$ ls Hello.class
ls: cannot access 'Hello.class': No such file or directory
```
write

## `cat` commands:
```
[user@sahara ~]$ cat


