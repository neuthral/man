





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Greater Than Numerical Comparison in a Bash Script

2 weeks ago
by Prateek_Jangid
Bash scripts have many options for mathematical calculations from the terminal.
You can do anything from generating a number list to comparing the numbers
through scripts. Although developing a number list is easy, comparing the
numbers can be difficult for beginners. Comparisons in a Bash script are useful
as it compares the details and executes the commands accordingly. In this
tutorial, we will explain the different ways to use the greater than numerical
comparison in a Bash script.

Greater Than Numerical Comparison in a Bash Script

There are various ways to compare two numbers in the Bash script, and we will
describe them all with some examples:

1. Compare Two Numbers Using > Command

It is a simple command which you can use to find out the greater number in the
comparison. For example, you have X=55 and Y=66. You can use the following
script to compare X and Y in a condition:
In the given source code, we used the (($X > $Y)) that returns true when the
value of X is greater than Y.
The double parentheses are used to create the integer arithmetic operations. It
is a built-in feature of the Bash script that returns either 1 for true or zero
for false. Now, let’s execute the bash script to get the following result:
./comparison.sh
Similarly, you can use the greater than or equal comparison using the >=
command. When X is greater than Y, it returns true.
This script provides the following result in the terminal:
./comparison.sh

2. Compare Two Numbers Using -Gt Command

You can use the -gt command in the script to check the greater number in the
condition. Here is the Bash script example that you can try:
The -gt command (greater than) checks if one value is greater than the other.
Once you run a Bash script, you will get the following result:
./comparison.sh
In the same way, you can use the –ge (greater than or equal) command to check
the greater than or equals to numerical comparison:
You will get the following result by executing the script in the terminal:
./comparison.sh

Conclusion

This is how you can efficiently perform the greater-than numerical comparison
in a Bash script. You can compare variables, strings, and numbers using the
script’s > or -gt command. We used the multiple examples to describe the
methods to compare two numbers in Bash. Similarly, you can use < or -lt
commands to evaluate the less than numerical comparison.


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
