





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use $() and ${} Expansions in a Shell Script

3 years ago
by Karim_Buzdar
If you are using a Linux system, you might already know how crucial a shell
interface is for interacting with your system. On most Linux distributions,
Bash is the default shell that we use to run commands and execute scripts. A
shell script is a set of commands that, when executed, is used to perform some
useful function(s) on Linux. This .sh file, written by a user, contains all the
commands used to perform a task so that we do not have to run those commands
manually, one by one.
In this tutorial, we will explain two of the most useful bash expansions used
in shell scripts:

* $() – the command substitution
* ${} – the parameter substitution/variable expansion

An expansion in Shell is performed on the script after it has been split into
tokens. A token is a sequence of characters considered a single unit by the
shell. It can either be a word or an operator.
We have run all the examples and scripts mentioned in this article on a Debian
10 Buster system. However, you can easily replicate them on most Linux shells.
We are using the default Debian command line, the Terminal, for this tutorial.
On Debian, you can access it through the Application Launcher search bar as
follows:
To access the Application launcher, simply hit the Super/Windows key on your
keyboard.

$() Command Substitution

According to the official GNU Bash Reference manual:
“Command substitution allows the output of a command to replace the command
itself. Bash performs the expansion by executing the command and replacing the
command substitution with the standard output of the command, with any trailing
newlines deleted. Embedded newlines are not deleted, but they may be removed
during word splitting.” Command substitution occurs when a command is enclosed
as follows:
$(command)
or
`command`
For example, the following echo commands substitute the date command’s output
as their input:
$ echo $(date)
$ echo ‘date’
You can also use command substitution to assign value to a variable. For
example, we will print today’s date through the variable TODAY as follows:
$ TODAY=$(date)
$ echo "$TODAY"
Another utility of the command substitution is in shell loops to get input.
Here, we will try to print all the .txt files in our home folder using command
substitution:
for f in /home/sana/*.txt
do
  echo "$f"
done

Using Command Substitution in a Shell Script

The above examples are a few ways in which you can utilize the power of command
substitution in your shell script. Here is a sample status report that we can
print using the following shell script:
#!/bin/sh
 
echo ***Status Report***
 
TODAY=$(date)
echo "Today is $TODAY"
 
USERS=$(who | wc -l)
echo "$USERS users are currently logged in"
 
UPTIME=$(date ; uptime)
echo "The uptime is $UPTIME"
Command substitution has been used thrice in this script; in printing the date,
logged in users and uptime. We saved the script as follows:
Made it executable and then ran it through the following command:
$ chmod +x status.sh
$ ./statys.sh
Here is the output of our status.sh script:
You can, of course, create more meaningful scripts by following the examples we
have just mentioned.

${} Parameter Substitution/Expansion

A parameter, in Bash, is an entity that is used to store values. A parameter
can be referenced by a number, a name, or by a special symbol. When a parameter
is referenced by a number, it is called a positional parameter. When a
parameter is referenced by a name, it is called a variable. When a parameter is
referenced by a special symbol, it means they are autoset parameters with
special uses.
Parameter expansion/substitutionis the process of fetching the value from the
referenced entity/parameter. It is like you are expanding a variable to fetch
its value.
The simplest possible parameter expansion syntax is the following:
Here is how you can use the parameter expansion in Bash:
${parameter}
For example, the simplest usage is to substitute the parameter by its value:
$ name="john doe"
$ echo “${name}”
This command will substitute the value of the variable “name” to be used by the
echo command:
You might be thinking that the same can be achieved by avoiding the curly
braces as follows:
The answer is that during parameter expansion, these curly braces help in
delimiting the variable name. Let us explain what we mean by limiting here. Let
me run the following command on my system:
$ echo "The name of the person is $name_"
The result did not print the value of the variable name as the system thought
that I was referring to the variable “name_”. Thus, my variable name was not
“delimited”. The curly braces in the following example will delimit the
variable name and return the results as follows:
$ echo "The name of the person is ${name}_"
Here are all the ways in which variables are substituted in Shell:

${variable}          This command substitutes the value of the variable.
                     If a variable is null or if it is not set, word is
${variable:-word}    substituted for variable. The value of the variable does
                     not change.
${variable:=word}    If a variable is null or if it is not set, the value of
                     the variable is set to word.
${variable:?message} If a variable is null or if it is not set, the message is
                     printed to the standard bash error.
${variable:+word}    If variable is set, word is substituted for variable.
                     However, the value of the variable itself does not change.

The above examples are a few ways in which you can utilize the power of
variable substitution in Bash. You can incorporate these ways to use expansion
in your shell scripts to optimally achieve your task at hand.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
