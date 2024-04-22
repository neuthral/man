





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash: If, Else If, Else Examples

3 years ago
by Karim_Buzdar
Bash conditional statements are those which allow us to take some action
towards various conditions. These statements implement blocks of code, based on
whether the condition specified by the programmer evaluates to true or false.
If it evaluates to true, executes a specific block of code otherwise move to
the next condition.
There are various types of conditional statements in Bash:

  1. if statement
  2. if-else statement
  3. if..elif..else statement
  4. Nested

In this article, we will learn one of the conditional statements that is if,
elseif, else along with few examples. In several other languages, the elif is
written as “elseif” or “else if”. The elif statement helps us to make decisions
among different choices.
The syntax of if, elseif, else is:
if <test_expression>; then
  <command-to-execute>
elif <test_expression>; then
  <command-to-execute>
else
  <command-to-execute>
fi
The “if’ keyword is followed by the condition you want to check. In this if-
else-if conditional statement, the expressions are evaluated from top to
bottom.

* This is followed by “then” keyword.
* After that, if an expression is evaluated to true, corresponding
  statements are executed. If the expressions is evaluated to false, the
  corresponding statement inside the “elif” will be executed.
* If none of the conditions is true, the statement inside the else blocked is
  executed.


Example 1

The elif (else if) is used for multiple if conditions. In case if the first
condition goes false then check another “if” conditions. In the following
example, we are taking input from the user and display corresponding
statements.

* Use “if” condition to check if the marks are greater or equal to 80. If the
  condition evaluates to true, it will print “Excellent” using the “echo”
  command under “then” block.
* If the first condition evaluates to false, it will then use “elif” condition
  to check if marks are greater or equal to 70, if this evaluates to true, it
  will print “Good”.
* If none of the above conditions evaluates to true, it will move to the “else”
  condition and print “Satisfactory”.

read -p "Enter marks: " marks
if [ $marks -ge 80 ]
then
  echo "Excellent"
 
elif [ $marks -ge 60 ]
then
  echo "Good"
 
else
  echo "Satisfactory"
fi

Example 2:

For instance, we want to document the marks for a certain course. The total
marks are 200 with 100 marks for Quizzes and 100 for assignments. We want to
display the sum of assignments and quizzes while making sure the overall count
does not exceed 200.

  1. Take the input: quiz_marks and assignments_marks
  2. Make sure none of the two inputs exceed the maximum possible marks for
     each of them i.e. 100 by using the “if” and “elif” conditions.
  3. If either of the input quiz_marks or assignments_marks exceeds 100,
     display a warning message by using “echo” command.


* Please check the input marks for quiz
* Please check the input marks for assignments


  1. If none of the above condition matches, i.e. neither of the marks exceeds
     100, move to the “else” condition and display sum of marks by using the
     “echo” command.

#!/bin/bash
read -p "Enter theory marks: " quiz_marks
read -p "Enter practical marks: " assignments_marks
if (($quiz_marks > 50));
then
  echo "Please check the input marks for quiz."
elif (($assignments_marks > 50));
then
  echo "Please check the input marks for assignments."
else
  echo " Your total marks: sum=$(( quiz_marks + assignments_marks))"
fi

Example 3:

Let’s take another example of a bank account program in which we want to have
three separate outputs for 3 different situations:

* The balance is less than zero
* The balance is zero
* The balance is above zero

For instance, in the following program, use the if, elif, else statements to
display different outputs in different scenarios:

  1. Use “if” condition to check if the balance is less than zero. If this
     condition evaluates to true, display the message using the echo command:
     “Balance is less than zero, Please add more funds else you will be charged
     penalty”.
  2. If the above condition does not match, then use “elif” condition to check
     if the balance is equal to zero. If it evaluates to true, display the
     message: Balance is zero, please add funds
  3. If none of the above condition matches, use the “else” condition to
     display the: Your balance is above zero.

#!/bin/bash
Balance=900
if ((Balance < 0)); then   
  echo "Balance is less than zero, Please add more funds else you will be
charged penalty"
elif ((Balance == 0)); then
  echo "Balance is zero, please add funds"
else   
  echo "Your balance is above zero."
fi
From the above examples of the conditional statement if, elif, else, you should
now be able to understand how this conditional statement works and where it can
be used in different scenarios. I hope you liked the article.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
