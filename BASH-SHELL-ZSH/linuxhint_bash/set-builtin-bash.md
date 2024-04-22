





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Bash Set Builtin

1 year ago
by Omar_Farooq
The Linux system contains many options to be set in it by a user. One of the
very well-known and useful groups of commands is “Set builtin”. The Set Built-
in has many flags to set any environment variables in Bash with its simple
commands. Today, we will discuss and implement some examples to see different
Set Built-in commands in Ubuntu 20.04 Linux operating system. Start by logging
in from your system first. Open your shell terminal using the “Ctrl+Alt+T”
shortcut key on the desktop. To get information regarding the “Set Built-in”
command, use the “help” command along with the “set” keyword in your terminal
as shown.
$ help set

Example 01: Set –x

Let’s start our first example by using the “set –x” built-in. The “set –x”
command builtin is used to expand any expression or query used in the shell
followed by its interpretation. This means it will tell you what it is going to
do along with the execution. Within the terminal, we have used the echo
statement to display the string “Linux”. Right now, we didn’t set any built-in
value.
$ echo ‘Linux’
Let’s use the “set –x” in the shell, as shown in the image. After setting it,
we have used the same “echo” command to display a string “Linux” in the
terminal. The “set –x” has expanded its output by showing that the command will
“echo” the string “Linux”. On the next line, it executed the file and displayed
“Linux”.
$ set –x
$ echo ‘Linux’
To reverse the effect of “set –x” or make it default, use “set +x” as shown in
the image.
$ set +x
After setting it to default, let’s make another bash code in the shell. We have
initialized a string variable “v” with the value “Ubuntu”. Then, we tried to
display the variable value with the “echo” statement. It simply displayed the
output of a variable “v”.
$ #!/bin/bash
$ v=”Ubuntu”
$ echo $v
Let’s set the “set –x” builtin once again.
$ set -x
Run the same above code once again. You can see that the “set –x” built-in is
the cause of expanding the commands to one or more lines by expressing and
displaying.
$ #!/bin/bash
$ v=” Ubuntu”
$ echo $v
You can also see the expanded commands, their calculation on string type while
using operators. So, we have defined two string variables v1 and v2.
$ v1=”Linux”
$ v2=”Ubuntu”
The “set –x” has been used to expand again. The echo statement concatenates
both variables. Due to “set –x” builtin, the command first expanded to show
what will happen, then strings have been concatenated.
$ set –x
$ echo $v1 + $v2
The mathematical expressions can also be evaluated with the help of an “expr”
command. To subtract two integers, you have to use the below syntax. The result
shows that the “expr” command will calculate the result of subtraction. The
next expanded line shows that the calculated result will be displayed by
“echo”. In the end, the result has been displayed.
$ echo ‘expr 55 -12’

Example 02: Set –e

The set –e builtin is used in bash to exit the bash code when encountering any
non-zero status. Let’s create and open a bash file first. The “set –e” works in
the functions only.
$ touch new.sh
$ nano new.sh
After adding the bash extension, a method show() has been defined containing
two echo statements within. It also contains the “return 1” clause between the
echo statements. After the method definition, the “set -e” built-in has been
used. The show() method is called after that.
After running the code file, it only executed the first “echo” statement. This
is because the “set –x” encountered “return 1” after the first echo statement
leads to quitting the execution.
$ bash new.sh
Let’s update the code once more. We have exchanged the placement of the second
echo statement with the “return 1”. After the method, we used “set –e” and
called the method. The “set +e” has been used again, and the function has been
called once more.
After the execution, the shell has been displayed with both the echo statement
texts. The show() method got executed only once because in its first execution,
the “set –e” encountered “return 1” and the programs terminated.
$ bash new.sh

Example 03: Set –u

In the built-in group, the “set –u” command is used to declare an error when it
encounters any variable with no value set. So, open the file “new.sh” to update
the code. Add the bash extension and add the set built-in “set –u”. It can work
with and without function. Declare a string variable “a” with the value “Linux”
as demonstrated. Use the echo clause to print this variable value. Another echo
statement has been used to print the value of an unset variable “v1” as per the
image below.
When we run the bash code, it displays the value of a first variable, “a” i.e.,
Linux. While executing the second echo statement, it encounters an unset
variable. It displayed the error.
$ sh new.sh

Example 04: set –o

The built-in “set –o” works the same as “set –u”. But it can be used with the
keyword ”nounset” in the bash code. So, we opened the file and replaced the
“set –u” with “set –o” along with the keyword “nounset”. The remaining code has
been left unchanged.
After running the code displays the same output as the above “set –u” does
after running the code.
$ sh new.sh

Example 05: Set –n

The “set –n” built-in is used when you don’t want to execute the commands
listed in your bash code. So, we have updated the code once again and replaced
the “set –o” with “set –n”. After that, all the variables and statements have
been defined. Saved and quit the code.
After running this updated bash code, we have got nothing in the result. This
is because the “set –n” built-in doesn’t allow it to happen.
$ sh new.sh

Conclusion:

This article contains the explanation of Set Builtin in Bash script. In this
article, we have discussed most of the set built-in commands, i.e., set –x, set
–e, set –u, set –o, set –n. Many other built-in sets can be used as well. We
extremely believe that it will help the beginner users of bash as well as the
expert ones.


About the author


Omar Farooq

Hello Readers, I am Omar and I have been writing technical articles from last
decade. You can check out my writing pieces.
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
