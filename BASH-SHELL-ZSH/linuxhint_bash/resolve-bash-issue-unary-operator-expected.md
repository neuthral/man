





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Resolve Issue: Bash Unary Operator Expected

6 months ago
by Omar_Farooq
Errors have a diverse number of types and reasons when it comes to bash
programming. One of those errors is the “unary operator expected” error in bash
programming. When evaluating expressions in conditional declarations, you may
run into the “unary operator expected” issue. The reasons for this error “bash
unary operator expected” might be diverse. We’ll start by talking about what’s
creating the problem. Following that, we’ll go over a couple of options for
resolving this problem. Let’s get started with today’s article by creating a
new bash file in Ubuntu 20.04 system. For this, we need to utilize the “touch”
instruction within the shell terminal and name the file “unary.sh”.
$ touch unary.sh
$ nano unary.sh

Example

We will start our first example for this article by creating a new bash code in
the “unary.sh” file. We will be utilizing the conditional statement for the
illustration of this error. Within this code file, we have added the bash
support at the first line as “#!/bin/bash”. We are trying the read statement to
take input from the user with the “-p” option and add that input into the
variable “v.” The if-else statement is here to check for the condition. It is
checking whether the value inputted by a user in variable “v” is equal to the
number 14 or not. To check equality, we have been using the “-eq” comparison
operator. If the value added by a user is matched by the number 14, the “then”
part will display “Value Matched” with the help of an “echo” clause. Otherwise,
the else part is going to execute its “echo” statement displaying the “Value
not matched” message at the shell. The code is complete here, and we can
execute it now.
After saving the bash code, we executed it with the bash instruction. Turns out
it asks for the input from the user. A user has added the value “67” in the
field and pressed Enter. As the value doesn’t match with the specified value in
the “if” condition, the “else” part got executed and displayed “Value not
matched,” as presented in the output shown below.
$ bash unary.sh
This was about the use of some numerical value to perform the comparison. Let’s
execute our code once again to make it occur the “unary operator expected”
error on our shell. So, we have tried the code once again, and on the input
field asking for a value to enter, we have entered nothing (left it blank) and
pressed the “Enter” button to continue. All of a sudden, it gives us the “unary
operator expected” error in line 3 of the code. After that, it simply displayed
the message “Value not matched” using the else part of the condition mentioned
in the code.
$ bash unary.sh
Although we have encountered the error “unary operator expected” at the output
area in the terminal, we are unable to recognize the main reason for this
error. To find the main reason for this issue, we need to debug out the bash
file code. For that, we need to use the “-xv” option within the bash
instruction followed by the file name starting with. “/” as shown. It will
debug each line of our code and show the error line as well. It shows that the
error line is “[ -eq 14 ]”. It doesn’t show the “$v” as we have specified in
the code. The reason for this error is that the use of space will make the left
side expression, i.e., “$v,” disappear from the condition.
$ bash –xv ./unary.sh
To prevent this script from throwing the “unary operator expected” error on
bash, we need to update the code once again. We have to add the double quotes
around the left expression “$v,” as we have done in the image below. The rest
of the code will be unchanged for now. Now, the code is ready for use. We have
to save it first with “Ctrl+S” and exit the file with “Ctrl+X.”
After the execution of the updated bash file with the bash query, the user has
again pressed Enter without inputting any value in the input field in front of
the “Enter Something” text. Now, the unary operator expected error has been
removed, but another error,” integer expression expected,” has arisen. But it
also shows the display message that the value entered by a user doesn’t match
the number 14. So, we need to find out the solution for this error.
$ bash unary.sh
As we know that we have been using the “-eq” comparison operator to compare
some values with the integer 14. It will throw an exception because the “-eq”
comparison operator is only designed and used for the comparison of string
values or variables. To compare the numbers of integers in bash, we need to
utilize the “=” assignment operator to check whether the two values are equal
or not. Let’s save this updated code to see the result.
After this updated bash code execution, the user has again entered nothing and
simply pressed “Enter” to continue. This time, we haven’t got any errors. This
is because of the use of the “=” operator. In return, it executed the “else”
clause and displayed a “Value not matched” message.
$ bash unary.sh
Another way to avoid encountering the unary operator expected error on our
terminal shell is to use the double “square” brackets at the start and end of
the “if” condition while using the “-eq” comparison operator for any type of
value. So, we did that as shown below.
After pressing “Enter,” the user doesn’t get any error while executing.
$ bash unary.sh

Conclusion

This is all about the use of different methods to resolve the bash error “unary
operator expected.” While doing so, we have encountered another error, “integer
expression expected,” and we have resolved it as well. You can amend the above
example and resolve your bash error.


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
