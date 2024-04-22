





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Set Bash Options

7 months ago
by Omar_Farooq
A user may personalize the Linux system using a variety of choices. The “Set
builtin” instruction set is among the most well-known and helpful. With its
easy instructions, the Set Built-in can set a variety of environment variables
in Bash. Today, we’ll look at various instances of Set Built-in instructions in
the Ubuntu 20.04 Linux system and review and apply them. Begin by logging into
your computer system. Let’s open the shell terminal to perform some of the set-
builtin options available and well-known among Linux Bash users.

Example 01: Set -x

The set -x option is utilized for the troubleshooting of commands. Before using
it, we have been looking at the simple “echo” instruction to display a string
“built-in” on the shell. The string value has been displayed successfully. We
must use the “set” instruction to set the “-x” option in Bash to troubleshoot
the commands. After using it, we executed the “echo” statement to display
“built-in”. The output is a little different. Each statement you might add will
be returned to you with a “+” sign.
The output displays the echo statement in the shell with the plus sign. After
that, it also showed the string within the echo statement as far as the
execution of the “echo” statement was concerned. The “+” line is the result of
troubleshooting for this instruction. After this, we have used the “set +x”
option to undo the “set”. After using the “echo” query, we currently know that
the shell is back to normal.

Example 02: Set -u

The built-in “set -u” command is used to declare an exception whenever it meets
any variable with no value. So, we have been performing this example within the
Bash file. Create a new file “new.sh” with the “touch” command and open it in
the editor, i.e., “nano”.
We added the Bash support in the code and utilized the “echo” statement stating
“checking set -u”. Then, we have to set the “-u” option using the “set -u”
line. Next, we initialized a string variable “v” with a value “Hello World”.
After this, we used two echo statements to display two variables, “v” and “z”.
As the variable “z” is neither declared nor initialized in the code, we expect
this line to throw an exception during execution. So, save the code and exit
the file.
We have used the Bash instruction to run the Bash file “new.sh”. The first echo
statement displays the “checking set -u” set of strings. After this, the value
of variable “v” is shown as “Hello World”. The last line displays the error due
to line 6, variable “z”.

Example 03: Set -o

The set built-in “-o” options work the same as the option “-u”, i.e., throw an
exception while encountering some invalid situation. So, we have been using the
very same code file and updated it a little. We have utilized the “set -o”
option with the noun set instead of “set -u”. After this, we initialized a
string variable with some value and used two echo statements to display two
variables, “v” and “z”. The value of “v” will be displayed as initialized
already, but the echo statement to print “z” will throw an exception as it is
neither declared nor initialized in the code. Let’s save this code and run it
to see the result.
After running this Bash script with the “bash” instruction, we have found out
that it displayed the first echo statement string and the value of variable “v”
as “Hello World”. Also, it shows an error because the variable “z” is missing,
i.e., unbound variable.

Example 04: Set -n

We have developed the new option “-n” specially designed to ignore the set of
statements or instructions within the Bash code. This means that it will not be
executing the lines in the code coming after it. So, we have updated our code
again as shown and added a simple echo statement to display a sentence. Two
variables of string types have been initialized, i.e., v1 and v2. Then, an echo
statement is here to display the value of variable “v1”. After displaying v1,
we used the “set -n” option here in the code. After setting “-n” in the code,
we have used the echo statement to display the value of the other variable,
“v2”. According to this situation, the last echo statement must not be
executed. Let’s see now:
So, we have executed the updated Bash file and got to know that the output is
as expected. The first echo statement shows a simple sentence, and the other
displays the value of v1. While the value of v2 through echo statement didn’t
get displayed due to the use of set “-n”.

Example 05: Set -e

The set -e is being used to leave immediately when the Bash detects a non-zero
condition. To test it, we have been updating our code with the new function
addition, i.e., “testfunc()”.Two echo statements have been used to display some
strings. We used the “return 1” status within both echo statements. Outside the
function, we used the set “-e” option to exit the execution when encountering
non-zero status and called the “testfunc”.
After running this code, only a single string from the first echo statement was
displayed. This is because we have used “set -e” before the function call and
it encountered “return 1” in the code. This is why the second echo statement
didn’t get executed.

Conclusion:

This was all about using different set-builtin options in the Bash code to get
different and unique outputs. We have tried the set -x, set -e, set -u, set -o,
and the set -n options within our Bash codes. There are a lot of other options
available. We hope you found this article helpful. Check the other Linux Hint
articles for more tips and tutorials.


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
