# OPERATING SYSTEM CS-2006
# PROJECT TITLE:
## Unix Shell

## SUBMITTED TO:
Sir Farooq

## GROUP MEMBERS:
21k-3076
21k-4717
21k-4723

# INTRODUCTION:
Unix shell, command line interpreter that provides CLI, command line interpreter to control and perform execution of system. A shell in a Linux operating system takes input from you in the form of commands, processes it, and then gives an output. Terminal enables users to let control and decide upon particular execution. Unix shell is a powerful tool allowing users to perform complex tasks. Unix shell enables users to perform wide range of advanced computing. Unix operating systems have built in terminal to write commands. In this project we will be build a shell implementing commands with CLI.  

# METHODOLOGY:
Objective of doing this project is to get familiar how the CLI of Linux based operating system works, how shell understands commands converts them to executable instructions and gives output and, how processes are created and destroyed. 
The methodology for building a shell is that, it runs in a while loop repeatedly asking for commands which is called interactive mode which will be read through getline function and then CommandProcess function which process that command. Starting of shell creates a parent process that will remain active until the shell is closed. After validating path, a fork() system call is made through which a child process is created. After the creation of child process, it is where you can execute the entire command. A function call of execv(), responsible for receiving parameters which will be executed in the child process, that confirms successful execution with another system call exit(), with a value of zero. When execution of the execv() is finished, the child process will be terminated with another system call wait(), which is responsible for the successful completion of the child process before returning to the parent process.
We have also implemented parallel commands. Unix shell also enables commands combining which enables users to enter more than one command using some operators. We have implemented concept of parallel commands using (&&) operator as it enables succession of second command only if first command is successful. Commands are splitting through split function which uses some delimiters to identify from where to separate the command. If it is not a parallel command then it will execute only one command but if more than one command is given it will separate the entire line through split function and execute simultaneously.
Unix shell has also a feature of redirection commands. Redirection commands enables to change standard input and standard output. We have implemented output redirection using (>) operator which will let the user to save the output into a file instead of displaying it on terminal unless asked explicitly.
We have also defined some built-in commands like help, exit, cd. There are many built-in and system commands in Unix which is executed directly without creation on child process.
We have displayed some appropriate error messages if user enters wrong commands and if trying to have built-in commands.

# ScreenShot
<img scr="ss1.jpeg">
<img scr="ss2.jpeg">

# REFERENCES:
•	https://brennan.io/2015/01/16/write-a-shell-in-c/
•	https://www.geeksforgeeks.org/making-linux-shell-c/
•	https://www.youtube.com/watch?v=z4LEuxMGGs8
•	https://linuxgazette.net/111/ramankutty.html
