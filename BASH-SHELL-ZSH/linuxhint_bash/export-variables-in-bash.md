





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Export Variables in Bash

2 years ago
by Aqsa_Yasin
Users can access the resources by setting the configurations and other settings
that are integrated based on the input of the user. The environment is where
users can keep track of all these settings, updates, and details to maintain
the overall shell. In this guide, we will walk users through different ways to
export the variables. To export a variable to an environment that has all child
processes inside the shell, an “Export” command is used. By default, all of the
variables that are defined by the users are local and are never exported to any
new process on their creation. We use an export command to export all existing
variables and defined functions within the child process. We will check out in
detail how to export them using an example in the later section of this
tutorial.

Requirements

Following is the list of things that are a must needed before executing the
commands mentioned. Users need to have:
Recommended OS: Linux Mint 20 or Ubuntu 20.04
User account: A user account with sudo rights
Note: In this article, we are using Linux Mint 20 to export variables in bash.
You can implement this article on any Linux distribution as per your desire.
To export the variable in bash, open Terminal from Menu on the bottom left on
the screen in your computer system. Click on the Terminal option. Once the
terminal is opened, you need to provide a variable, let’s call it vech for the
sake of ease. We will then assign it a value for now, i.e., “Bus”. In Linux
Mint, the export built-in automatically exports all values to the environment
of its child processes.
$ vech=Bus
Note: Environmental variables are defined for the current shell. These
variables are further inherited by any child’s shells or processes. They can be
used to pass all relevant information into the process that takes birth in the
shell. Shell variables are contained exclusively inside the shell where they
are defined. They are often used to keep a record of location information like
the current directory in use, etc. Usually, these variables are saved in
capital letters to differentiate them.
The variable is created using the echo command to display it on the console.
Provide the variable name next to it. Then click enter. The screen will display
the value provided to the variable created that was Bus in our case.
$ echo “$vech”
Now, you need to start a new shell instance. For this, type bash on the console
window.
$ bash
Note: To enter the bash, the user must be a sudo user and must have privileges
required to access the shell. Enter the password to proceed. Once done, you
will be entered inside the shell.
$ sudo bash
Now, you need to display back the variable vech’s value with echo. The value in
our case set by us initially was “Bus”, type echo $vech, then click the enter
button.
# echo $vech
For now, as shown in the above image, we will have an empty line in the output.
This is because the vech variable declared by us is not exported into the new
process till now. This is where the export command comes into use to make the
variable known and aware of our child processes. Enter the following example at
your console:
# export backup=”/nas10/mysql”
# echo “Backup dir $backup”
# bash
# echo “Backup dir $backup”
Export is a command used in the bash shell to make use of variables and
functions that are to be passed on further to all child processes. It works by
including a variable in child process environments. This is done by keeping
another environment.

Viewing All Exported Variables on the Shell

To view all of the exported variables on your current shell, we generally use
the -p. To execute this flag, we will be using it along with the export
command. This will export all existing variables and functions that are user-
defined within our child process. If there is no variable defined during the
process or no function names are given, we will still use the -p option. This
will return a list of all exported names in the shell. Type the cited command
in the command line.
# export –p
Hit enter. A list of data will be displayed containing all printed exported
names, as shown in the figure below:
Please note here that the system environment variables are now being passed to
all new processes as displayed above. Similarly, users can remove environment
variables. So, to unset these environment variables, use the appended command.
Type, and then hit enter.
# export –n
All set variables will no longer be an environmental variable. However, they
will still be shell variables.
Note: You can also add and set the environmental variables permanently as well.
These variables will be set for all Global Environment Variables and can be
used by all Users. For that, you need to create a file and add a system-wide
environment variable and then initialize this variable. Further, you will be
required to place your sh script with all of your exported variables.

Conclusion

In this way, the variables can be exported to child processes of the shell.
Users can check how export commands can be run. Variables can be included in
any of the child process environments without causing any effect on other
existing environments. The shell running session and related information, i.e.,
our environment, is an important part of the Linux bash. Users can simply set
variables at any of the current environment and reuse them again. By default,
bash also has some environment variables. Playing around with the variables and
setting them based on usability and requirements can be done easily using the
terminal in Linux.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
View_all_posts

RELATED LINUX HINT POSTS


* What_are_Double_Parentheses_in_Bash
* Floating_Point_Math_in_Bash
* Bash_Continue_Built-In_Statement
* 10_Most_Important_Things_to_Know_About_Bash_Scripting
* Mastering_Backticks_in_Linux_Bash_Scripts
* Making_a_Bash_Script_Return_with_Different_Return_Codes_on_Exit
* Greater_Than_Numerical_Comparison_in_a_Bash_Script

Linux Hint LLC, [email protected]hint.com
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
