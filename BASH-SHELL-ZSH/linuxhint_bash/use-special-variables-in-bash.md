





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Special Variables in Bash

12 months ago
by Suparna_Ganguly
Are you looking for a guide to using special variables in Bash? Get prepared!
This article explains how and when to use special variables while working in
Bash.
In one of the previous articles, you learned about Bash variables. Bash comes
with special variable features as well. They are used to control the Bash
script’s execution flow. You can read their values but you can’t assign values
to them. This article will take you through the usages of 9 different special
variables used in Bash. So, let’s explore today’s topic on special Bash
variables.

$$

The $$ gives the process ID or PID number of the current shell in use. This
works differently depending upon whether you are using this special Bash
variable from the Linux command line or within the shell script. This is
because $$ produces the process ID of the running bash shell. But when you
begin with a new script you start a new Bash shell.
Let’s take a quick example explaining the concept of $$.
In the above program, 57 is our PID. ps -ef captures the first line of your
system’s full process list by allowing extended regular expression (regex),
also grepping for PID besides the PID. The | (vertical bar) allows this dual
capture. | is the extended regex separator.

[email protected]

[email protected] (dollar at the rate) means all parameters passed to the Bash
script. All arguments get double-quoted individually. For instance, if a Bash
script receives two arguments, the [email protected] variable is equivalent to
$1 $2.
Each positional parameter expands as a separate field – the first parameter
would be joined with the first part and the last parameter would be joined with
the end part of the whole word. However, if there’s no positional parameter,
the special variable @’s expansion produces zero fields, and it’s even when you
double-quote @.

$*

The special variable $* (dollar star) signifies all variables written in a
single string. All arguments are generally double-quoted.
In the above example, we wrote two separate parts within double quotes ending
with a ; (semicolon). Bash concatenated both of the parts making it a single
argument. As you enter a space in a Bash client, Bash interprets that
particular space as a separator.
When you begin with a Bash script, you can pass arguments. The script handles
the arguments passed to the same. For whatever reason, if the script doesn’t
handle arguments, there is no consequence to either declaring or not declaring
many, or any variables at all to the Bash script. Other variables used in
passing arguments are $1, $2, and so on.

$#

$# (dollar hash) is a special variable used in Bash that expands to the
positional parameters’ decimal number. $# contains the total number of
arguments supplied to the Bash script or the shell. When arguments are directly
passed use the following syntax.
$ bash -c ‘echo $#’ _ <arg1> <arg2>...
This is like the argc in C programming.
Now, let’s consider the following example to understand this concept further.
In the above example, bash -c receives an argument written after the command.
Here the _ (underscore) denotes a placeholder. At first, we wrote the command
without passing any arguments. Hence, the output showed 0. Then it displayed
the outputs as 1 and 3 for passing 1 (x) and 3 (x, y, z) arguments
respectively. The original arguments are x ($1), y ($2), and z ($3).
Note: The command name (parameter 0) is not counted under the number given by
‘#’. This is because ‘#’ is a special parameter and not a positional parameter.

$0

The special variable $0 shows the filename of the running script. So, when you
type:
$ echo $0
This produces the following output.
The output shows “bash” as our current script’s filename.

$?

$? is a special variable that displays what the exit code is of the latest
command. Once you know the exit code of a statement you can continue with the
script in multiple directions. If you get the exit code as 0, it generally
means the previous process terminated successfully. In case the exit code is 1
(or more than 1) it often signifies the process ended with a negative outcome
or an error. The command is:
$ echo $?
Now, let’s understand this with the code snippet shared below.
My last executed code was a success, hence after executing the command, I got 0
as the output. Next, we got an error “rm: can’t remove ‘hello.world’ : No such
file or directory”. This produced 1 as the output after running the command.
Here we tried to delete a file “hello.world” using the rm command. But
hello.world doesn’t seem to already exist in our shell. That’s why we received
an error.

$!

$! (dollar exclamation) is a special variable that contains the PID of the
latest job that has been backgrounded. ! expands to the most recently executed
background or asynchronous command’s process ID. The shell treats some
parameters specially. These can only be referenced; assigning values to them is
not allowed.
Let’s see the syntax for using the variable and its output.
$ echo “$!”
From the above output, we can see that the last background command’s PID was
88.

$-

$- (dollar hyphen) is a special variable that returns the flags used in the
current Bash shell. $- contains the shell’s flags in use in the terminal. These
flags determine the function of your shell. Let’s have the syntax and its
output.
$ echo $-
We can see -s, -m, and -i flags are active in our current Bash shell. Below are
some flags and their meanings.

* -s :-s is the short form of stdin. This reads commands from stdin.


* -m :-m is the short form of monitor. This enables job control.


* -i : -i is the short form of interactive. It means the shell currently in use
  is interactive.


* -n : -n is the short form of noexec. It means you can only read commands in a
  script and cannot execute them.


* -a : -a is the short form of allexport. This exports all defined variables.


* -D : -D lists all the double-quoted strings prefixed by $, however, it
  doesn’t let you execute commands in the script.


* -C : -C is the short form of noclobber. It prevents you from overwriting
  files through redirection.


* -B : -B is the short form of brace expansion. This enables brace expansion
  function in Bash.


$_

$_ (dollar underscore) is a special Bash variable set to the latest argument of
the last executed command. The syntax is:
$ echo $_
Below is an example to understand this special variable.
$ bash -c ‘echo $#’ _ x y

$ echo $_
From the above example, you can see that we passed two arguments x and y. So, y
is the last argument of the latest command executed. Hence, executing $_
variable we got y as the output.

The Conclusion

Today, you have learned about the usages of 9 special Bash variables, namely
$$, [email protected], $-, $_, $?, $0, $!, $*, and $#. These all are different
from each other and have different functionalities. We also provided their
syntaxes and examples showing how to use them in the terminal. While going
through this article if you practice the programs in your terminal it’d help
you understand the concept of special Bash variables better. Hope you find this
tutorial on Bash special variables informative and helpful.


About the author


Suparna Ganguly

I'm an Engineer by degree and a Writer by choice. I like to learn and explore a
good range of topics including Linux, programming, open-source, games, and
computers. My content write-ups in LinuxHint can be your source of knowledge,
guide, and values.
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
