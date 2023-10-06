# Lab Report 1 - Remote Access and FileSystem (Week 1)
## Commands
**cd**
* *an example of using the command with no arguments:*
  
```
# Command and output
[user@sahara ~]$ cd
[user@sahara ~]$ pwd
/home
```
1. When the command was run, I was in the home directory.
2. The reason why I got that output is that when I use the command with no arguments, it changes my current working directory to my home directory. It is a convention to help users navigate back to the home directory.
3. The output is not an error.
  
* *an exmaple of using the command with a path to a directory as an argument:*
```
# Command and output
[user@sahara ~]$ cd ~/lecture1
[user@sahara ~/lecture1]$ pwd
/home/lecture1
```
1. When the command was run, I was in the lecture1 directory.
2. The reason why I got that output is that when I use the command with the path to a directory, this changes my current working directory to the corresponding directory.
3. The output is not an error.

*  *an example of using the command with a path to a file as an argument:*
```
# Command and output
[user@sahara ~/lecture1]$ cd messages/Hello.java
bash: cd: messages/Hello.java: No such file or directory
```
1. When the command was run, I was still in the lecture1 directory.
2. The reason why I got that output is that when I use the command with the path to a file, it occurs an error.
3. An error occurs because cd changes the working directory, and it expects the path to a directory, not a file.

**ls**
* *an example of using the command with no arguments:*
```
# Command and output
[user@sahara ~/lecture1]$ cd messages
[user@sahara ~/lecture1/messages]$ ls
en-us.txt  es-mx.txt  ja.txt  zh-cn.txt
```
1. When the command was run, I was in the lecture1 directory.
2. The reason why I got that output is that when I use the command with no argument, it lists the content in the current working directory.
 
 
