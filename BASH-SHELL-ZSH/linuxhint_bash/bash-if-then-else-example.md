





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash if-else Statement

1 year ago
by Sharqa_Hameed
While working in Bash, you may need to add conditions in your script. Depending
on whether a programmer-specified boolean condition turns out to be true or
false, Bash conditional statements perform specified operations based on the
conditions. These conditional statements are utilized to execute specific
sections of your shell program.
The if, if-else, if-elif-else statements are used in Bash scripts for executing
blocks of code based on a condition outcome, just like they work in any other
programming language.
This article will go through the fundamentals of the Bash if-else Statement and
will show you how to utilize these conditional statements in your Bash script.
So let’s start!

Bash if statement

Conditional statements can be represented in various forms in a Bash script,
and the “if” statement is the most basic form of it. Have a look at the syntax
of the “if” statement:
if (condition)
then
  if block-statements
fi
To add the “if” statement in your Bash script, write out the keyword “if” and
specify the conditional expression with it. In the next line, add the “then”
keyword and write out the statements you want to execute within this block.
After adding the if block statements, close the if statement with the keyword
“fi”.

Bash if statement working

The given “if” statement block will work as follows: First of all, the program
will check the “if” statement. In case, if the specified condition is true, it
will execute block statements that come after the “then” keyword. In another
case, if the condition turns out to be false, then the program will move
forward toward the statements that come after “if” statement:

Bash if statement Example

Now, we will write a Bash script comprising the “if” statement. The script
given below will check that the number we have entered is greater than 5 or
not:
#!/bin/bash
echo -n "Enter any number of your choice: "
read NUM

if [[ $NUM -gt 5 ]]
then
  echo "The number is greater than 5."
fi
Open up your favorite text editor, and add the above-given code in a file:
Then, click on the “Save” button present at the right side of the title bar:
Save this file as a Bash shell script file by adding the extension “.sh”. We
have saved our bash script as “testfile.sh”:
Now, open up your Ubuntu terminal by pressing “CTRL+ALT+T” and execute the
below-given command in it:
$ bash testfile.sh
After executing the “testfile.sh” bash script, you will be asked to input a
number. For instance, we entered “10“. Now the “if” condition will evaluate if
the number entered by you is greater than 5, which is true in this case. So, in
the end, the “echo” command will be executed, and it will print out the
statement that the entered number is greater than “5”:
In the above-given example, the entered number fulfilled the “if” condition.
But what if we enter any number that does not match the specified condition,
what should the bash script do in such a case? The simple “if” statement will
do nothing. For instance, we have executed the same “testfile.sh” script, and
now we have input “3” which is “not” greater than “5″. We have not added any
statement to handle this condition; therefore, the output will show nothing:
In such cases, where you want to execute something when your “if” condition
evaluates “false”, step up and use the if..else statement.

Bash if-else statement

You can utilize an if-else statement in a Bashscript to execute any statement
if the specified condition is evaluated as false. Check out the syntax of the
if-else statement:
if (condition)
then
  if block statements
else
else block statements
fi
To add an if-else statement in your Bash script, start with the keyword “if”
and specify the conditional expression with it. In the next line, add the
“then” keyword and write out the statements you want to execute when the
condition turns out true. After adding the if-block statements, utilize the
keyword “else” and write out the statements which will execute in case, if the
“if” condition is not true. These statements are known as “else block
statements“. After that, close the if-else statement with the keyword “fi”.

Bash if-else statement working

First of all, the bash script will check the if statement. If the condition is
evaluated true, then the program will execute the statements present in the
“if” block. In another case, if the condition turns out to be false, then the
program will move forward towards the else block and will perform the action
specified in the “else block-Statement”:

Bash if-else statement Example

In the same “testfile.sh” script, we will add an “else” clause that will print
out a statement in case the “if” condition is “false”:
#!/bin/bash
echo -n "Enter any number of your choice: "
read NUM

if [[ $NUM -gt 5 ]]
then
  echo "The number is greater than 5."
else
  echo "The number is less than 5."
fi
Save the added changes in the “testfile.sh” and execute this bash script in
your terminal:
$ bash testfile.sh
Our “if” condition will check that the number we have entered is greater than
“5” or not. So for the first time, we will enter “6“, which makes it happen to
execute the if block-statements and the script prints out “the number is
greater than 5” on the terminal:
We have also added an “else” block; now, let’s check out if it’s working. For
this, we will enter a number smaller than 5:
The above-given output declares that the if-else statement is working fine.
What if we enter “5”?
The output will print out the “the number is less than 5,” which is not true.
To handle such conditions, we can utilize the if-elif-else statement in a
bashscript.

Bash if-elif-else statement

In a bash script, if-elif-else statement is represented in the below-given
form:
if (condition)
then
  if block-statements
elif (condition)
then
  elif block-statements
else
else block-statements
fi
To add an if-elif-else statement in your Bash script, start with the keyword
“if” and specify the conditional expression with it. In the next line, add the
“then” keyword and write out the statements you want to execute if the
condition turns out true. After adding the if-block statements, use the keyword
“elif” and specify another condition. Next, add the “then” keyword and write
out the elif block statements. Lastly, add an “else” block with the statements
executed if the specified conditions go false and close the if-elif-else
statement with the keyword “fi”.

Bash if-elif-else statement working

Here, the program will first check the “if” condition; if it is true, it will
execute the “if block-statements” and come out of the conditional structure. In
the other case, if the condition is false, it will check the condition
specified with else-if or “elif”, if that condition turns out to be true, the
bash script will execute the “elif” block statements. If none of the specified
conditions are “true“, else block statements are going to be executed:

Bash if-elif-else example

In the same “testfile.sh” script, we have added the “elif” block as follows:
#!/bin/bash
echo -n "Enter any number of your choice: "
read NUM

if [[ $NUM -gt 5 ]]
then
  echo "The number is greater than 5."
elif [[ $NUM -eq 5 ]]
then
  echo "The number is equal to 5."
else
  echo "The number is less than 5."  
fi
The “elif” block will check if the entered number is equal to 5:
Save this “testfile.sh” script and execute it in your terminal:
$ bash testfile.sh
We will enter “6” for the first time, which is greater than “5”. In this case,
the “if block-statements” will be executed:
Now, let’s enter a number smaller than “5”:
So, what about the “elif” statement? Now, we will enter input “5” to check the
working of “elif” block:
The output shows us that our program executed the statement added inside the
“elif” block for the entered number.

Conclusion

One of the essential principles in computer programming is decision-making. As
in other programming languages, if statement, if-else, and if-elif-else
statements are used in Bashto execute code based on specific conditions. This
article showed you how to use if, if-else, if-elif-else statements in bash
script with syntax and examples. If you need to handle conditions in your bash
script, try out if-else statements.


About the author


Sharqa Hameed

I am a Linux enthusiast, I love to read Every Linux blog on the internet. I
hold masters degree in computer science and am passionate about learning and
teaching.
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
