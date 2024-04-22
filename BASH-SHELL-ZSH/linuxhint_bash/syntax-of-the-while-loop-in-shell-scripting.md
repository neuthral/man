





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


What is the Syntax of the While Loop in Shell Scripting?

1 year ago
by Omar_Farooq
Many of us heard about and may even have tried many of the loops and statements
in the programming world. Many types of loops exist in programming languages,
one of them is the “while” loop. This loop is used to execute the number of
lines in its “do” clause when the condition is satisfied. Let’s see some
examples of using the “while” loop with different syntaxes in the bash script.

Example 01:

The very first method of using a while loop in the bash script is with the
simple brackets. So, start by opening a shell terminal using “Ctrl+Alt+T” at
the desktop of Ubuntu 20.04. After the terminal opens, create a new bash file
in it. For file creation, use the “touch” instruction with the name of a file
having a “.sh” extension as shown in the affixed image.
$ touch bash.sh
Open this file in the terminal with the use of some editor. We recommend you to
utilize the “Nano” editor as per the below-shown instruction.
$ nano bash.sh
Within the file, add the bash extension first at the top of a file. We have set
a variable “z” with the value “2”. The while loop has been initialized to check
the condition for variable “z”. If the value of “z” is equal to or less than
10, the “do” clause will be executed. Within the “do” clause, the value of
variable “z” will be displayed with the help of the “echo” statement. Also, the
variable “z” value would be incremented by 2. The while loop ends here.
Upon running the bash file, we have got the below-shown result. The value of
variable “z” has been incremented by 2 each time until it reaches 10.
$ bash bash.sh

Example 02:

The second method to use the while loop in the bash script is with the square
brackets. So, let’s open the same file once again to update its code. After the
bash extension, we have added a variable “z” with a value of 1.  The “while”
loop has been initialized with the condition in its square brackets. The flag
“-lt” stands for “less than”. If the value of “z” is less than 10, it will
execute the “do” clause. The do clause contains an “echo” statement to print
out the variable value and increment it with 1.
Upon executing the bash code, we have got the result shown below. The value of
variable “z” has been incremented and printed out from 1 to 9.
$ bash bash.sh
Let’s change the condition in square brackets of a while loop. The flag “-le”
represents “less than and equal to”. The remaining bash code is the same. The
condition checks that if the variable is less than or equivalent to 10,
implement the “do” clause. Print out the variable value and increment it by 1.
When we have executed the bash code, it shows the result starting from 1 up to
10.
$ bash bash.sh
Let’s make another condition within the “while” loop. We have set a variable
“z” with a value of 33. Within the “while” loop, the “-gt” stands for “greater
than” here. So, it is verifying if the value of variable “z” is greater than 5
or not. If satisfied, the “do” clause will display the value of variable “z”
and decrement it by subtracting 3 from it. Otherwise, the loop ends here.
As the value 33 is greater than 5, so the value has been displayed on the
terminal and decremented by 3 until it reached near 5.
$ bash bash.sh

Example 03:

Let’s take another method to use while loop in bash script. In this method, we
will be using a file to read its data with the help of a “while” loop. Let’s
say we have a file test.txt with some text data in it, as shown below.
$ cat test.txt
Open the bash.sh file again to update it. After adding the bash extension, we
have declared a variable “file” containing the path to a file.  The “while”
loop has been initialized to read the file data. So, the model has been set to
“read”. If the file has permissions to be read out as the flag “-r” indicates,
then each line from the file would be read out using the “echo” statement
within the “do” clause.
Upon running this bash script on the terminal, we have got the data of a file
in our terminal as an output. This output data is similar to the data in the
text file “test.txt”.
$ bash bash.sh

Example 04:

Another way to use the “while” loop in a bash script is without any condition
mentioned within it. You can also use other loops or statements within it. So,
after adding the bash extension in the same file, “bash.sh”, we have
initialized a “while” loop with no conditions. Within the “do” clause of a
“while” loop, the read statement is used to get input from the user in two
variables, “x” and “y”. The variable “z” has been initialized, which is taking
the sum of both variables “x” and “y” as its value. After this, we have used
the “if” statement to check a condition that if a value of variable “x” equals
the 5, the “do” statement will be printed out. Within the “do” clause, the echo
statement will be printed out, and the loop will be broken. The “while” loop
ends here.
After running, the user has added 2 and 4 and got the sum “6” at first input.
On the second input, the user added 4 and 8 and got 13. The last input added 5
and 2 and got 7 as the sum while the loop terminates here.
$ bash bash.sh

Conclusion:

This guide contains 4 examples of the different syntaxes of using the “while”
loop within the bash script. Initially, we have elaborated on the basic
introduction of this guide. We believe that all the examples implemented here
are easy to do for every bash user.


About the author


Omar Farooq

Hello Readers, I am Omar and I have been writing technical articles from last
decade. You can check out my writing pieces.
View_all_posts

RELATED LINUX HINT POSTS


* How_to_Take_Input_From_a_User_in_Bash_Script_[Advanced_Techniques]
* 10_Cool_and_Awesome_Bash_Loop_Examples
* How_to_Handle_Command_Line_Arguments_in_Bash?
* What_are_Double_Parentheses_in_Bash
* Floating_Point_Math_in_Bash
* Bash_Continue_Built-In_Statement
* 10_Most_Important_Things_to_Know_About_Bash_Scripting

Linux Hint LLC, [email protected]
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
