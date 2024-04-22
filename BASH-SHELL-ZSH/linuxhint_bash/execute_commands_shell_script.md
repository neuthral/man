





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Execute Commands from Within a Shell Script

2 months ago
by Denis_Kariuki
“Working with shell script is something any Linux user should be at home with.
However, how you learn to execute commands plays a big role in your
understanding and working with shell scripts. This guide explains all details
about executing commands within a shell script. We will cover everything from
creating a shell script to defining variables to executing the shell script.
Let’s get started!”

Executing Commands From a Shell Script

The shell is an interpreter that allows users to work and interact with the
Linux system. The shell works as a command-line interpreter, taking inputs and
giving output. A shell script can contain loops, functions, variables, and
commands. The best thing with shell scripts is how they make automating tasks
easy. Let’s get into the details of executing commands in a shell script.

Creating a Shell Script

A shell script has the .shextension, and you can create a shell script using an
editor, provided you save the file using the .sh extension. In this case, we
will create a linuxhint.shscript using the nano editor.
$ sudo nano linuxhint.sh
Once the file opens, the line below is the first thing you must write for the
system to know that you are working with a shell script.
#!/bin/bash
With your shell script constructed, we can proceed to see how to execute
commands inside the script.

Executing Commands Within a Shell Script

A shell script supports the built-in Linux commands. It works similarly to how
you would execute Linux commands on your terminal. For instance, if you want to
execute commands to get the current date and time and display the logged-in
user, you could use the dateand whocommands by typing them as shown.

Executing a Shell Script

Once you’ve defined the commands you want to execute, save the bash script.
Before you execute the script, we must first make it executable using the
syntax below.
sudo chmod +x filename.sh
Once it is executable, you can execute the script using the syntax below.
bash filename.sh
or
. filename.sh

Working With Variables

Shell scripts allow the creation of user-defined variables to hold the output
of given commands. To hold the command’s output inside a variable, enclose the
command using $().For instance, if we needed to get the current date using the
datecommand and store it in a variable, we could define our variable as shown
below.
mydate=$(date)
Note that there shouldn’t be any spacing between the words in the line.
If you want to create user-defined variables, write the variable name, and the
value should be enclosed in double quotes. For instance, check the variable
below.
greet=" Hello, are you enjoying the tutorial?"
Once the variable is created, you can call it using the $followed by the
variable name. You can then execute the command using the echocommand.
The output would execute as expected based on the commands we added.

Working With Interactive Shell Commands

With a shell script, you can work with commands and variables that interact
with the user through inputs to determine the output. As shown below, we use
the read command to get the user input and echo the output.
Here’s the output

Defining Functions

You can also execute commands through functions in the shell script. A function
can take any number of arguments, and you can create a function to execute any
command. Below is a shell script with a function that creates a folder and five
files inside it.
Here’s the output after executing the script.

Conclusion

Shell scripts are not that challenging to work and create. With a few tricks,
you can easily use different commands in your shell scripts to achieve much
functionality. In this guide, we’ve seen the various ways you can execute
commands within a shell script. Hopefully, you now have a foundation for
creating shell script commands.


About the author


Denis Kariuki

Denis is a Computer Scientist with a passion for Networking and Cyber Security.
I love the terminal, and using Linux is a hobby. I am passionate about sharing
tips and ideas about Linux and computing.
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
