





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Floating Point Math in Bash

1 week ago
by Prateek_Jangid
A number that has a decimal space is a floating number. A floating number is a
positive and negative whole number with a decimal point like 2.5, 10.8, -5.23,
etc. That’s why accuracy is crucial when you use a floating number in a
calculation.
When working with numbers, you should perform quick floating point math,
especially in shell scripts. However, it can take a lot of work for a beginner
to evaluate floating points in bash. So in this tutorial, we will give you a
brief on the ways to perform floating point math in bash.

Floating Point Math in Bash

Bash only supports integer arithmetic, so if you need to perform calculations
with floating-point numbers, use a separate utility in bash. Let’s go through
some utilities and see how to perform floating point math in bash:

1. BC

The bc command is an interactive process to provide arbitrary-precision
arithmetic in bash. The bc command first reads the input file specified by any
file parameter and then reads the standard input. With the bc arbitrary
precision calculator, you can perform floating point math in shell scripts such
as addition, subtraction, multiplication, division, etc. For example, we have a
bash file as follows:

As you can see, we have just used the bc command using pipe in this bash file.
Let’s run the script in the terminal:

The above output shows addition, subtraction, multiplication, and modulus are
all correct, but the division answer is wrong. Therefore, we have to add the
scale for the division:

Along with all the division output, it will also be correct.

Now we will go back to the bash file and declare another number whose value
will be whatever you want and will do operations like power, square root, etc.

Here we will find the square root of 2.2, which we have already declared in our
bash file. On running the bash file, our output will be something like this:

Thus, you can perform floating point math in bash through the bc command.

2. PERL

The Perl language does not require compiling; instead, it allows platform-
independent code. You can also perform arithmetic of floating numbers in bash
with the help of Perl, which supports language features like C, C++, csh, sh,
grep, awk, and sed. You can do this by running the following commands:
$ perl -e 'print 2.2 + 3.3'
$ 5.5
$ perl -e 'print 2.2 - 3.3'
$ -1.1
 

3. AWK

The awk utility allows you to write effective but short programs as statements.
Mostly, awk is used for patterns for scanning and processing. This command
searches one or more files to see if they contain matching lines and performs
related actions. You can easily perform floating point math in shell script
through awk pattern scanning and processing.
You can use awk for any floating number to calculate the power (**,^), the
natural logarithm (log(x)), the square root (sqrt(x)), the arctangent (atan2
(y,x)), the sine function ( sin(x)), the cosine function (cos(x)), and so on:
$ echo - | awk '{print sqrt (3.2)}'
$ 1.78885
$ echo - | awk '{print s62.5 / 5.5}'
$ 11.3636
$ echo - | awk '{print sqrt 2.2 ^ 1.3}'
$ 2.78708
 

Wrapping Up

So this was all about the methods to evaluate floating point math in bash
script. You calculate the floating point in different programming languages
​​like Perl, Python, Ruby, bc arbitrary precision calculator, and awk pattern
scanning and processing language. You only need to add the commands in the bash
script and then run the script to get the desired results.


About the author


Prateek Jangid

A passionate Linux user for personal and professional reasons, always exploring
what is new in the world of Linux and sharing with my readers.
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
