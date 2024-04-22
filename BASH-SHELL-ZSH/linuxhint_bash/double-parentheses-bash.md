





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


What are Double Parentheses in Bash

1 week ago
by Prateek_Jangid
Brackets are important in any programming language to execute the program and
get the desired outputs. In bash, we use single and double parentheses to
perform different tasks through a script. However, many beginners and even
intermediate bash users need to learn about double parentheses. So in this
tutorial, we will briefly summarize what double parentheses are in bash.

What are Double Parentheses in Bash

The “((..))” double parentheses are similar to the let command, which you can
use to perform arithmetic calculations in a script. For example, let’s create a
script that will perform various arithmetic calculations:
#!/bin/bash
echo "Please enter the values of A and B"
read A
read B
sum=$((A+B))
echo "Addition of $A and $B is $sum"

((sub=A-B))
echo "Subtraction of $A and $B is $sub"

num1=A
num2=B

((multiply=num1*num2))
echo "Multiplication $A and $B is $multiply"

division=$((num1/num2))
echo "Division of $A and $B is $division"
Once you run the above script, the terminal will ask you to enter two numbers,
and then it will perform the calculations:

Similarly, you can use the following patterns of double parentheses styles to
get the required results:
#!/bin/bash
echo "Please enter the values of A and B"
read A
read B
sum=$((A+B))
echo "Addition of $A and $B is $sum"

((sub=A-B))
echo "Subtraction of $A and $B is $sub"

num1=A
num2=B

((multiply=num1*num2))
echo "Multiplication $A and $B is $multiply"

division=$((num1/num2))
echo "Division of $A and $B is $division"
This script provides the same result as the previous one:

You can also use the [[ rather than [  because it is an advanced type that
offers a ton of enhancements such as:

*
  o The [[ can efficiently handle the empty strings and some strings with the
    whitespace.
  o You can use || and && logical operators with [[ but not [ because single
    [ can’t pass || and && operator as a command-line argument.



Wrapping Up

This was all about the double parentheses in bash, which you can try to enhance
the arithmetic calculations easily. We have explained various types of examples
to perform arithmetic calculations by adding double parentheses. Bash contains
a ton of concepts that you can learn to become a bash expert. So make sure you
check out Linuxhint to read various tutorials of bash.


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
