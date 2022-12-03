# Learning Bash Scripting
### What is bash?
Bash is a shell, a program lets us interact with a computer giving us access to programs, hardware resources and files stored on the system.
Bourne again shell
* Bash is widely used shell, available on many platforms.
* Short for bourne Again Shell, in interference to the earlier Bourne shell.
* An interactive command-line shell that also allows commands to be combined into script files which can be run like programs.
* Combining commands into scripts saves time and reduces errors.
------------------
### What is bash for?
* Bash is best for writing small to medium size scripts that run on Linux systems.
* If your work flow can be run as commands in bash terminal consider making a script.
* If your workflow requires other more specialized tools Bash may not be the best choice for automation.

-----------------
### Where to run Bash ?
Bash is primarily used on Linux system but is available on macOS and Windows system.

Using a Linux system, virtual machine or cloud instance is recommended to learn Bash.

The included version of Bash on macOS is extremely outdated and may be removed in the future.

To run Bash on Windows use GitBash or WSL or Linux VM .

-----------------
### Pipes and Redirection
* **Pipes** send output of one process to another.
* Pipes is very often used with grep, awk, cut and sed command.
````
$ ls | wc -l


$ cat text.txt | less
break output into pagess

$ cat text.txt | wc
    45   1856  12678
count the number of line in this file 

````
* **Redirections** send streams(standard input, output and error) to or from files.
* represented with > or < sign .

|Symbol |Function |
|---|---|
|> | output redirection (turncate ) <br> take whatever redirected and overwrite the contents of destination file  |
|>> |Output redirection (append ) <br> add to the end of the existing file |
|< |Input redirection |
|<< |Here document <br>Allows you to pass multiple lines if input to a command.|
````
$ ls > list.txt 

````
|Stream |Name |Content |
|---|---|---|
|0 |Standard input (stdin) |Keyboard or other input |
|1 |Standard output (stdout ) |Regular output |
|2 |Standard error (stderr) |Output marked as 'error' |

---------------------

### what is bash scripting
#### simple bash script
[Hello World in bash](scripts/first-script.sh)



|Command | Description  |
|---|---|
|bash --version |Shows us which version of bash is installed |
|echo $SHELL | TO check the default shell |
|
