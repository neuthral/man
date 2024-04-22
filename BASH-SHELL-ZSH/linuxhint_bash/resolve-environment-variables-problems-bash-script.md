





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Resolve Problems with Environment Variables Not Being Set in a Bash
Script

1 year ago
by Zeeman_Memon
Environment variables are used to modify the behavior of an environment. These
variables can change how software or application works. Setting up environment
variables has multiple applications in bash. Such variables can be used to
store anything.
Moreover, every system has certain environment variables that it uses while
interacting with the user. In this article, we will first look at the basics of
bash scripts and set up and manipulate environment variables and then go
through some remedies for the associated problems.

Bash Scripts

In Ubuntu, nearly every task can be executed using either the Graphical User
Interface or the Command Line Shell. Some tasks are more easily done using the
shell rather than the GUI. Scripts are files that consist of commands. All of
these commands are executed when the script file is executed. Bash scripts are
such scripts that use the Bash interpreter.
The extension of the scripts is .sh. Scripts can be written using any text
editor. Each bash script starts with the line #!/bin/bash, which tells the
system to use the bash interpreter.

Environment Variables

Environment variables have the properties of process locality, inheritance, and
case sensitivity. Process locality means that the environment variables are
exclusive to the specific instance of the shell unless specified otherwise.
Inheritance refers to the parent-child relationship between various
environments.
Case sensitivity, as the name implies, means that the environment variables are
sensitive to case changes. Generally, the format of environment variables is
dependent on its parent system. However, all of the environment variables have
two features in common; variable name and stored value.
The variable name can be anything, but the value must be in the format
compliant with the environment variable type. This is especially important when
dealing with the environment variables created by the system. For example, the
environment variable LANG is responsible for selecting the language that the
application uses to communicate with the user. Its value is location-dependent,
but typically in the US, it will have the value “en_US.UTF-8”.

Manipulating Environment Variables

There exist several graphical utilities for looking, setting up, and editing
environment variables, but in this article, we will be looking at how to deal
with such variables in the bash command line.
To create a new environment variable, you can use the export command. There are
multiple ways to create an environment variable. You can define the variable
first and then export it. We will create the variable named EDITOR with the
value nano (text editor) and then export it.
$ EDITOR=nano

$ export EDITOR
The other way of creating the environment variables is by defining them in the
export command itself.
$ export EDITOR=nano
If you intend to use spaces in the value, you need to use double quotations
while creating the environment variable as shown:
$ export VAR= “my value”
The values of the environment variables can be accessed by using the echo
command followed by the name of the respective variable with a dollar sign.
$ echo $VAR
You can also use the printenv command to get the value of any environment
variable.
$ printenv VAR

Issues related to environment variables

While defining environment variables in bash scripts, the common issues are
related to the parent-child relation of shells. The solution to such issues is
to define the variables in a parent environment. As we saw earlier, typically,
the environment variables are temporary and exclusive to the shell instance in
which they are created; however, we can also define environment variables that
are persistent and available to other users.
If you want to create an environment variable that is permanent for your use
only, you will have to edit the .bashrc file. It is located in the /home/user
directory. You can add a VAR environment variable in the .bashrc file by
executing the following commands:
$ nano /home/user/.bashrc
Now, we use the nano text editor to modify the contents of the bash file.
export VAR="My permanent variable"
To apply the changes to your current session, source the .bashrc file by using
the following command:
$ source .bashrc
The variable VAR will be available for every instance of the shell run by the
current user.
However, if you are looking to create an environment variable that is available
for all the users, you will have to include it in the /etc/environment file.
For example, we can add a GLOBAL environment variable to the /etc/environment
file by executing the following commands:
$ nano /etc/environment
As we did before with the .bashrc file, we now edit the contents of the
environment file.
export GLOBAL="This is a global variable."
Source the environment file to apply the changes by typing the following
command:
$ source /etc/environment
If you want to create an environment variable that stores the result of a
command executed in a bash script, you will have to use parameter substitution.
The general format of parameter substitution involves usage of the export
command followed by the command with a dollar sign enclosed in brackets as
shown:
$ export VAR = $ (<bash command>)
For example, if you want to store your SHELL environment variable in another
variable MYSHELL, you can use the following command:
$ export MYSHELL = $(echo $SHELL)

Conclusion

In this article, we have gone through the basics of bash scripts and
environment variables. Moreover, we have understood how to manipulate the
environment variables, some typical issues related to creating such variables
in bash scripts, and how to remedy them.


About the author


Zeeman Memon

Hi there! I'm a Software Engineer who loves to write about tech. You can reach
out to me on LinkedIn.
View_all_posts

RELATED LINUX HINT POSTS


* 10_Cool_and_Awesome_Bash_Loop_Examples
* What_are_Double_Parentheses_in_Bash
* Floating_Point_Math_in_Bash
* Bash_Continue_Built-In_Statement
* 10_Most_Important_Things_to_Know_About_Bash_Scripting
* Mastering_Backticks_in_Linux_Bash_Scripts
* Making_a_Bash_Script_Return_with_Different_Return_Codes_on_Exit

Linux Hint LLC, [email protected]
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
