





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Simple Addition and Subtraction of Numbers in Bash

2 weeks ago
by Prateek_Jangid
Bash includes various arithmetic operations like addition, subtraction,
division, multiplication, modulus, exponent, etc. As a beginner, you should
always go for simple arithmetic calculations through the script.
This tutorial is for you if you are also interested in learning addition and
subtraction in a Bash script. In this tutorial, we will go through several
methods to see how to do simple additions and subtractions of numbers in Bash.

Simple Addition and Subtraction of Numbers in Bash

There are multiple ways to perform arithmetic calculations in Bash. Let’s start
to briefly explain them one by one:

Using the Double Parentheses

You can use the double parentheses to perform the basic arithmetic operations.
Here is the general syntax:
$((expression))
The compound notation (( )) evaluates the result, and the variable operator $
is used to store the result. Here are some basic script examples to perform the
addition and subtraction:

Method 1


Output:


Method 2


Output:


Method 3


Output:


Method 4


Output:


Method 5


Output:


Method 6


Output:

Tip: Square bracket notation ( $[expression] ) also allows you to evaluate an
arithmetic expression and avoid it from being deprecated.

Using the Let Command

The let is a built-in command in Bash that allows you to perform arithmetic
operations. It requires the following:
let <arithmetic expression>
Through this example, you will understand better how to do additions and
subtractions in Bash using the let command:

Output:


Using the Expr Command

As a legacy command line utility, expr evaluates the integer arithmetic. In
Bash scripts, you can perform arithmetic expansion with the help of the expr
command, which is also known as an all-purpose expression evaluator. The expr
command also performs the same function as the let command, but it prints the
result directly rather than saving it to a variable. The syntax to execute the
expr command in Bash is as follows:
`expr value1 operator value2`
The following example shows how you can get the results by running expr in
Bash:

Output:


Using the BC Command

The bc command can run the basic calculations in Bash. The program takes
standard input and runs interactively to perform arbitrary precision
arithmetic.

Output:


Using the Awk Command

Using awk as a pattern selector allows you to select the patterns. Through this
command, you can perform additions and subtractions in Bash as follows:

Output:


Using the Declare Command

Bash’s declare command allows the integer calculations. It is used for simple
addition and subtraction in Bash or something like this:
The -i option has to be added to perform the calculations in Bash with the help
of the declare command.

Output:


Using the Dc Command

The dc command or desk calculator helps you to make the reverse polish
calculations. It also supports infinitely precise arithmetic and takes standard
input.
In the previous script, we used “p” so that it can send the print signal to the
dc command.

Output:


Conclusion

We hope that you may understand the basic arithmetic operations such as
addition, subtraction, and many more. In this tutorial, we explained how to do
a simple addition and subtraction of numbers in Bash with multiple methods. We
included the commands like bc, awk, let, declare, etc.


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
