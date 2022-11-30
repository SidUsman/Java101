## Linux Command Line

-----------------
### Introduction 
Linux broadly refers to a free, open source operating system.
just another name for kernel. A kernel allows software to communicate with a computer's hardware.
Linux was inspired by MINIX which was inspired by Unix. Linux is free software under the GPL(GNU General Public License).

### Linux Tools and Distributions
* All linux system run a version of the Linux kernel.
* Most Linux systems use the same set of core tools called the GNU coreutils.
* Linux distributions are operating systems that include the kernel and various other pieces of software.
* Distribution maintainer make choices about how their distributions are configured and what tools they provide.
  
    **Common Distribution Families:**
  Many distributions are related to each other and all distributions differ in various ways.
  The command line or shell is common to all of them.(Bash shell is used widely) 
  * Arch 
  * Debian 
  * Red Hat 
  * Slackware

### What is Command Line?
The command line interpreter or Command-line processor uses a command-line interface(CLI) to receive commands from a user in the form of lines of text.

Command-line also called Windows command-line, command screen or text-interface that navigate by typing commands at prompts instead of using a mouse.
command-line programs can read text inputs and output text to the screen.
command-line programs can read and write from files and network.

### What is Bash?
Bash is a widely used shell or command-line interpreter.

**Using a terminal:**
We use a shell like bash through a terminal application either in full screen mode or as windows in a graphical environment.
we can use graphical and text base interface at the same time and even open more than one terminal window at the same time to perform different tasks.

### Terminal terms:
* Command-line interface(CLI) is any place we can enter text commands.
* A shell is a piece of software that interprets typed commands and runs them.
* Terminal is software that a shell program runs inside of.

### General Command Syntax:
In writing commands
* There will always be a command.
* There may be one or more options.
    Option may accept arguments.
* There may be one or more arguments.

````
Example:

ls -lh /usr/bin
sort -u user.text
grep -i "needle" haystack

In which there are three parts 
command    option(s)   argument(s)
ls          -lh         /usr/bin
sort        -u          user.tex
grep        -i"needle"  haystack

````
### Commands 
* Commands are programs that are available on a system.
* When we run a command, the system takes a specific action.
* many commands have short names in order to save typing.e.g ls,du,cat.

### Options 
* Options tell a command how to operate.
* Options often begin with a dash or minus sign e.g. -e  or -s .
* Options are often represented by one letter or number.
* Most commands offer more than one option.
* Options can be used together. e.g. 
```` 
ls -l 
ls -l -a -h 
ls -l -a 
ls -lhl
ls --group-drirectories-first --human-readable

````

### Arguments 
* Arguments tell the command what to operate on.
* it is usually a file, path, set of files or directories separated by spaces.
* An argument can also be a string of text or something else.
````
sort -u user.text
````


|Command	|Usage |
|---|---|
|ls	|Lists the content of a directory|
|alias	|Define or display aliases|
|unalias|	Remove alias definitions|
|pwd	|Prints the working directory|
|cd	|Changes directory|
|cp	|Copies files and directories|
|rm	|Remove files and directories|
|mv	|Moves (renames) files and directories|
|mkdir	|Creates directories|
|man	|Displays manual page of other commands|
|touch	|Creates empty files
|chmod	|Changes file permissions|
|./	|Runs an executable|
|exit|	Exits the current shell session|
|sudo|	Executes commands as superuser|
|shutdown	|Shutdowns your machine|
|htop	|Displays processes and resources information|
|unzip|	Extracts compressed ZIP files|
|apt, yum, pacman	|Package managers|
|echo	|Displays lines of text|
|cat	|Prints file contents|
|ps	|Reports shell processes status|
|kill	|Terminates programs|
|ping	|Tests network connectivity|
|vim|	Efficient text editing|
|history	|Shows a list of previous commands|
|passwd	|Changes user password|
|which	|Returns the full binary path of a program|
|shred	|Overwrites a file to hide its contents|
|less|	Inspects files interactively|
|tail	|Displays last lines of a file|
|head	|Displays first lines of a file|
|grep	|Prints lines that match patterns|
|whoami|	Outputs username|
|whatis|	Shows single-line descriptions|
|wc	|Word count files|
|uname	|Displays OS information|
|neofetch	|Displays OS and hardware information|
|find	|Searches for files that follow a pattern|
|wget	|Retrieves files from the internet|


