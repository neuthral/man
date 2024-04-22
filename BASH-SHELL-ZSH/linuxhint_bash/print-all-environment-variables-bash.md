





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Print all Environment Variables

1 year ago
by Omar_Farooq
Environment variables are a collection of dynamic specified values kept inside
the machine that has been utilized by programs running in terminals or
subshells in Ubuntu and Linux platforms. The environment variable, in basic
terms, is an attribute with a title and a value. Environment variables involve
changing the way a system functions as well as the behavior of the device’s
programs. The environment variable can hold data such as the regular word
processor or search engine, the route to executable documents, the machine
locale, and keypad layout preferences, among other things.

Set Environment Variable Value

You need to understand that the environment variables are initialized the same
as the other variables in a programming language are initialized, i.e., bash
variables. Although, the title of an environment variable is always case-
sensitive, i.e., it must be uppercase. More than two values can be assigned to
an environment variable using the colon “:”.
Here is a simple general syntax of initializing an environment variable. The
set built-in command has been widely known to set the values of environment
variables. If you use it without any argument or any set flag, it will make
your shell display all the environment variables, as you can see from the image
below. The common examples of “set” built-in are “set –x” to expand and
display, “set –e” to quit the program upon encountering any non-zero status,
“set –u” and “set –o” to display an error when it founds a variable with no set
value, “set –n” to avoid executing the commands and many more.

* KEY=value
* KEY=value1:value2

$ set

Print All Environment Variables Using Env

Let’s start using different commands in the shell to print the environment
variables. Before that, launch your console application using the “Ctrl+Alt+T”
on the Ubuntu 20.04 desktop. The very first method to display all the
environment variables is using the “env” command in the shell. But, it will
only display the currently active environment variables of the system.
You can also pass some arguments in it to modify the output. We have used the
simple “env” command to display all the current environment variables in our
shell as per the output shown.
$ env

Print All Environment Variables Using printenv

Let’s see another example to print all the environment variables in the shell.
This time we have been using the “printenv” command in the shell to do so. The
“printenv” command displays the currently active environment variables and the
previously specified environment variables in the shell.
You can see the output of using the “printenv” command to display all the
environment variables in the shell as per the snapshot below. We have got a lot
of environment variables along with their assigned values, i.e., shell
variables, display variables, authentication variables, and a lot more, as
demonstrated from the image.
$ printenv
You can also use the same command with the keywords “more” and “less”. More
commands will be helpful when you want to see more when needed. While the less
command will automatically show fewer environment variables on your shell
screen to avoid inconvenience. The commands for more and less display are
stated as follows:
$ printenv | more
The more clear view for the output of the “more” command of printing
environment variables is shown in the image below. Tap the “Enter” key to
explore more variables.
The printenv command is very handy when it comes to transferring its variable
data into other files. This means we can also transfer all the environment
variables and their values to some bash file using the “printenv” command. You
have to use the greater than sign after the “printenv” keyword along with the
name of a file where the data of variables will be stored.
After doing this, you can see that the file will have all the environment
variables. The output is the same for displaying the content of a file using
the “cat” command and the “printenv” command in the shell.
$ printenv > new.sh
$ cat new.sh
On the other hand, you can also use the arguments within the “printenv” command
to make it specific. Let’s say, if you want to check the values for the
environment variable “HOME” in the shell, you have to mention it in the
“printenv” command with the “grep” keyword. If the variable named “HOME” exists
in the system, it will display it on the shell. As you can see, it displayed
the “HOME” variable and its value, i.e., path in the shell.
$ printenv | grep HOME
Let’s check for some other environment variables. Let say check for the folder
“tmp” using the “grep” keyword. The folder “tmp” belongs to the variable
“SESSION_MANAGER” in our system.
$ printenv | grep tmp
Now, let’s check about the “bin” folder that is widely used in the system. Upon
running the command, we have got 4 environment variables in return, showing
that it is a part of all those environment variables of the Ubuntu 20.04
system.
$ printenv | grep bin
To check for the variable that doesn’t even exist in your system leads to an
empty result. As the system has no environment variable for a folder or file
“new”.
$ printenv | grep new
You can also use another command to display all the variables found in your
system, i.e., not only the environment variables. The declare command can be
used for this purpose along with the “-p” flag within the query.
$ declare -p
If you only want to display the environment variables in your shell, you can
also do that by declaring a command. You have to declare the “-xp” flag instead
of the “-p” flag, as shown in the image. You can have a look at the output that
displays only the environment variables.
$ declare -xp

Conclusion

This guide has been designed for all the bash users of the Linux system despite
their learning capability. This is because all the examples implemented within
this article are very simple and well-explained to make it understandable for
every type of user.


About the author


Omar Farooq

Hello Readers, I am Omar and I have been writing technical articles from last
decade. You can check out my writing pieces.
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
