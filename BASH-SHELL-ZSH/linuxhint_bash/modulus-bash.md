





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Modulus in Bash?

1 year ago
by Omar_Farooq
In mathematics, the modulo operator is widely known to determine the remainder
of two values upon division. This mathematical operator can also be used in the
bash script. Therefore, we will see how a modulo operator can be used in bash
with different ways to get the remainder. Let’s start by logging in from the
Ubuntu 20.04 system. Try “Ctrl+Alt+T” to launch the shell terminal on the
Ubuntu desktop. Let’s have a few examples.

Example 01:

Let’s start with the first example of simply using the modulo operator on the
terminal itself. To use modulo in the shell, we have to utilize the “expr”
command to evaluate its value. So, we have consecutively added three “expr”
commands to find out the modulo of two integer values each time by using the
“%” operator between them and got three remainder values.
$ expr 79 % 12

$ expr 89 % 12

$ expr 99 % 12

Example 02:

Let’s see how a modulus operator can be used within the bash script while using
the bash files. So, we have created a new file, “modulo.sh” and opened it
within the “GNU Nano” editor.
$ touch modulo.sh

$ nano modulo.sh
You need to add the bash extension first within the file, i.e., “#!/bin/bash”.
After that, we have two variables, “a” and “b” and assigned integer values to
both. Another variable, “res” has been using the modulo operator to calculate
the modulus of both variables, i.e., a and b. At last, the echo statement is
used here to show the remainder of both variables calculated by a modulo
operator within the shell terminal.
When we run this code, it will display 1 as the remainder to values 10 and 3.
$ bash modulo.sh

Example 03:

To make our code more interactive, let’s take values from the user as input.
So, we have added the bash extension. Two read statements have been used here
to get input from the user and save to the variables “a” and “b”. Input must be
an integer type. The “res” variable has been calculating the remainder by using
the modulo operator, displaying the echo command.
After running this code the first time, a user added 17 and 3 and got 2 as the
remainder.
$ bash modulo.sh
Upon running this code a second time, the user added 53 and 3 as input and got
2 as modulus.
$ bash modulo.sh

Example 04:

Let’s begin to use the modulus in some loops within the bash script. So, open
the same file once again to update the code. After adding the bash extension,
we have initialized a “for” loop ranging from value 3 to 43. Within it, the
“if” statement has been utilized to evaluate the expression. The “expr” command
has been used here to calculate the remainder using the modulo operator on the
defined range on each iterator divided by “2”. The “if” statement has been
checking that if the remainder of the expression does not equal to “0”, then it
will continue to print out the particular range value via the “echo” statement.
The “for” loop ends after the “if” statement.
After running the file modulo.sh on the shell with the bash command, we got the
following result below. As all the even numbers of the range were completely
divisible by “2” and got “0” remainder, that is why the “echo” statement
doesn’t display them on the shell. While all the odd numbers were not
completely divisible by “2”, hence they are printed out.
$ bash modulo.sh

Example 05:

If somebody wants to display the remainder as well, this example is for him/her
as we didn’t display the remainder in the previous example. The code starts by
taking integer values as an input from the user and saving them to the variable
“a”. The “rem” variable uses the modulo operator to calculate the remainder of
value “a” divided by 2. The echo statement displays the remainder. If the
“remainder” equals “0”, it will display the success message; otherwise, the
failure message on the shell uses the echo statements in “if” and “else”
clauses.
The user added 8 as an input and got “0” as the remainder upon running the
code. So, it got a success message.
$ bash modulo.sh
While running the code a second time, the user added 14 as input and got 1 as
its remainder. Hence, it got the “not completely divisible” message.
$ bash modulo.sh
This whole time, we used the same divisor, i.e., 2. Let’s change the divisor.
So, open the same file and update it to “7” as per the snap image beneath. The
remaining code is the same. Save your updated bash code to see the results.
After running the updated file, the user added “89” as a dividend. As a result,
when divided by “7”, it got “5” as remainder. Therefore, the “not completely
divisible” statement got executed.
$ bash modulo.sh
While running it again, the user added 77 as input and got 0 as a reminder,
i.e., completely divisible.
$ bash modulo.sh

Example 06:

Let’s have our last and most significant example to get the user’s dividend and
divisor value. So, the “read” statement has been used here for this purpose.
The dividend value has been saved to the variable “a” and the divisor value
would be saved to variable “b”. The “if” statement has been used to make a
condition. The “expr” command is used to get the modulus of both values, i.e.,
a and b. The “if” statement checks if the remainder is equivalent to 0 or not.
If equals, it will print the “echo” statement of the “if” clause, otherwise of
the “else” clause.
After running this code, the user added 77 as input divided and 4 as a divisor.
The remainder wasn’t equal to 0, so it displayed the “echo” statement of the
“else” clause.
$ bash modulo.sh

Conclusion:

This article would be really helpful to bash users when calculating the
remainder of some mathematical values with the modulus operator in the shell.
All the examples are easy and explained very well for better understanding.


About the author


Omar Farooq

Hello Readers, I am Omar and I have been writing technical articles from last
decade. You can check out my writing pieces.
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
