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

$ cat << Endoftext
>this is a
>multiline 
>text string 
>Endoftext
this is a 
multiline 
text string 

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

### Bash built-in and other commands
* Many of the programs we use in Bash are commands.
  * separate software that does not depend on Bash 
* Bash includes built-in commands as well
  * Part of bash itself 
* Some Bash built-ins have the same name as other commands
builtin take precedence on command 
````
$ echo Heloo there 
Hello there 
$ printf hello
hello$

$ command echo hello
hello

$ builtin echo hello
hello

$ command -V name_of_program 
will tell us if the program is builtin or command 

$ enable -n name_of_builtin
to disable specific builtin in session 

$ enable name_of_builtin
to re-enable the builtin again 

````

--------------
### Brackets and Braces in Bash 
![braces](sql-assets/bracesplus.png)

### Bash expansions and substitutes 
Expansions and substitutes allows us to specify values that are not known until a script runs.

|Representations | Name |
|---|---|
|~ | Tilde expansion |
|{...} |Brace expansion |
|${...} | Parameter expansion |
|$(...) |Command substitution |
|$((...)) |Arithmetic expansion |

### Tilde expansion ~ 
Tilde expansion represents the user's $HOME environment variable.
````
$ echo ~
/home/username

$ echo ~-
presents the dircetory you were just in 
````

### Brace expansion
* Brace expansion creates sets or ranges. 
* This is written with braces around an expansion.
* Lets us substitute an item from a list of values separated by commas or range of numbers or letters in a given pattern, separated by two dots or periods.
* used when we need to keep part of a path the same but replace a little piece of it.
  * e.g. if we want to create a file inside each of three different directory trees where only part where only part of a path need to change each time.
  * could be used to provide a set of values to use in the same part of a string more generally.
* used working with sequential items .
````
$ echo {1..10}
1 2 3 4 5 6 7 8 9 10

sidradev@Mac-5 java101 % echo {10..1}
10 9 8 7 6 5 4 3 2 1

$ echo {01..100}
001 002 003 004 005 006 007 008 009 010 011 012 013 014 015 016 017 018 019 020 021 022 023 024 025 026 027 028 029 030 031 032 033 034 035 036 037 038 039 040 041 042 043 044 045 046 047 048 049 050 051 052 053 054 055 056 057 058 059 060 061 062 063 064 065 066 067 068 069 070 071 072 073 074 075 076 077 078 079 080 081 082 083 084 085 086 087 088 089 090 091 092 093 094 095 096 097 098 099 100
(number 1 to 100 padded with 0)

$ echo {a..z}
a b c d e f g h i j k l m n o p q r s t u v w x y z

$ echo {Z..A}
Z Y X W V U T S R Q P O N M L K J I H G F E D C B A

$ echo {1..30..3}
1 4 7 10 13 16 19 22 25 28
(every third number between 1 and 30 )

$ echo {a..z..2}
a c e g i k m o q s u w y
(return every other letter between a and z)

$ touch file_{01..12}{a..d}
(create 48 file with sequential name )

 % touch {01..05}{a..c}
 % ls
01a		02c		04b		Bash-101.md	sql-assets
01b		03a		04c		Linux-101.md	sql-learning.md
01c		03b		05a		README.md
02a		03c		05b		learning-vim
02b		04a		05c		scripts


````
------------------
### Parameter expansions ${...}
Parameter expansion retrieve and transforms stored values.
* Sometime can be used without brackets 
* Used to extract sub-strings or manipulating the value of parameter as its being used.
* to replace a particular word or value
* 
````

$ greating="hello there"
$ echo $greating
hello there 

$ echo ${greating:6}
there
(print greating starting from 6th character)

$ echo ${greating:6:3}
the
(print greating starting from 6th character for 3 characters)

% echo ${greating/there/everybody}
hello everybody

 % echo ${greating//e/_}
h_llo th_r_

 % echo ${greating/e/_}
h_llo there
````

-------------------
### Command and substitutions $(...)
* Command substitution puts the output of one command inside another.
* Older representation : `...`
* Bash run the specified command in a subshell and return the output of that into the current command.
* Often used with string manipulation tools to extract part of command's output, such as a file size, an IP address or so on that needed to be handed back to the parent command.

````
 % uname -r
20.6.0

 % echo "the kernel is $(uname -r)."
the kernel is 20.6.0.

 % echo "the python is $(python -V)."
the python is Python 3.9.12.
````

--------------
### Arithmetic expansion $((...))
* Arithmetic expression does calculation.
* Older representation: $[...]
* Bash can use arithmetic expansion to perform arithmetic or calculations and use the result in a command. 

````
$ echo $((2 + 2))
4

$ echo $(( 4 - 4))
2

$ echo $((4 * 5))
20

$ echo $(( 4 / 5 ))
0

````

--------
### Bash Scripts syntax

**One-liners :**
* Many commands presented in one line of text
* Often piped commands or command separated by semicolon.
* Can be very long( and even warp), but there's on newline until the end.
* Often stored in a note for frequent use.

**Bash script :**
* Text file that contains a series of commands
* Bash myscript.sh

**Executable Bash script :**
* Includes a shebang as the first line (#!/usr/bin/env bash)
* 









|Command | Description  |
|---|---|
|bash --version |Shows us which version of bash is installed |
|echo $SHELL | TO check the default shell |
|command -V name_of_program |will tell us if the program is builtin or command |
|enable -n name_of_builtin|to disable specific builtin in session |
|enable name_of_builtin |to re-enable the builtin again |
|help |list of all built-in |
|help name_of_builtin |for info for that built-in |
|echo ~- |old pwd |