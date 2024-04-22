





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash If Not Operator With Examples

7 months ago
by Omar_Farooq
Bash platform is a bonus for new Linux users who want to get hands-on
experience in programming. It allows you to use any statements, loops, and
different options to get different results. One of those statements is the “if”
statement that is used to execute a part of a code until a certain condition is
true. Just like that, the “if-not” condition is also considered to do the same
things while using the exact opposition condition.
For this, we need to utilize the not operator “!” with the “if” statement in
the bash script. Let’s discuss the use of the “if-not” operator in Bash
programming with the help of some examples. Get started with the new Bash file
creation while using the terminal shell of the Ubuntu 20.04 system as per the
touch query.
$ touch ifnot.sh
$ nano ifnot.sh

Example 1

Within the first Bash example of this article, we will be using the “if-not”
operator to check which one of the two strings is less than the other. For
this, we have added the Bash support within the file and added two new string
variables v1 and v2. The value of v1 is a little greater than the value of v2.
After this, we have started the “if” statement with the “!” operator to check
the condition among the two string variables i.e., if the value of v1 is less
than v2 or not.
As we have been using the “!” operator with the “if” statement, we need to set
the results according to the situation. We have to set the echo statement to
“v2 is less than v1” for the ‘then’ part of this condition. This is because
when the “<” operator returns “false”, the “!” operator will reverse it to
“true”. After this, the else part also includes the “echo” statement to display
that “v1 is less than v2” i.e., when the condition “<” returns “true”, the “!”
will make it “false”. Let’s save this Bash code and run it on the shell.
After executing this code with Bash instruction, we have got to know that the
results will be altered according to the condition specified and are accurate.
$ bash ifnot.sh

Example 2

Let’s use the “if-not” operator to check the equality of two integer variables.
For this, we will be updating our code as shown. We have initialized two
integer variables v1 and v2 with the integer values. We have used the “if”
statement with the “not” operator to check the condition of whether the two
integer variable values are equal or not. For checking their equality, we have
been using the “-eq” operator of Bash within the condition clause. If the two
values are equal and the “-eq” operator returns “true”, the “!” operator will
reverse it and make it “false”. Thus, the “else” part will be executed stating
“EQUAL” from the echo statement.
If the condition”-eq” returns “false”, the “!” operator will make it “true” and
the echo statement from the “then” part will display “NOT EQUAL” as a result.
After running this Bash code, we have got the result “NOT EQUAL” as v1 is not
the same as v2.
$ bash ifnot.sh
Let’s update this code a little bit by adding the same value to both integer
variables i.e., v1=14 and v2=14. This time, we have also updated the inner
condition for two variables. So, we have been using the “not equal” operator
i.e., “-ne” to check if the two values are not equal. The “!” operator is also
used within the “if” statement. If the “-ne” operator returns “true” the “!”
operator will reverse it by “false” and the else part will be executed.
On the contrary, if the “-ne” operator returns “false”, the “!” operator will
make it “true” and the “then” part will be executed. According to variables,
the “then” part must be executed and display “EQUAL”.
After running this Bash code, we have come to know that the result is the same
as expected.
$ bash ifnot.sh

Example 3

Let’s try the “if-not” operator to check a different condition this time. This
time, we have been using the “-z” operator to check whether the variable is
empty or not. For this, we have started the code with the initialization of an
empty variable “v”. The “if-not” operator condition is checking whether the
variable “v” is empty or not using the “-z” option here. The condition will
display “Not Empty” upon getting the “true” from the “if-not” operator
condition. Else, it will display “Empty” after getting the “false” as a return
value from the “-z” option.
After running this Bash code, we have got “Empty” as the variable “v” is empty.
$ bash ifnot.sh

Example 4

Within our last example, we will be checking whether the simple Bash file is
located in the current home directory or other folders or not. For this, we
will be using the “-f” option within the if-not operator condition. So, we have
initialized a FILE variable with the file location as “/home/Linux/ifnot.sh”.
The “if” statement with the “!” operator will be used to reverse the result of
the condition in the square brackets. The “-f” option is checking whether the
given FILE variable contains a file or not. If so, the “then” and “else” parts
of the statement will be executed according to the condition returned value
i.e., “true” or “false”.
After executing this code, we got the “It’s a Bash file” message.
$ bash ifnot.sh

Conclusion

This article is all about the use of the “if-not” condition within the Bash
script with the use of simple Bash examples. We have tried it using many
options of Bash like “-z”, “-f”, “-ne”, -“eq”, and “<”. We have tried these
options and “if-not” conditions jointly on strings, integers, and files.


About the author


Omar Farooq

Hello Readers, I am Omar and I have been writing technical articles from last
decade. You can check out my writing pieces.
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
