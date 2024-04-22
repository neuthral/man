





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Print All Environment Variables and Values

1 year ago
by Prateek_Jangid
Your shell compiles multiple types of information while interacting with the
server from the shell session. It provides information about the shell behavior
and its access to the resources. Configuration settings contain some of these
settings, and user input determines others.
In this way, the shell keeps track of all settings and information to maintain
the environment. Shells build an environment each time they start a session
that contains variables that define a system’s properties. So, if you want to
know the methods to bash print all environment variables and values, then read
this blog to get a brief on it.

BashPrint All Environment Variables and Values

By using the commands env or printenv, we can see all of our environment’s
variables. So here is the following command and its output:
printenv
env
Both printenv and env produce similar results. They differ only in how they
carry out certain tasks. When you use printenv, for example, you can see the
values of specific variables using the below command:
printenv PATH
According to what we learned above, child processes usually inherit the
environment variables from parent tasks, allowing you to easily override or add
variables to them.
Printenv displays that several environmental variables have been set without
our input through our system files and processes.
You can use the set command for this. Without any other parameters, typing set
will get us a list of environmental variables, all shell variables, shell
functions, and local variables:
set
Most of the time, this list is very long. So, you can use the following command
for the lesser output:
set | less
It is probably not necessary to learn about all of the Bash functions, for
instance.
To clean up the output, we can specify to operate in POSIX mode, which will not
print shell functions. So that it doesn’t change any current environment, we
can run this in a subshell:
(set -o posix; set)
There are some environmental variables and shell variables that must be listed
here.
The output of these commands will not match the output of env or printenv, so
we cannot obtain only shell variables using these comparisons, but using these
commands will give us a partial list:
comm -23 <(set -o posix; set | sort) <(env | sort)
While this is true, a few environmental variables may still be present since
printenv and env don’t quote strings as they do.
In your session, you will still see the environment variables and shell
variables you set.
There are many uses for these variables. These technologies offer an
alternative to writing changes to files to set persistent session values.

Common Linux Variables

We display values of shell variables in Linux using the printf/echo commands:

System       Commands     Description
Variable
BASH_VERSION BASH_VERSION This variable contains the current version of bash.
HOSTNAME     HOSTNAME     Computer name.
CDPATH       CDPATH       cd command’s search path.
HISTFILE     HISTFILE     Command history is saved in this file.
HISTFILESIZE HISTFILESIZE In the history file, this is the maximum number of lines.
HISTSIZE     HISTSIZE     Command history memory size. It is set by default to 500.
HOME         HOME         The home directory of the current user.
IFS          IFS          Internal Field Separators split words after expansion and lines into words
                          with the built-in command read.
LANG         LANG         This is used by any category not selected specifically with a variable
                          beginning with LC_ to determine the locale category for that category.
PATH         PATH         This is the search path for commands—the shell searches for commands in the
                          directories delimited by colons.
PS1          PS1          Set the prompts.
                          Read built-in command timeout by default.
TMOUT        TMOUT        An interactive shell also interprets a value of seconds as the time after a
                          command is issued before submitting it. It will log the user out without
                          input.
             TERM
TERM         export       Choose a terminal type to log in with.
             TERM=vt100
SHELL        SHELL        The login shell path is set here.
             DISPLAY
DISPLAY      export       Display the name X
             DISPLAY=:0.1
             export
EDITOR       EDITOR=/usr/ Set the name of the default text editor.
             bin/vim


Conclusion

So, it was the brief information on the bash print of all environment variables
and values. We have included the best possible details to view the environment
variable through the Linux terminal. Make sure you visit our official website
to know more about Linux.


About the author


Prateek Jangid

A passionate Linux user for personal and professional reasons, always exploring
what is new in the world of Linux and sharing with my readers.
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
