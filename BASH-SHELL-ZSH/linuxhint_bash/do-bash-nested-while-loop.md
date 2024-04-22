





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Do Bash Nested While Loop

11 months ago
by Omar_Farooq
The loops are quite well-known in most programming languages to iterate the
data or increment or decrement the values in the code. The loops can be used
alone or in nested forms. One of the most famous loops used in programming is
the “While” loop. This loop continues to get executed until the mentioned
condition is satisfying. Within this guide, we will be deliberating the way to
use the nested “while” loop in bash programming. As most of our work would be
through a terminal, so we need to open it first. Hence, we are trying the
shortcut key “Ctrl+Alt+T” to open the terminal shell application of the Ubuntu
20.04 system.
Let’s start creating a nested “while” loop in the bash script of Ubuntu 20.04.
This will be started from the creation of a new file in a terminal with the
help of a simple touch query with the bash file name. The file name is
“new.sh”. This file is now held at the home folder of our Ubuntu 20.04 system.
We need to open it within some editor to add bash code. So, we have been
utilizing the “GNU Nano” editor for this purpose. This file has been opened
with the help of a simple “nano” instruction and quickly opens it within the
editor. Both the touch and nano instructions are shown in the attached
screenshot picture.

Example 01: Simple While Loop

The very first example will only explain the single while loop in bash. The
empty nano editor is opened via the terminal shell. It’s time to add some bash
code to it. We have started our bash code with the bash extension i.e. “#!/bin/
sh”. We have adjusted a variable “var” with a value of 5. The while loop has
been started with square brackets around its condition. It is using the
comparison operator “lt” to test if the variable “var” value is less than value
10. As the condition is true, it will execute the “do” part until “done”. So,
within the while loop, it has been using the echo statement to display the
variable value. The next consecutive line is incrementing the variable “var”
value by 1 each time the condition meets. The script ends here.
Let’s just run the single while loop code in the terminal with the “bash”
command as below. It will increment the variable value until it equals 10 and
then stop. You can see the output below.

Example 02: Nested While Loop

Let’s have our second example which will show us how to use the nested while
loop in bash. So, the code has been started with the same bash extension in the
nano bash file. The iterator “i” has been set to 0. The while loop has been
started with these square brackets shown in the code. It is using the variable
“i’ to check whether it is less than 10 or not via the comparison operator
“lt”. As the condition meets i.e., 0 is less than 10, it will execute the “do”
part of a loop. The do part contains an echo statement to display the variable
“i” current value and an increment statement to increment the value of variable
‘i’ by 3. This incremented value will be saved again to the variable ‘I’.
The next inner “while” loop will not be executed as the condition in it doesn’t
meet i.e., 3 does not equal to 6. So, the outer while loop will continue to
execute until it reaches the value 6. In its 3rd iteration, the value will
reach 6 and the inner “while” loop will be executed as the condition satisfies.
Within the inner “while” loop, we have got two echo statements. One is to show
the current iteration or variable “i” value. The second statement is to tell
that the variable “i” value will be decremented by 2 from now. After both echo
statements, we have used the decrement statement to decrement the current value
of the variable “i” by 2 and save it again to it. Both the loops end here as
the program is completed.
After the execution, the outer “while” loop got executed 3 times and displayed
0,3,6. When the value of “i” reached 6 by increment, it executed the inner
“while” loop. The current value “6” of the “i” variable is decremented by 2 and
the control is given to the outer loop again. The outer loop displayed the
decremented value “4” and then incremented it by 3. Now the value is “7” and
displayed. The inner “while” loop will not be executed as the value “7” doesn’t
equal “6.”. So, the outer loop is again executed and now the value becomes 10
by an increment of 3. Here the outer loop stops as the conditions meet i.e.,
the value of “I” is equal to 10.

Example 03: Nested While Loop

Here comes the last example. We have initialized a variable “var” with a value
of 2. The bash code contains nested “while” loops i.e., inner and outer. The
outer loop checks if the “var” value is less than 20, it will display that
value and increment it by 2 until it reached 20. The inner loop is utilizing
the equal operator to check whether the value is equal to 20 or not. If so,
then it will display that value and display the message that the loop is ending
here. The break statement is used here to simply quit the program here.
The execution of this bash program shows that the initial value “2” has been
increment by 2 until it reaches 20. After that, the program has been stopped as
per the break statement.

Conclusion:

This guide has emerged with the illustration of implementing the nested “while”
loop in Bash script. We have not only used the examples of nested “while” loop
but also the single “while” loop to demonstrate it more. The examples contain
simple comparison operators to do the task.


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
