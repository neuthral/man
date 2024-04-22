





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


What is the “Does Not Equal” Sign in Bash? How To Use It

1 year ago
by Aqsa_Yasin
The not equal “-ne” controller inside the Linux Bash programming language
compares two possible values when they’re not equivalent. The not equal
function in Ubuntu bash is denoted by the symbol “-ne,” which would be the
initial character of “not equal.” Also included is the “!=” operator that is
used to indicate the not equal condition. The exclamation point, i.e., “!=” is
also commonly used in certain computer languages to indicate that something is
not equal. In addition, for the not equal expression to operate, it must be
enclosed by brackets [[…]]. The not equal operation yields a boolean result of
True or False. The not equal expression is often used in conjunction only with
if or elif expressions to check for equality and run instructions.

Example 01:

Let’s see how not equal sign works in bash. For this purpose, let’s login from
the Linux operating system first. In our case, we have been working on Ubuntu
20.04. After the successful login, launch the console application named
“terminal” at your desktop by “Ctrl+Alt+T”. Alternatively, you can explore it
from the Activity menu bar and search it using the search bar. The terminal app
has been launched successfully; we will create a new bash file to save the bash
code within it. So, we have made a bash file named “test.sh” with the built-in
“touch” query as below.
$ touch test.sh
When you are done with file creation, open this file in any of the editors
already built-in or installed in your Linux system. In our case, we have GNU
editor configured in our Ubuntu 20.04. Hence, we have been opening the
“test.sh” file with the nano query as follows:
$ nano test.sh
You will see that the newly created bash file will be opened via GNU editor.
Now write the code shown in the image below within your bash file. So, we have
added the bash extension first. After that, we have declared a variable “val”
having a string value “Aqsa”. Within the “if” statement, we have declared a
condition. We’ll make a string element $val and compare it to the string
“Aqsa”. Throughout this instance, we’ll see whether the provided text bash
variable “val” isn’t identical to the specified string “Aqsa”. If the condition
satisfies and both the values are not matched, it will run the first echo
statement. Otherwise, it will execute the other part of a code and end the “if-
else” statement. When comparing text types, the -ne operator couldn’t be cast-
off; alternatively, the “!=” operator must always be castoff. So, you can see
that we have used “!=” instead of “-new” here in the code below. Save this code
with “Ctrl+S” while quit via the “Ctrl+X” shortcut method.
When the bash file was executed within the terminal, it displayed the other
part of the code because the condition wasn’t satisfied. As for conditions to
be true, there must be not equal string type values. Therefore, we got the
output “It’s Equal”.
$ bash test.sh
Open the bash file once again with the “nano” query. The only change is to be
done in the “if-statement” is within the “brackets”. We have just changed the
string “Aqsa” to “Aqsaa”. Now the variable value “Aqsa” and this string “Aqsaa”
don’t meet each other equally. The condition doesn’t meet here. Therefore, the
echo part of the “then” clause must be executed and print “It’s Not Equal”
within the terminal. Let’s save the bash code once more and quit the Editor.
Upon the successful execution of the bash file via bash command, it printed out
“It’s Not Equal” as expected.
$ bash test.sh

Example 02:

Let’s have a different look at code this time. There is a little different
here. We have been using the two variables to be compared this time. We have
named these string variables as “fname” and “lname” with different values,
e.g., “Aqsa” and “Yasin”. Now, within the “if” statement condition part, we
have used both variables to compare via the not equal “!=” operator. If the
condition satisfies, it will implement the echo statement of the “then” part.
Or else, it will run the “echo” part of the “else” statement.
Upon running the test.sh bash document in the terminal, we have got the result
of the first echo statement “Names are not Equal” as per condition satisfied.
$ bash test.sh
Let’s see what happens when we use “-ne” instead of “!=” within the bash code
while comparing the string type variables. Open the test.sh bash file once more
with nano instruction. After the file is opened, replace the “!=” part of the
“if” statement condition line with “-ne”. The remaining code will be the same,
and there will be no change in it.
This time, when we have executed the bash code, it gets us an exception in the
terminal saying “integer expression expected”. This means that the “-ne”
operator must only be used for integer types of variables for comparison. On
the other hand, it also shows the wrong output “Names are Equal”, and it’s a
big error.
$ bash test.sh

Example 03:

This time we will be using the integer type variables to compare the “-ne”
operator instead of the “!=” operator in the example. So, we have initialized
“val1” and “val2” integer-type variables with numerical values. Then we have
used these variables in the “if” condition clause to have a “-ne” comparison.
The remaining code is the same with the minor changes.
As the val1 and val2 variables have different numerical values, the execution
displays that the “Numbers are Not Equal”.
$ bash test.sh

Example 04:

We have used the single word string type values or some integer types in all
the above instances. This time we will be using a long string or sentence
within the variable to get compared. After opening the bash file, we have
declared two string type variables, “s1” and “s2” with the same string values.
This time we have assigned the long sentence as value to both variables, e.g.,
“Aqsa Yasin is a Content Writer”. We have compared both variables with the “!=”
operator within the if statement and in the bracket section as both variables
are string types.
As the condition goes wrong, that’s why it prints “Strings are Equal”.
$ bash test.sh

Example 05:

Within our last example, we have declared two variables having emails as their
string values to be compared. In a single glance, you will not be able to
indicate an error, but both values are not the same. The rest of the code
doesn’t change. Save the code and turn towards the terminal.
As the emails are not equal, it executed the first echo statement of then
clause saying “Mails are Not Equal”, once the file has been executed in the
shell with the “bash” query.
$ bash test.sh

Conclusion:

In this simple guide, we have seen many instances for the working of not the
equal operator. We have elaborated these examples for the string and integer
type variables. We hope this article will be beneficial and easy to do for you.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
