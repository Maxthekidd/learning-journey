# Basic Commands & Directory Hierarchy

### bash - bourne again shell
 - the enhanced version of the Bourne shell that is used by Linux
- It runs commands, which can be
  1. Other programs
  2. Its own built-in features
  3. It also serves as a small programming environment

### Shell scripts
- Text files containing a sequence of shell commands

Elementary commands
 - pwd - to print current working directory.
 - cd (x) - to change directory to the directory of choice.
 - ls - to list the contents of current working directory or any other directory as specified.
 - chsh - change shell
 - cat prints out file contents
 - echo - Basically just returns/echoes the argument.

  Absolute and Relative Pathnames
  - .. - Parent directory
  - . - Currect working directory

 - file - determining the file type
 - less - to view file contents (less = more!)

ASCII format = basically what I have known as txt files, these are pure text files (not really, txt files are a bit more modern and flexible, ASCII files can only contain text -obviously including spaces and line terminators-)

the ls command can be used to list the contents of multiple directories simultaneously
e.g - ls /usr/bin ~
 this would list both the contents of the bin directory inside the usr directory and the user's main directory

## Manipulating Files and Directories
Commands
 - cp - Copy files & directories
 - mv - move files & directories
 - rm - remove files & directories
 - ln - create hard & symboliic links
 - mkdir - create new directory
 - rmdir remove directory

## Standard Input & Output
### What it is
Unix processes use Input/Output streams to read and write data. Processes read data from input streams and write data to output streams.
standard input - stin
standard output - stdout
### Why does it exist
The avenues of utility for this honestly suprised me, it can be used to split data streams (e.g seperating standard output from standard error)
### Examples
Typing commands into the shell is a good example of the shell acting as an input stream, recieving confirmation that the command has been executed successfully from the shell is a good example of the shell behaving as an output stream
### Questions I still have
.
### Things that suprised me
The existence of a third data stream (standard error - stderr) as a seperate stream from standard output
