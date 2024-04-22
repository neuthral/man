





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Continue Built-In Statement

1 week ago
by Prateek_Jangid
In bash, the continue built-in statement functions as a control statement.
Program control is passed to the next iteration unless specified in the
enclosing loop body for the current iteration. This concept appears in bash
along with other programming languages.
However, it is always hard for a beginner to learn the bash continue statement.
So if you are also looking for simple ways to learn it, this tutorial is for
you. This tutorial will give you a brief on the bash continue built-in
statement with various examples.

Bash Continue Built-In Statement

The bash continue built-in statement resumes the iteration of an enclosing loop
such as while, for, select, or until. It has meaning only when it applies to
loops. Its general syntax is :
continue < n >
 
In the above syntax, n denotes an integer value whose default value is 1. This
integer value represents the depth of the continue statement. Execution
continues on the loop control of the nth enclosing loop when n numbers are
given, i.e., you can start the outer loop statement by increasing the integer
value.

Resumes an Iteration in Different Loops With Continue Built-In Statement

In bash, you can use the continue statement in different loops. It depends on
the loop type whether the program restarts or starts over.

Continue Built-in Statement in For Loop

The controlling variable takes the next element in the list as its value within
the “for” loop. We have taken numbers from 3 to 60 under the for loop in the
following script. Here, through the continue statement, we print out those
numbers divisible by 10 and continue the loop.

In the following output, you can see that only those numbers from 3 to 60 are
printed, which are divisible by 10.

Continue Built-in Statement in While Loop

When you use the continue statement in “until” and “while” constructions, the
system resumes the execution with the command at the top of the loop.
This while loop starts with 25 numbers and continues until the value of n
reaches 15 in the loop. Under this loop, if the value of n is less than 19, it
prints that number along with the “class.”

On running the above script, you will get the blow output.

Continue Built-in Statement Until Loop

Compared to the while loop, the until loop is not much different. In the same
way, it works. In the following until loop example, numbers will be added
starting from 25 and will continue until n exceeds 13. Under this loop, if the
value of n is more than 17, it will print with the number “You are not an
adult.”

You will get the following output after running the above script.

Wrapping Up

You use the bash continue built-in statement when you want to leave the loop
partially but skip a code when the input meets a specific condition. The
continue statement passes the control back to the loop statement for the next
iteration, except for executing the code when a defined condition is met.


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
