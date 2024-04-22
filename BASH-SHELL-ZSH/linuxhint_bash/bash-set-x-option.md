





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How To Use Bash “set -x” Option?

1 year ago
by Aqsa_Yasin
Before it reached the public, each software must be error-free. Software
engineers make every effort to ensure that their applications are bug-free.
While there are hundreds of code lines, it is still difficult to build an
error-free code. Troubleshooting is a continuous process that aids in the
detection of mistakes, the collection of useful code information, as well as
the elimination of superfluous code sections. Set -x switches the shell to a
state in which all instructions are displayed to the console. It’s evident that
you’re using it for troubleshooting, which would be a common use case for set -
x: showing every instruction as it’s processed might help you to understand the
script’s input and output when it’s not working as anticipated.
Many systems include shell inbuilt man pages, however, these are only valid if
you’ve used the standard shell. We possess POSIX control man pages, which would
show up for terminal builtins since there isn’t a freestanding tool to shadow
them; those man pages seem valid across all Bourne-style terminals but seem to
be frequently inadequate. The solution is the same across Bourne-style shelling
in this situation. Let’s have a look at the man page of the set.
Before that, log in from the Linux operating system and try to open the console
application through the app area. If you want to do it quickly, just try “
Ctrl+Alt+T”. When the console shell got opened, open the man page using the
help instruction command within the shell as below:
$ help set
You will get a lot of information regarding the set feature and its usage.
Let’s scroll a little below to find out about set –x more. You can see that it
says this could print commands and their arguments as they are executed.
Set -x operates across both collaborative and non-interactive environments, so
test it in a dynamic terminal to see just what happens. Each statement is
initially repeated back to the user. Let’s have a look at “set –x”, but within
it, we will also have a look at the “set +x” option after some time. So first
of all, we need to execute the set –x option in the shell as per the below
snapshot. The output shows that the “set –x” has been set and it will let you
know that it has to print the lines of code as it is as they are implemented.
$ set -x
Let’s have a look at the basic code of bash to implement the set –x on our
system. First of all, we will be implementing the one-line code to check the
change of set –x on it. So, we have used the simple “echo” statement in the
shell. Make sure not to use double inverted commas for the covering of an echo
message. Because it will not be going to work the way we want it. The output
shows the repetition of an echo statement in the shell as it is first with the
plus sign. After that, we have seen how it also displayed the message of the
echo statement in the shell as per the execution of the “echo” statement.
$ echo ‘This is the line’
Let’s see some more lines of codes to get a glance at “set –x” in bash within
Ubuntu 20.04 system. First of all, we have added the bash extension within the
shell command line area and hit “Enter”.
$ #!/bin/bash
After that, we have declared a simple variable named “val” and assigned it a
string-type value “Aqsa”. After that, we have again tapped the “Enter” button
from the keyboard.$ val=“Aqsa”
After the initialization or declaration of a variable, we wanted to print it in
our terminal using the “echo” instruction. You will see it will print the value
of variable “val” as Aqsa” in the output area. Right now, we have not applied
the settings option on the code, that’s why it simply displays the value of the
variable, and nothing changes. This was the simple code to do, without a set
option.
$ echo $val
Let’s set the “set +x” option and see what changes. For that simply try the
below command:
$ set +x
We have declared a variable named “age” in the shell having integer type value
“25”. When we have used the echo statement to display the value of the variable
“age”, it simply displays it with no change. Hence, this proves that “set +x”
always works as opposed to “set –x”.
$ age=25

$ echo $age
Let’s set the “set –x” option and have new lines of code on the terminal.
So we have tried the below query to set the “-x” option:
$ set –x
Now the option has been set, it’s time to declare some variables first. So, we
have declared a variable named “job” in the shell. Then, we have assigned it a
string type value “writer”. When we have pressed “enter”, it displays the same
line of instruction at the output area, with the plus sign as per the image
below.
$ job=writer
When we tried the echo statement to show the value of the “job” variable, it
does not only shows what echo statement is going to print, e.g., value “writer”
of variable “job” with a plus mark but also displays its value at the next line
separately.
$ echo $job
Let see how it works with the echo statement when more than two variables are
used within it with a “+” mark for concatenation of strings. Hence, we have
used the below instruction to concatenate two string-type variables. At the
first line of output, it displays what is going to be the output, and the
second line of output simply executed the result of the “echo” phrase.
$ echo $val + $job
After this, we have used the same style of concatenation for string and integer
type of variable. It outputs the same way as it does above.
$ echo $val + $age
To apply set –x on some mathematical expressions, let’s first see a simple echo
statement on an expression of integers as below. Make sure to use the required
commas instead of double. It simply displays the sum of both integers.
$ echo `expr 12 + 17`
Now set –x option, and then run the above expression once again. You will see
that it will show you the steps it takes to evaluate the expression. Firstly
print the evaluation of expression within the echo line. After that, it will
show the echo statement with the expression evaluated. The last line will show
the result.
$ set –x
$ echo `expr 12 + 17`
When you set +x, it will reverse the process as below:
$ set +x
$ echo `expr 12 + 17`

Conclusion:

The above discussion shows that when set -LETTER enables a possibility, set
+LETTER disables it. As a result, setting +x disables traces. The set +x trace
is inevitable unless you quit the shell — in which case you would use a
subshell.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
