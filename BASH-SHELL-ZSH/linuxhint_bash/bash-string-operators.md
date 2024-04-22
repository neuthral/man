





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash String Operators

7 months ago
by Omar_Farooq
As we already know that the Bash string values are the group of words or
characters. To manipulate string variables and values, Bash provides us with
many functions and operators. If you are new to Bash programming and string
manipulation, then this simple article is meant for your help. Within this
guide today, we will be utilizing and discussing some of the most-used string
Bash operators specially designed for string manipulation in Bash programming.
Let’s get started with some of the examples to see the working of these
operators. Start with the Bash file creation as we have to code in Bash. The
“touch” instruction can be a plus to use here in Ubuntu 20.04. We prefer to use
the Gnu Nano editor to open the Bash file and create code in it. You can use
the text editor or vim editor as well.
$ touch string.sh
$ nano string.sh

Example 01: Comparison Operator

We have started our first example of using the comparison operator for strings
in C#. The empty file has been started with the bash support “#!/bin/bash”. We
have initialized two string variables s1 and s2 with string values. Both the
string values for these variables are equal in length but different in case
i.e., first has all uppercase letters while the other has only the first letter
capital for a single word. We have been using the “if-else” statement to check
the condition i.e., comparison among two strings if they are equal or not.  The
comparison operator “=” has been used within the “if” condition between the
curly brackets to check whether the variable s1 is equal to s2 or not.
If the condition satisfies and returns “true”, then part of the statement will
execute its echo statement stating “s1 and s2 are the same”. Else, the “else”
part will execute its echo statement stating “Not Same”. The if-else statement
will be completed here and the code is now ready for execution.
After running this Bash file on the shell via the “bash” instruction, we have
got to know that the strings are not equal to each other using the comparison
operator in the condition.
$ bash string.sh
Let’s update this code to see a result for the “Not Equal” comparison operator
i.e. “!=” among the very same two string variables. So, we have opened the file
and updated the value of s2 with the value same as the value of variable s1
i.e., HELLO WORLD with all capital letters. We have replaced the Equal “=”
operator with the Not Equal “!=” operator within the “if” statement condition
between the variables i.e., s1 and s2. We have also updated the “then” and
“else” parts of the statement by interchanging the “echo” statement results.
If the condition returns true (s1 is not equal to s2), it will display the
message “Not Same” by executing the “echo” statement from the “then” part.
Otherwise, it will execute the “else” part of the statement and display “Same”
as the text message using the “echo” statement.
After executing this updated Bash code, our else part from this program got
executed i.e., “Same”, because both the strings are now equal in size and
syntax.
$ bash string.sh
Other comparison operators for a string in Bash are “less than” and “greater
than” operators. These operators lexicographically (according to alphabetical
order) check the strings and return its result. So, within the below-shown Bash
code, we have initialized two string variables with half similar values. The
“if-else” nested statement has been used to check strings “lexicographically”.
As the second string v2 is lexicographically less than the string v1, it will
be displaying the “elif” part of the statement i.e., “v2 is less than v1”. If
the condition goes “false” there is a possibility that the else part of the
statement got executed.
After running this code, we have found out that the v2 string is
lexicographically lesser than string v1 i.e., alphabetically contains fewer
characters as compared to string v1.
$ bash string.sh

Example 02: “-z” Operator

Let’s get started with the “-z” operator to check if the given string variable
is empty or not. So, we have been using a single variable of string type “s1”
that has been initialized with a string value. The “if-else” statement is here
to use the “-z” operator within the “if” condition before the string variable
“s1”. If the condition returns “true” as a result of “-z” to check the
emptiness, the “then” part will execute its echo statement stating that the
string is “Empty!”. Otherwise, the else part will be executed stating that the
string is “Not Empty”.
After running this Bash code in the Bash shell, we have come to know that the
string “s1” is not empty as it contains the string value “HELLO WORLD” in it.
$ bash string.sh

Example 03: “-n” Operator

The “-n” operator works quite the same as the “-z” operator does i.e., checking
the emptiness of a string. But, the rule of checking the emptiness is different
from the above example. It will be checking for the string length to determine
the emptiness of a string.
For instance, within the below code, we have been using the operator “-n” to
check the emptiness of a string “s1”. The operator “-n” will check whether the
length of a string is non-zero or not. If the string length is non-zero, it
will display that the string is “Not Empty”. Otherwise, it will display that
the string variable “s1” is “Empty”.
After using this “-z” operator, we now know that the variable “s1” is not
Empty.
$ bash string.sh

Conclusion

It was all about the use of different Bash operators for strings in Bash
programming using different and unique examples. We have discussed different
comparison operators i.e., “=”, “!=”, “<” and “>”, and tried the operators “-
z”, and “-n” for a string value to check different properties. We hope this
article will be useful for you.


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
