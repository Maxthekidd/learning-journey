# Basic Commands & Directory Hierarchy

### bash - bourne again shell
 - the enhanced version of the Bourne shell that is used by Linux.
- It runs commands, which can be:
  1. Other programs.
  2. Its own built-in features.
  3. It also serves as a small programming environment.

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

the ls command can be used to list the contents of multiple directories simultaneously.
e.g - $ ls /usr/bin ~
 this would list both the contents of the bin directory inside the usr directory and the user's main directory.

## Manipulating Files and Directories
Commands
 - cp - Copy files & directories
 - mv - move files & directories
 - rm - remove files & directories
 - ln - create hard & symboliic links
 - mkdir - create new directory
 - rmdir remove directory

## Standard Input & Output
Unix processes use Input/Output streams to read and write data. Processes read data from input streams and write data to output streams.
standard input - stin
standard output - stdout
standard error - stderror

The avenues of utility for this honestly suprised me, it can be used to split data streams (e.g seperating standard output from standard error).

Typing commands into the shell is a good example of the shell acting as an input stream, recieving confirmation that the command has been executed successfully from the shell is a good example of the shell behaving as an output stream. Receiving an error messege however (command failed) is not a standard output, it is a standard error.

$ echo $? can be used to enquire on the status of your previous command
- 0 - command executed successfully
- 1 - command failed

The existence of a third data stream (standard error - stderr) as a seperate stream from standard output did surprise me.

When splitting data streams, all three data streams have corresponding integers.
- 0 - Standard output
- 1 - Standard input (implied)
- 2 - Standard error

$ find /etc -type f 1> ~/result.txt 2> ~/error.txt (splits the data streams and sends standard input to the result.txt file in the home directory and the standard error to the error.txt file in the same directory.

rmdir - command fails if the directory in question is empty, however you can use recursive delete ($ rm -r dir), very dangerous command especially if executed with root privileges e.g sudo, be very careful!

## Shell Globbing
This is when the shell matches simple patterns to file and directory names

- * - an example of a globbing character, it matches any number of arbitrary characters
    - $ echo * - matches everything
    - $ echo *at - matches everything ending with 'at' - cat, bat, sat.
    - $ echo at* - matches everything beginning with 'at'  - atleast, attribute, athletle.
    - $ echo *at* - matches everything containing 'at' - palate, atleast, cat, attribute, bat, athlete, sat.
    - 
- ? - another prominent globbing character, this one matches exactly one arbitrary character
    - $ echo b?at - matches boat and brat.
    - 
If you do not want the shell to expand a character into a glob, enclose it in single quotes '*' - '?'

NOTE: The shell peforms expansion before running the command

# Intermediate Commands

## grep
prints the lines from a file or input stream that match an expression
$ grep root directory1/file1
- prints out all the lines in file1 that contain the expression 'root'

Options
- -i - case sensitive matches
- -v - Invert (shows non-matches)
