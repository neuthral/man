





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Expr in Bash for Multiplying and Division of Numbers

2 weeks ago
by Prateek_Jangid
The expr command in Bash is used to evaluate expressions. These expressions can
take more than 1 argument, which can be anything like regex, integer, string,
etc. The expr command in Bash performs basic calculations like addition,
subtraction, etc. It also evaluates the string operations like substring,
evaluating regular expressions, length of the string, etc. However, many Bash
users may get confused in approaches or in multiplying and dividing numbers.
Here, we will perform the multiplication and division of numbers in Bash
through the expr command.

Expr in Bash for Multiplication and Division of Numbers

The expr command in Bash reads and evaluates the expression parameters and
writes the result to standard output. The syntax of the expr command is:
`expr integer1 operator integer2`

Multiplication of Numbers in Bash Using the Expr Command

Although “*” symbolizes multiplication, “*” in Bash represents all files in the
current directory. If you use “*” directly with the expr for the multiplication
of two numbers in the shell, it gives you an error. So, to multiply the numbers
in Bash, use “\*’” instead of “*”.
The following example explains how you can multiply the numbers in Bash using
the expr command:
#! /bin/Bash
#Multiplication of integers using the expr command
A=25
B=5
echo "Multiplication of A and B is (A x B) = AB"
echo "AB= `expr $A \* $B`"
Output:

Division of Numbers in Bash Using the Expr Command

Let’s divide the numbers in Bash using the “/” symbol. The following example
will give you a better clarification:
#! /bin/Bash
#Division of integers using the expr command.
A=25
B=5
echo "A / B = `expr $A / $B`"
Output:

Conclusion

This is how you can multiply and divide the numbers using the expr command in
Bash. Creating arithmetic calculations in Bash is simple, and we recommend that
you learn these arithmetic operations as beginners. This practice can help you
gain a hands-on experience with the Bash scripts. For more information on Bash
and shell scripting, please visit the Linuxhint website. We uploaded hundreds
of tutorials that are related to Bash and other programming languages.


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
