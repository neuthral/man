





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Expr Command

1 year ago
by Omar_Farooq
The “expr” or expression instruction has been very well-known among bash users
to evaluate certain expressions and give the results. These expressions contain
more than 1 argument within. The expression could be of any type, i.e., string,
integer, or regex. The type of expression defines what sort of operation can be
performed. In this article, we will be discussing the “expr” command in bash
script within Ubuntu 20.04 system. Open the shell terminal first.

Expr on Integers:

Let’s start using the expression commands for integer type values. So, within
the terminal shell, we have tried to make subtraction between two integer
values, i.e., 14 and 9, using the “expr” command. The output shows the
subtraction value, i.e., 5.
$ expr 14 - 9
To use the “expr” command for addition, you must add “+” between the integer
values. The “expr” command will calculate the sum 23 of both values 14 and 9.
$ expr 14 + 9
Let’s use the “expr” command to divide two integer values. We have used
“/” sign between the values along with the “expr” keyword. We got “5” as a
resultant value.
$ expr 15 / 3
To multiply two integer values with the help of an “expr” command, you have to
use the “*” sign along with the “\” sign. Without the “\” sign, it will not
calculate the multiplication of integers. As a result, it displayed the value
45 as a multiplication result.
$ expr 15 \* 3
Let’s have a look at the “expr” command to use it within the bash file instead
of directly using it on the terminal shell. So, create a new bash file with the
touch query as shown below.
$ touch bash.sh
Open the newly created bash file using the “nano” editor with the keyword
“nano”.
$ nano bash.sh

Example 01:

Add the bash extension at the top of a file. We have added two read statements
to get input from a user and save it to the variables v1 and v2. The variable
“res” has been used to apply the “expr” command to calculate the sum of both
variables. The sum of both integer variables would be displayed on the shell
using the variable “res”.
The user added two integer values. The sum “7” has been calculated via the
“expr” command.
$ bash bash.sh

Example 02:

Let’s have a new example of using the “expr” command to check new conditions on
integers. Open the same bash file. The overall code is the same again. Only the
variable “res” containing the “expr” command would be changed a little. So, we
have added the “=” sign to check if the two integers added by a user are equal
or not. If the condition for equality of both integers satisfies, it will
return 1 to the variable “res” else return 0. The values returned in the
variable “res” would be displayed on the shell with the help of an echo clause.
Upon running the code the first time, the user added 7 and 4 as input. As a
result, the “expr” command returned 0 as the values entered by the user are not
equal.
$ bash bash.sh
The user has added the same integers upon running the code once again. The
“expr” returned 1, as the values matched.
$ bash bash.sh

Example 03:

We will be using the “expr” command to check one or more expressions within
this example. Two two read statements are getting integer values as input. The
variable “a” is using the “expr” to check whether the value “v1” is less than
the value v2. The variable “b’ is using the “expr” command to see if the value
v1 is equal to value v2. The variable “c” is using the “expr” command to check
if any of the variables “a” or “b” expressions turned out to be true. If any of
the conditions satisfy, it will return 1; else, return 0.
Upon running this code, the user added 45 to v1 and 66 to v2. As v1 is less
than v2, so It returns 1 to variable “a”. While the values are not equal, it
returns 0 to variable “b”. At last, the variable “c” got true because one of
the variable expressions was true according to the condition.
$ bash bash.sh

Expr on Strings:

Let’s have a look at the examples to see how the “expr” command is on the
strings. So, open the bash file once again using the nano command.

Example 01:

Add the bash extension at the top of a bash file. We have declared a variable
“var” with a string value “Ubuntu20”. Then, we have declared a variable “z”
using the “expr” command between it to get the length of a variable “var”. The
echo statement has been used here to display the value stored in the variable
“z” i.e., length of a variable “var”.
On running the bash file, the “expr” command calculated the length of a string
variable “var” and displayed it on the terminal, i.e., 8.
$ bash bash.sh

Example 02:

To calculate the index of some specific character from a variable, you can also
use the “expr” command. So, open the same file to update it again. All the code
remains the same, but the expression “expr” has to be changed. Now, we have
been using the keyword “index” instead of length to calculate the index of a
character “t” from the variable “var”. Now, this expression will get the
character “t” index number and display it on the terminal via the echo
statement.
 
Upon running the code, we have got 5 as an index of character “t”.
$ bash bash.sh

g

Let’s make a substring from the variable “var” using the “expr” command. Update
the code file with the keyword “substr” to create a substring from index 2 to 5
of variable “var”. Other code remains the same.
After running this code, we have got a substring “buntu” as a result.
$ bash bash.sh

Conclusion:

This article contains many examples for implementing the “expr” command on the
strings and integers separately in the bash script. We hope this article will
help you a lot to clear your doubts and get a better hands-on experience on the
bash “expr” command.


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
