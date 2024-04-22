





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Set Environment Variables in Linux

3 years ago
by Nitesh_Kumar
Setting environment variables in Linux is a good way to define common and
repetitive variables that are used across a number of applications and terminal
commands. These environment variables help in cutting down verbosity, bring
ease of use, and make development workflow better.
An environment variable in Linux can be used to pass information or influence
the behavior of an application or a process. This article will explain various
ways to set environment variables and how to use them.
To set an environment variable for the shell currently in use, define a
variable in the following format:
$ MYVAR=”xyz”
The definition is self explanatory, “MYVAR” is the variable name while “xyz” is
its value. Running the command below will verify if the environment variable
has been set correctly:
$ echo $MYVAR
Notice the syntax of environment variables. While they work like any other
shell variables, it is generally a good practice to use capital letters and
underscores for left hand side (variable name).
To unset a variable, use the command below:
$ unset MYVAR
If you check the variable again using the echo command mentioned above, no
output will be displayed. Note that unset will work for current terminal
session only. If there are any global, system wide environment variables
defined on your system, they will be available again in a new terminal session.
To set an environment variable for the shell currently in use and also for any
child processes / shells launched from it, use a variable in the following
format:
$ export MYVAR=”xyz”
To permanently set an environment variable for bash shells (most default
terminal apps in Linux distributions are configured for bash shell), add the
variable (with “export” keyword) at the end of the hidden .bashrc file in your
home directory.
export MYVAR=”xyz”
You can edit .bashrc file by running the command below:
$ subl ~/.bashrc
Replace “subl” with the command of your favorite text editor. You will need to
reload .bashrc file to enable the changes. Run the command below to do so:
$ source ~/.bashrc
Below is an example of custom environment variables I have set for Ruby Gems.
You can view all environment variables enabled on your system by running the
command below:
$ env
To specifically check if the custom environment variable added to .bashrc file
has been enabled or not, run the command below:
$ env | grep MYVAR=
To set an environment variable system wide for all apps, shells and processes,
add your custom variable in “/etc/environment” file without “export” keyword.
MYVAR=”xyz”
You can edit “/etc/environment” file by running the command below:
$ sudo subl “/etc/environment”
Replace “subl” with your favorite text editor. You may need to reboot the
system for the changes to take effect. To verify if your custom variable has
been set correctly, run the command below:
$ env | grep MYVAR=
Alternatively, you can use “printenv” command to verify the changes:
$ printenv MYVAR
Note that the “unset” command explained above works for all custom environment
variables, whether they are session specific or global variables. However,
unset removes a variable for the running shell session only and it won’t remove
any system wide or global variable permanently.
Some of the predefined environment variables in Ubuntu include:

* USER – name of the logged-in user
* HOME – home directory of logged in user (usually /home/username)
* DISPLAY – active monitor in use (usually automatically set by login manager)
* PWD – working directory where the shell is being used or invoked
* SHELL – shell that is being used system wide (usually /bin/bash)
* LANG – language used by the system (user defined, can be changed)
* PATH – scripts / binaries / executables are searched in the directories set
  in the PATH variable

Some of the environment variables that are commonly used to influence
application behavior:

* LC_ALL – force overrides user defined locale with the value specified in the
  variable
* LD_LIBRARY_PATH – used to define additional directories where runtime
  libraries will be searched
* PATH – used to define additional directories where scripts / binaries /
  executables will be searched
* LD_PRELOAD – used to load custom / downgraded / upgraded libraries in an
  application

This marks the end of this article. Environment variables in Linux helps in
running tweaked commands and applications without actually modifying underlying
source and binaries by providing a way to define and use global variables
across the system.


About the author


Nitesh Kumar

I am a freelancer software developer and content writer who loves Linux, open
source software and the free software community.
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
