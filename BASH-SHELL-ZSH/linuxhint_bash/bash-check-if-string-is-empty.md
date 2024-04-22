





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Check If String Is Empty

6 months ago
by Omar_Farooq
While coding in any programming language, we use many variables of different
types. One well-known and most used variable type is the “string”. The string
is a group of characters and special symbols including space in programming.
While working in Linux provides us the opportunity to utilize string variables
in our code. Today, we will demonstrate some of the examples to check whether a
string variable is empty or not using some of the most well-known Bash options.
So, let’s get started now. Let’s start with the Bash file creation, as all of
our work will be done within the Bash file. So, use the “touch” instruction of
Ubuntu to create a Bash file named “empty” with the “sh” extension. The GNU
Nano editor can be utilized to open this newly created Bash file.

Example 01:

We will be starting from the most basic illustration of checking whether the
string is empty or not. For this, we will be using the assignment operator
within the “if-else” statement to state the condition. First, we have added a
Bash support “#!/bin/bash” in our code file. After this, we have initialized an
empty string variable “str” using the assignment operator and double inverted
commas. Here, the “if-else” statement states our condition and its result
according to the returned value.
We have started the “if” clause with square brackets to add our condition. We
have been using the double inverted commas to state the string variable “str”
with the “$” sign and utilizing the assignment operator “=” to check whether
it’s empty or not. If the condition is satisfied, the “then” part of the
statement will execute the echo statement stating that the string is “Empty”.
Otherwise, the “else” part of the statement will run the “echo” statement
stating that the string is “Not Empty”. The if-else statement ends at “fi”.
Save your code using “Ctrl+S” and quit this editor utilizing the Ctrl+X
shortcut. Coming back to the terminal, we are using the Bash instruction to run
this Bash file, i.e., empty.sh. On execution, it returns “Empty” because the
string “str” is initialized empty in the code, and the “then” part of the “if-
else” statement has been executed so far.
$ bash empty.sh

Example 02

Let’s look at another option, “-z”, used so far in Bash to check for the empty
string. The code has been started with Bash support, and we have initialized a
string variable “v” with the value “Hello” in it. Then, we started the “if-
else” statement to check whether the string is empty. For this, we have used
the “-z” option within the square brackets condition of the “if” part of the
statement and stated the variable “V” with the “$” sign in inverted commas. If
the condition is satisfied and the string is found empty, the “then” part will
get executed, and the echo statement will display “String v is empty”. On the
contrary, if the string is not empty, the else part will be executed, and the
echo statement will display “String v is not Empty”.
After saving this file, we exited the editor and executed the code using the
Bash query shown below. It turns out that the string is not empty, and the
“else” part of the statement was executed. This shows that the “-z” option
works perfectly fine to check for a string emptiness.
$ bash empty.sh

Example 03

Here is another option, “-n”, to check whether the specified string is empty or
not. It works on the rule of checking the length of a string by counting the
string characters in it. If the length of a particular string turns out to be
other than zero, it will return “true”; otherwise, it will return “false”.
Let’s get started with the use of the “-n” option in our illustration now. So,
we have initialized an empty string variable “val” first. After this, we have
been using the “-n” option within the “if” part of the “if-else” statement
within the square brackets. This option is checking whether the length of
variable “val” is other than zero or not. If the length of variable “val” is
other than zero, the “-n” option will return true, and the “then” part of the
statement will get executed.
The echo statement will display the message “String val is not Empty”. But, if
the statement returns “false”, the else part will execute its echo statement
and show the message “String val is empty”. As our string “val” is empty, we
expect it to execute its else part.
When we have executed our code with Bash instruction after saving the code, we
have the result as we expected, i.e., “String val is empty”.

Example 04

You can also use the “test” method to check for the string emptiness, as shown
below. Within this method, you need to test the variable using the “$” sign
before the curly brackets around the variable name “val”. Within the curly
brackets, you need to use the variable name “val” and the keyword “test”
separated from each other by “:” as shown. It will work the same as the
previously explained options in the examples.
The following result will be shown according to the variable “val”.
$ bash empty.sh

Conclusion:

This article is all about using different options of Bash to check for the
emptiness of some strings. We have created simple Bash scripts using the
variables and if-else statements. Within the codes, we have used different
options of Bash like “-n”, “-z”, and “=” assignment operators to check for the
string emptiness. The results are displayed according to the cases. We hope you
found this article helpful. Check the other Linux Hint articles for more tips
and tutorials.


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
