





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to debug a bash script?

3 years ago
by Sam_U





Any program needs to be free of errors before it reaches the consumers.
Software developers try their best to make the software programs bug-free. But
it is hard to make a code faultless when there are thousands of lines.
Debugging is an ongoing process; it helps in immediately detecting errors,
gathering valuable information about code, and eliminating redundant code
chunks.
All the programming languages have some common and few distinct approaches to
find bugs. For example, debugging programs can be used to remove errors
quickly. Whereas shell scripting does not have any particular tool to debug the
code. This write-up is about discussing various debugging techniques that can
be used to make the bash script error-free. Before we dive into the methods,
let’s have a basic understanding of shells and shell scripting:

What is the shell in Linux?

When you boot up your computer, the kernel gets information about the attached
hardware and allows other attached components to interact. Apart from that, it
manages memory, CPU and recognizes any new peripheral. All in all, a kernel is
the backbone of any operating system. But have you ever thought to interact
directly with the kernel, command it to perform a specific task? Is it even
practicable to do that? Absolutely! With the help of a shell, a computer
program with an interactive interface, anybody can operate the kernel. The
shell allows humans to interact with the kernel and instruct it to perform any
task.
In Unix, there are two main shells Bourne shell and C shell. Both of these
types have their subcategories. Different types of Bourne shells are Korn shell
(ksh), Almquist shell (ash), Bourne again shell (bash), and Z shell (zsh). At
the same time, the C shell has its own subcategories like C shell (csh) and
TENEX C shell (tcsh). As mentioned above, out of all the shells, Bash (Bourne
again shell) is the most widely used shell and comes out of the box in many
Linux distributions because of its efficiency and user-friendliness.
Bash is the default shell of many Linux distributions and is extensively used
by millions of Linux users. It is so diverse and influential that it can
perform every task you usually perform in GUI-based applications. You can edit
files, manage files, view photos, listen to music, play videos, and much more.

What is a Shell Script:

As we have learned the basic idea of shell, now let’s move towards shell
scripting. The shell script is a computer program that executes multiple
commands in a shell that acts as an interpreter to perform a specific function.
As discussed above that, there are 2 particular types of shells. However, this
guide is focusing on the Bourne Again shell (Bash).
So what is a bash script? In Linux, all the bash commands are stored in “/usr/
bin” and “/bin” folders. For instance, whenever you run a command, bash
searches if it exists in the directory or not. The command gets executed if it
finds in the directories else gives an error.
How about performing a task that needs multiple commands to run in the
terminal? In this specific situation, bash scripting can help you. Bash
scripting is a form of shell scripting which allows you to make programs to run
multiple bash commands to perform a specific task.

What are bugs in bash scripting:

While working with bash scripting or with any other programming languages, you
encounter many errors. A bug is an error or a fault in the program that can
cause the program to behave incorrectly.
Every programming language has its own procedure to find bugs; similarly, bash
also has many build-in options to debug a terminal program.
Managing errors and debugging a program is no less than a hassle. It is a time-
consuming job and can worsen if you are not aware of the right tools to debug
your program. This write-up is a complete guide about debugging of bash-scripts
to make your script error-free. So let’s begin:

How to debug a bash script:

When you work on large programming projects, you encounter many errors or bugs.
Debugging a program can sometimes be complicated. Programmers usually utilize
debugging tools, and many code editors also assist in bug finding by
highlighting the syntax.
There are various tools in Linux to debug codes, for example, GNU Debugger aka
“gdb.” Tools like GDB are helpful for programming languages that compile into
binaries. Since bash is a simple interpreted language, there is no need for
heavy tools to debug it.
There are various traditional techniques to debug a bash scripting code, and
one of them is adding “Assertions.” Assertions are conditions that are added in
the programs to check specific conditions and execute the program accordingly.
It is a defensive technique that helps in finding bugs and testing as well. You
can find many toolsthat assist in adding assertions in bash scripts.
Well, adding assertions is one of the old traditional techniques. There are
sets of flags/options available in bash to debug a bash script. These options
can be added along with shebang in the scripts or added while executing the
program in the terminal. The topics we are going to take up are listed below:

  1. How to debug bash script by enabling verbose “-v” option
  2. How to debug bash script using xtrace “-x” option
  3. How to debug bash script using noexec “-n” option
  4. How to identify the unset variables while debugging bash script
  5. How to debug the specific part of the bash script
  6. How to debug a bash script using the “trap” command
  7. How to debug a bash script by eliminating file globbing using the “-f”
     option
  8. How to combinedebugging options to debug a shell script
  9. How to redirect debug-report to a file

So let’s check various techniques in bash to debug a bash script:

1. How to debug bash script by enabling verbose “-v” option:

One of the easiest approaches to debug the bash script is using the “-v”
option, also known as verbose. The option can be added with the shebang or
explicitly put with the script file name while executing it. The verbose option
will execute and print every line of the code as the process by the
interpreter. Let’s understand it with a bash script example:
#! /bin/bash
echo "Enter Number1"
read number1
echo "Enter Number2"
read number2
if [ "$number1" -gt "$number2" ]
then
echo "Number1 is greater than Number2"
elif [ "$number1" -eq "$number2" ]
then
echo "Number1 is equal to Number2"
else
echo "Number2 is greater than Number1"
fi
The above code is getting two numbers from the user and then performing some
conditional statements to check whether the number is more significant, less,
or equal to the other entered number. Though any text editor can be used for
bash scripting, I am using Vim editor. Vim is a powerful, feature-rich editor
that highlights the syntax of bash scripts and reduces the chances of syntax
errors. If you do not have Vim editor, get it by running the command mentioned
below:
$sudo apt install vim
Create a bash script file using:
$vim b_script.sh
If you are new to Vim editor, I recommend you learn how_to_use_the_vim_editor
before proceeding.
Now, back to script, execute the script by using “-v” option:
$bash -v b_script.sh
It can be seen in the above output that each line of the script is printed in
the terminal as they process by the interpreter. Note that the script will stop
taking input from the user and then process the next line of the script. As
discussed above that the “-v” option can be placed after shebang as shown in
the following:
#! /bin/bash -v
Similarly, the verbose flag can also be added in the next line of shebang using
the “set” command:
#! /bin/bash
set -v
Any of the methods discussed above can enable verbose.

2 How to debug bash script using xtrace “-x” option:

Execution trace, also known as xtrace is a smart and useful debugging option,
especially to trace logical errors. Logical errors are usually associated with
variables and commands. To check the state of the variable during the execution
of the script, we use the “-x” option. Now again, run the “b_script.sh” file
with the “-x” flag:
$bash -x b_script.sh
The output is explicitly showing the value of each variable during the
execution process. Again, the “-x” can be used beside the shebang and after the
shebang line using the set command. The xtrace puts the “+” sign with each line
of the script.

3 How to debug bash script using noexec “-n” option:

Syntax errors are one of the primary causes of bugs. To syntactically debug the
bash script, we use“noexec” (no execution) mode. The option used for noexec
mode is “-n.” It will only display the syntax errors of the code instead of
executing it. A much safer approach to debugging the code. Let’s execute
“b_script.sh” again with the “-n” option:
$bash -n b_script.sh
There will be no execution of code if there is no syntax error. Now, let’s
modify our code:
#! /bin/bash

echo "Enter Number1"
read number1
echo "Enter Number2"
read number2
if [ "$number1" -gt "$number2" ]
then
echo "Number1 is greater than Number2"
elif [ "$number1" -eq "$number2" ]
#then
echo "Number1 is equal to Number2"
else
echo "Number2 is greater than Number1"
fi
I am commenting “then” after “elif”. Now, with “-n” execute “b_script.sh”
script:
$bash -n b_script.sh
As anticipated, it clearly identified the error and displayed it in the
terminal.

4 How to identify the unset variables while debugging bash script:

Making a typo while writing a code is common. Often, you mistype a variable,
which does not let the code execute. To identify such an error, we use the “-u”
option. Let’s modify the code again:
#! /bin/bash
echo "Enter Number1"
read number1
echo "Enter Number2"
read number2
if [ "$num1" -gt "$number2" ]
then
echo "Number1 is greater than Number2"
elif [ "$number1" -eq "$number2" ]
then
echo "Number1 is equal to Number2"
else
echo "Number2 is greater than Number1"
fi
In the first “if” conditional statement, I renamed the “number1” variable to
“num1”. Now “num1” is an unset variable. Now run the script:
$bash -u b_script.sh
The output has identified and explicitly displays the name of an unset
variable.

5. How to debug the specific part of the bash script:

The xtrace mode processes every line of the code and gives output. However,
finding errors in a large code would be time-consuming if we already know which
part is potentially causing the error. Luckily, xtrace also allows you to debug
a specific portion of the code, which can be accomplished using the “set”
command. Place “set -x” at the beginning of the portion that needs to be
debugged and then “set +x” at the end. For example, I want to debug the
conditional statements of “b_script.sh”, so I will enclose all the conditional
statements in “set -x” and “set +x” options as shown in the code below:
#! /bin/bash
echo "Enter Number1"
read number1
echo "Enter Number2"
read number2
set -x
if [ "$number" -gt "$number2" ]
then
echo "Number1 is greater than Number2"
elif [ "$number1" -eq "$number2" ]
then
echo "Number1 is equal to Number2"
else
echo "Number2 is greater than Number1"
fi
set +x
Now, run the script using “bash b_script.sh”.
The output is only debugging the if conditions as specified.

6. How to debug a bash script using the “trap” command:

If your script is complicated, then there are more elaborative techniques as
well for debugging. One of them is the “trap” command. The “trap” command
catches the signals and executes a command when a specific situation occurs.
The command can be a signal or a function. I have created another script by the
name of “sum_script.sh”:
#! /bin/bash
trap 'echo "Line ${LINENO}: First number is $number1 , Second number is
$number2 and sum is $sum" ' DEBUG
echo "Enter first number"
read number1
echo "Enter second number"
read number2
sum=$[number1 + number2]
echo "the sum is $sum"
The“trap” command with “DEBUG” signal display the status of the variables
“number1”, “number2” and “sum” after the execution of each line as shown in the
following output image:
The yellow blocks are blank spaces because the user has yet entered no input;
these spaces will fill up as the user enters values. This method is also quite
helpful in debugging bash scripts.

7. How to debug a bash script by eliminating file globbing using the “-f”
option:

File globbing is a process of finding the files with wildcard characters, i.e.,
“*” and “?”. In many situations, you don’t need to expand files while
debugging. In such cases, you can block the file globbing using the “-f”
option. Let’s understand it with a script “fglobe_script.sh”:
#! /bin/bash
echo "Display all text files."
ls *.txt
The above code will display all the text files in the current directory,
execute:
$bash fglobe_script.sh
To turn off file globbing, use the “-f” option:
$bash -f fglobe_script.sh
Similarly, you can use it with the shebang and with the “set” command as well:
#! /bin/bash
echo "Display all text files."
ls *.txt
set -f
echo "Display all text files"
ls *.txt
set +f
Now, run “bash fglobe_script.sh”:
The portion enclosed with “set -f/set +f” options did not process commands with
wildcard characters.

8. How to combine debugging options to debug shell script:

We use only one option in the above-mentioned debugging techniques, but we can
combine various options for better comprehension. Let’s implement “-x”and “-v”
options to the “sum_script.sh” script. I am using the “sum_script.sh” script.
#! /bin/bash
echo "Enter first number"
read number1
echo "Enter second number"
read number2
sum=$[number1 + number2]
echo "the sum is $sum"
Now execute:
$bash -xv sum_script.sh
Both “-x” and “-v” outputs are combined, as displayed in the output image.
Similarly, we can also combine the “-u” option with verbose “-v” for error
detection. I am replacing the “number1” variable with “num” in the sixth line
of the script:
#! /bin/bash
is $number2 and sum is $sum" ' DEBUG
echo "Enter first number"
read number1
echo "Enter second number"
read number2
sum=$[num + number2]
echo "the sum is $sum"
To view the output, run the below-mentioned command:
$bash -uv sum_script.sh

9. How to redirect debug-report to a file:

Saving a debug report of a bash script to a file can be handy in many
situations. It is a bit tricky because to redirect debug-report to a file; we
use some special variables. Let’s implement it on “b_script.sh” code:
#! /bin/bash
exec 5> dubug_report.log
BASH_XTRACED="5"
PS4='$LINENO-- '
echo "Enter Number1"
read number1
echo "Enter Number2"
read number2
if [ "$number" -gt "$number2" ]
then
echo "Number1 is greater than Number2"
elif [ "$number1" -eq "$number2" ]
then
echo "Number1 is equal to Number2"
else
echo "Number2 is greater than Number1"
fi
In the second line of the code, it can be seen that we are redirecting the
output to a “debug_report.log” file using the “exec” command with file
descriptor 5 (FD5).
exec 5> debug_report.log: The “exec” command is redirecting everything
happening in the shell to a file “debug_report.log.”
BASH_XTRACEFD=”5”: It is a particular_bash_variable and cannot be used in any
other shell. It needs to be assigned a valid file descriptor, and bash will
write the extracted output to “debug_report.log.”
PS4=’$LINENO– ‘: It is also a bash variable used to print the line number while
debugging using xtrace mode. The default value of PS4 is the “+” sign
The above script is generating a log file called “debug_report.log,” to read
it, use the “cat” command:

Conclusion:

A code full of bugs can affect the program’s performance and harmful to the
hardware as well. Debugging is very crucial for every program since it makes
the program more efficient. Finding existing and potential errors during the
development of a program can prevent your program from behaving unexpectedly.
Large codes usually need active debugging, enhancing the code’s effectiveness
by eliminating the recourse consuming chunks of code.
Many programming languages and environments have their own companion debuggers.
In bash scripting, various techniques can be implemented to debug the script.
This guide thoroughly focused on all of the methods that can be used to find
bugs in the bash scripts. So whenever you feel that your bash script is not
behaving as expected, use any of the techniques mentioned above, but xtrace
mode (-x) is pretty helpful in most cases.


About the author


Sam U

I am a professional graphics designer with over 6 years of experience.
Currently doing research in virtual reality, augmented reality and mixed
reality.
I hardly watch movies but love to read tech related books and articles.
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
