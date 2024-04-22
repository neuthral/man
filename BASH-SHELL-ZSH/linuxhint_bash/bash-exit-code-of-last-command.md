





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Exit Code of Last Command

2 years ago
by Sidratul_Muntaha
When a bash command is executed, it leaves behind the exit code, irrespective
of successful or unsuccessful execution. Examining the exit code can offer
useful insight into the behavior of the last-run command.
In this guide, check out how to check bash exit code of the last command and
some possible usages of it.

Bash Exit Code

Every UNIX/Linux command executed by the shell script or user leaves an exit
status. It’s an integer number that remains unchanged unless the next command
is run. If the exit code is 0, then the command was successful. If the exit
code is non-zero (1-255), then it signifies an error.
There are many potential usages of the bash exit code. The most obvious one is,
of course, to verify whether the last command is executed properly, especially
if the command doesn’t generate any output.
In the case of bash, the exit code of the previous command is accessible using
the shell variable “$?”.

Checking Bash Exit Code

Launch a terminal, and run any command.
$ date
Check the value of the shell variable “$?” for the exit code.
$ echo $?
As the “date” command ran successfully, the exit code is 0. What would happen
if there was an error?
Let’s try running a command that doesn’t exist.
$ abcd
Check the exit code.
$ echo $?
It’s a non-zero value, indicating that the previous command didn’t execute
properly.
Now, have a look at the following command:
$ cat sample.txt | grep “coin”
When working with a command that has one or more pipes, the exit code will be
of the last code executed in the pipe. In this case, it’s the grep command.
As the grep command was successful, it will be 0.
$ echo $?
In this example, if the grep command fails, then the exit code will be non-
zero.
$ cat sample.txt | grep “abcd”
$ echo $?

Incorporating Exit Code in Scripts

The exit code can also be used for scripting. One simple way to use it is by
assigning it to a shell variable and working with it. Here’s a sample shell
script that uses the exit code as a condition to print specific output.
$ #!/bin/bash
$ echo "hello world"
$ status=$?
$ [ $status -eq 0 ] && echo "command successful" || echo "command unsuccessful"
When being run, the script will generate the following output.
Now, let’s see what happens when there’s an invalid command to run.
$ #!/bin/bash
$ random-command
$ status=$?
$ [ $status -eq 0 ] && echo "command successful" || echo "command unsuccessful"
When being run, the output will be different.

Exit Code Value Explanation

When the exit code is non-zero, the value ranges from 1 to 255. Now, what does
this value mean?
While the value is limited, the explanation of each value is unique to the
program/script. For example, “ls” and “grep” has different explanations for
error code 1 and 2.
$ man ls
$ man grep

Defining Exit Status in Script

When writing a script, we can define custom exit code values. It’s a useful
method for easier debugging. In bash scripts, it’s the “exit” command followed
by the exit code value.
$ exit <value>
Per the convention, it’s recommended to assign exit code 0 for successful
execution and use the rest (1-255) for possible errors. When reaching the exit
command, the shell script execution will be terminated, so be careful of its
placement.
Have a look at the following shell script. Here, if the condition is met, the
script will terminate with the exit code 0. If the condition isn’t met, then
the exit code will be 1.
$ #!/bin/bash
$ if [[ "$(whoami)" != root ]]; then
$   echo "Not root user."
$   exit 1
$ fi
$ echo "root user"
$ exit 0
Verify the result of running this script without sudo privilege or “root” user.
$ ./sample.sh
$ echo $?

Final Thoughts

This guide demonstrates what exit codes are and how you can use them. It also
demonstrates how to assign appropriate exit codes in a bash script.
Interested in bash scripting? One of the easiest ways to get started is by
writing your own scripts. Check out this simple guide on how_to_write_a_simple
bash_script.
Happy computing!


About the author


Sidratul Muntaha

Student of CSE. I love Linux and playing with tech and gadgets. I use both
Ubuntu and Linux Mint.
View_all_posts

RELATED LINUX HINT POSTS


* What_are_Double_Parentheses_in_Bash
* Floating_Point_Math_in_Bash
* Bash_Continue_Built-In_Statement
* 10_Most_Important_Things_to_Know_About_Bash_Scripting
* Mastering_Backticks_in_Linux_Bash_Scripts
* Making_a_Bash_Script_Return_with_Different_Return_Codes_on_Exit
* Greater_Than_Numerical_Comparison_in_a_Bash_Script

Linux Hint LLC, [email protected]
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
