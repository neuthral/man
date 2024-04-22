





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash and Conditions: A Complete Guide

2 weeks ago
by Prateek_Jangid
In Linux, Bash scripts include conditions that can help a user to perform the
decision-making tasks. Bash script conditions mainly include conditional
statements and conditional operators. The conditional statements make it easier
to write logic and make decisions accordingly. This statement concept is
similar to all programming languages but slightly different in Bash.
There are various conditions in a Bash script, but the “if statements” are the
most common ones. Many beginners always want to learn more about the Bash and
conditions. This tutorial will explain how to use the Bash conditions in Linux.

Bash and Conditions: A Complete Guide


  1. If Statement
  2. Advanced If Statements

     o If-Else Statements
     o If-Elif Statements
     o Nested If Statements

  3. Case Statements
  4. Boolean Operations

Let’s look at the brief discussion about each Bash condition with some
examples.

1. If Statement

If statements allow you to decide whether or not to execute the specific
statement of code as per the condition. It requires the “if” keyword at the
beginning and the “fi” keyword at the end of the code statement.
If the condition is true, the code performs the actions; if it is false, it
aborts the code. For example, let’s create a script that returns a statement if
one value is greater than the other:
#!/bin/bash
if [ $1 -gt 50 ]
then
echo $1 "is greater than 50"
pwd
fi
Now, if you use any number greater than 50, the script shows the following
result:
./script.sh 53
If you enter a number less than 50, it will not return any statement.

2. Advanced If Statements

The “if statement” doesn’t provide any result when it is not true. That’s why
various advanced if statements come into the picture.
If-Else Statement
The if-else statement provides the result even if the statement is not true.
Hence, if the value is true, it returns the condition_1; if it is false, it
returns the condition_2. For example, you can create a script that gives a
result about the comparison of two numbers:
 #!/bin/bash
if [ $1 -gt 150 ]
then
echo $1 "is greater than 150."
else
echo $1 "is not greater than 150."

fi
Once you execute the script in the terminal, you may get the following result
as per the number:
./<script.sh> 163
./<script.sh> 123
As you can see in the previous image, 163 returns “163 is greater than 150” and
123 returns “123 is not greater than 150”.
If-Elif Statement
The if-elif statement revolves around three conditions, making it one of the
more complex ones. In this case, the execution goes through the commands one by
one if they are true or skips when any command is false. For instance, let’s
create a script that identifies whether the number is even, odd, or zero:
Now, execute the script in the terminal and enter any number to print the
details accordingly:
Nested If Statements
You can add multiple “if conditions” in a single script in the nested
statements. For example, you can combine two different conditions where the
script can evaluate that the given number is greater than 150 and whether it is
an even or odd number:
Now, if you execute the script and enter any number, you may get the result
accordingly:

3. Case Statement

This Bash statement simplifies the complex conditions that contain multiple
choices. You can replace the “if statements” with ;; to get the result easily.
You can add multiple conditions to the case statements to make the script
cleaner and easier to understand. For example, let’s create a script that
provides the details about the employees and their designation:
Now, you can run the script in the terminal and enter any name:

4. Boolean Operations

Sometimes, you want to perform the “if conditions” but sometimes, multiple
conditions meet in a single script. That’s why we use the Boolean operations
which are classified into the following:

* Logical AND (&&) which returns true if both operands are true or returns
  false otherwise.
* Not equals to (!) which is a unary operator that returns true only if the
  operands are false but returns false if the operands are true.
* Logical OR (||) which returns true if either or both operands are true, but
  returns false if none of them are true.

Here is the example where we include all the Boolean operators in the single
Bash script:
Once you create the script, execute it in the terminal:

Conclusion:

This article is about the Bash conditions that you can use in Linux. We used
different examples to explain every condition briefly. These conditions can
help you to create the Bash scripts and get the results easily. The Bash script
is not limited to the conditions, as it contains many concepts. If you want to
know more about the Bash concepts, please visit Linuxhint.


About the author


Prateek Jangid

A passionate Linux user for personal and professional reasons, always exploring
what is new in the world of Linux and sharing with my readers.
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
