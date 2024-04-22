





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


What are Bash Environment Variables

1 year ago
by Adnan_Shabbir
In computing, variable is a term that can be used to assign it any value or to
use the variable dynamically in accomplishing the specific task. For instance,
programmers declare variables by any symbol (alphabetical letters mostly) and
can be used to act as a different value in several programs. Our operating
systems have a list of variables that are used to manipulate the programs or
processes in a computer and are known as environment variables. These variables
reside in every kind of OS and can be handled (create, edit, delete,) as like
other variables in a PC. Like other operating systems, Linux also has
environment variables, and these variables are used in several scripts and
programs within the Linux environment. Contrary to these environment variables,
a variable type named as shell variables also exists in Linux, but they are
active in the current instance of the shell, once the shell environment is
terminated the shell variable is also washed out. In this guide, we will
briefly explain the bash environment variables: Before a deep insight let’s go
through the basics of environment variables:

Basics of Bash Environment variables

This section contains the basic information and operations related to
environment variables and how you can play with these variables:

How to print existing environment variables

All the defined variables are stored inside the operating system, and can be
printed by using one of the following command:
$ env
Or:
$ printenv
If the value of a single/specific variable is required, the following syntax is
used:
$ echo $[VARIABLE]
Additionally, if you want to print the list of available shell variables too
along with environment variables; then use the following command to do so:
$ set
The “printenv” and “env” command have printed the environment variables that
are used to display specific information related to your system; we have listed
the most commonly used environment variables:

Variable  Description
USER:     User that is currently logged in
SHELL:    Path of the user’s shell
EDITOR:   It will display the name of default file editor
LOGNAME:  This env variable will print the name of current user
UID:      The unique identifier of a user
HOSTNAME: The hostname of the user’s device over the network
TEMP:     The directory location of temporary files
PWD:      The current operational directory of the terminal
LANG:     This env variable will show the current language settings
TERM:     The current terminal emulation


How to declare an environment variable

In the earlier part of this writing we have discussed the variable types in
Linux: shell and environment. We must not intermingle both variables; and it is
observed that declaring a environment variable is a tricky process and the
clash can occur with shell/local variables:
You can set a new variable and the syntax to perform such action is written
below:
[VARIABLE]=[variable_value]
Remember that, the above syntax will create a shell variable and once you are
out of shell instance, you cannot use the variable.
So, to create an environment variable, user must follow these steps:
Step 1: Export the shell variable: To declare an environment variables, you
have to open the “.bashrc” file with nano(or you can use any other editor)
editor with the help of following command:
$ sudo nano ~/.bashrc
Once it is opened in editable format, you can declare the environment variable
with the help of export keyword and use the following text at the end of the
file to declare it:
export ENV=“new environment variable”
Step 2: Load the ~/.bashrc file into memory : Even though the export keyword is
used, you must load the ./bashrc file into memory to accommodate the changes
successfully; execute the following command to do so:
$ source ~/.bashrc

How to declare environment variables permanently for all users

To set the environment variable permanently for all users; you have to create a
new “.sh” file in directory “/etc/profile.d” and edit the file with nano
editor: for example, the command mentioned below will create and edit the file
“perm.sh”:
$ sudo nano /etc/profile.d/perm.sh
And write the following line in that file to create a permanent variable:
export PERMANENT=“an env variable for all users”
After making the change, “Ctrl+S” to save the file and also reload the file to
the system:
$ source /etc/profile.d/perm.sh

How to set system wide environment variable

To set an environment variable that is available system wide, you have to
access the file “/etc/environment” and get the edit permission (using nano
editor) of the file and write the following syntax in the lower end of the
file:
VARIABLE_NAME=“VALUE”
You will notice that while declaring this system wide environment variable the
export keyword is not necessary to write before declaring the variable.

How to remove an environment variable

If in case you want to remove the environment variable, you can use the syntax
mentioned below to unset that specific variable:
$ unset [VARIABLE]
However, it is observed that the variables that are stored in configuration
files are removed from the current session of the shell, but they are fetched
again once the system is rebooted; so, for the removal of those variables the
users can remove them from the files manually:

Conclusion

Variables have the key importance in computers whether they are declared as a
local or global variable. The local variables are also known as shell variables
whereas the latter one is known as environment variables. In this article, we
have provided a detailed tutorial of the environment variables; these variables
can be manipulated like other variables, but the manipulations of these
variables are quite tricky and sensitive. This guide would help you get the
basics of environment variables as well as the operations a single environment
variable can perform. The variables can be declared for multiple conditions
(other than general declaration); like declaring it for all users, or the
variable that would be available for the whole system.


About the author


Adnan Shabbir

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
