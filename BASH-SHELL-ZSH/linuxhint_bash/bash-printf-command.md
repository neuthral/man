





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Printf command

2 years ago
by Sam_U
Working with bash scripting, we mostly use the “echo” command to print any
output, which is convenient and easy to use and fulfills the requirement most
of the time. But simplicity comes with limitation; echo command has its own
limitation when it comes to formatting the output, in that case, “printf”
command play its role.
The “printf” command in bash scripting works the same way “printf ()” works in
the C language. This post will focus on the “printf” command, its syntax, and
examples that further elaborate the use of this command. Let’s check the syntax
of the “printf” command:
printf <var> <formate> <arguments…>
<var> : It is optional to assign output to a variable.
<formate> : It is a string that may contain different format specifiers such as
“%s”, “%b”, “%d”, “%f”, and backslash escape
<arguments…> : The arguments can be any value or variable

How to use printf command in bash scripting using Vim editor:

We are using Vim editor for this guide because of its rich functionality and
ease of use. Get Vim on your device using:
$ sudo apt install vim
Launch vim editor:
$ vim
Let’s write a simple program to print a string using “printf”:
#! /bin/bash
printf “Hello Linuxhint”
To save the file, press the “Esc” button to switch the mode and then type “:
w example.sh” and then “Enter”. Now open a new terminal window and type:
$bash example.sh
The above command will execute the script the print out “hello linuxhint” text
as shown below:
Now, let’s include some format specifiers:
#! /bin/bash
printf “%s\n” “Hello Linuxhint”
In the above example, “%s” tells that the corresponding argument should be
treated as string and “\n” for the new line. Similarly, if we use “%d,” then
the argument will be treated as an integer:
#! /bin/bash
printf “%s\n” “Hello Linuxhint” “Learn about” “Linux”
All three arguments will be treated as a string and printed in a new line as
demonstrated in the following output:
Another example is mentioned below further to understand the use of the
“printf” command:
#! /bin/bash
echo “Enter your name”
read name
echo “Enter your age”
read age
printf  “Your name : %s\nYour age : %s\n” “$name” “$age”
“Your name : %s\n Your age : %s\n ” is format while “$name” “$age” are the
arguments. Whereas “%s” pointing the arguments.

How to use conversion specifiers with printf command:

The conversion specifiers are characters used with the “%” sign to indicate how
to treat the arguments. Let’s check the list of some commonly used specifiers:

Specifier Description
%%        Prints “%” symbol
%c        Takes arguments as a single character
%e and %E Take argument in floating-point number and prints in exponential
          notation, %e for lower case letter and %E for capital letter
%g and %G Take argument in floating-point number and prints in normal or
          exponential notation
%f        Takes argument as floating numbers
%d        Takes arguments as signed integers
%u        Takes argument as unsigned integers
%o        Takes argument as an unsigned octal number
%x and %X Takes arguments as unsigned hexadecimal integers

Let’s further elaborate the above specifiers with an example in bash:
#! /bin/bash
echo “Enter a number to convert”
read number
printf  “Decimal : %d\nOctal : %o\nHex : %X\n” “$number” “$number” “$number”

How to use Flag, Width, and Precision directives with printf command:

Flag directives come with optional use with the “printf” command. The commonly
used flag directives are

* “-” Left justify the output
* “+” Adds “+” sign with integer
* “0” Adds “0” with a number instead of spaces

Width directives add space with the output usually used after the flag. Let’s
understand it with an example:
#! /bin/bash
echo “Enter your name”
read name
echo “Enter your age”
read age
printf “You name and age are: %5s %5d\n” “$name” “age”
“%30s” means space is 30 characters long, and to align the output form left,
use the “-” sign “%-30s”.
The precision directive consists of the dot “.” Following by positive integer:
#! /bin/bash
printf “%.2f” 2.56473
The output would be:
If the number is an integer, the precision directive will add “0” before the
number. If the number is floating-point type, then the precision directive will
specify the number of positive digits after the decimal point. For string, it
specifies the number of characters to be displayed:
#! /bin/bash
printf “%.2f\n” 2.468936
printf “%.3d\n” 10
printf “%.3s\n” “samlinux”

Backslash Escaped parameters:

Backslash escape parameters, also called escape sequences, are used with a
backslash to format the string with the “printf” command. These sequences do
not represent themselves but interpret in some other characters. Some commonly
used escape sequences are:

Character Description
\\        Prints backslash character
\b        Prints backspace character
\n        Prints output in a new line
\r        Prints a carriage return (cursor at the beginning of the line)
\t        Gives tab space from right
\v        Gives tab space


Conclusion:

When it comes to print something in bash scripting, the “echo” command is most
commonly used because it is easy to use and remember. But “echo” command has
its limitation. Therefore, to properly format the output, the “printf” command
can be used. The “printf” command comes with plenty of options to format string
output and even basic numbers’ conversions and formatting. This guide
thoroughly comprehends the “printf” command’s functionality in bash scripting
with examples.


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
