





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to write a ‘for’ Loop in a Shell Script

1 year ago
by Omar_Farooq
The “For” loop is the most used and well-known loop in the programming field.
Also, it is the easiest loop to be utilized in the codes. It operates on some
list of values that are defined in it or out of it.  The “for” loop can be
defined in bracket-style or without brackets as per your choice. Today, we will
be learning to write and use the “for” loop within the shell script while
working on Ubuntu 20.04. So, let’s start your learning by Login from the system
and launch the console shell application on it employing “Ctrl+Alt+T”.

Example 01

Let’s look at the “for” loop in a shell script without writing it in a file. To
start a shell script, you need to add a bash extension with the hash sign.
After that, we have started a “for” loop in the next line. The “for” loop must
contain some variable. In our case, this variable is “I”. This variable is part
of a loop to execute values, e.g., 2, 4, 6, 8, 10. After that, the “do”
statement will tell us what to do upon the loop got executed. In this example,
it will display a text along with the variable value until the loop ends. The
“done” clause shows that the “for” loop has been ended. Hence, it displays the
5 statements containing the 5 different values that are being used in the loop.
#! /bin/sh

Example 02

Another way to use the “for” loop in the shell script is via some files. So, we
have generated a bash file named “bash.sh”. The file contains another way to
write the “for” loop in the script. This is the most used and old way to write
the “for” loop in another programming language other than bash. The loop starts
from 1 and ends on 10 while incrementing by value 1. Until the loop ends, it
will display the text “Displaying line:$i” using the “echo” line within the
“do” clause. The done clause demonstrated that the loop had been ended.
Run the file using the “bash” query as displayed on the image. The loop has
been executed 10 times, and every time it displays the new line.
$ bash bash.sh

Example 03

There is another way to define list items in the “for” loop that has been
displayed in the snap below. The list contains an initial value of “3” that
would be ended on “15” and must be incremented by 3. This means the initial
value “3” will be incremented by integer “3” until it becomes 15. The echo
statement within the “for” loop will display every value each time the value
has been incremented.
Upon executing a file, we got the 5 results as the loop has been executed 5
times. The output shows that the initial value is 3 incremented by “3” every
time, and the final value is 15.
$ bash bash.sh
Let’s create a table of “6” by using the very same syntax of the “for” loop.
The table must end on “60” and increment by “6”. Each incremented value will be
saved in variable “var” and will be displayed.
After successfully executing the updated shell script file, we have got the
table of 6 up to 60 that can be seen in the screenshot picture below.
$ bash bash.sh

Example 04

Let’s see how the loop operates on the “if” statements upon declared or used
within it. So, we have been using the most used syntax of declaring the “for”
loop, i.e., within the brackets. The loop starts from 1 and ends on 10. Within
the “do” clause, if the statement has been utilized to check the condition. If
any of the values from the loop list matched the integer “6”, the loop must
break. Otherwise, the loop continues to display the loop list value in the
shell.
After running the bash file in the shell, we have found that the integer “6”
matches the loop value and displays only the first 5 loop list items. The loop
breaks after the condition got met on the 6th increment.
$ bash bash.sh
Let’s use the for loop with its another syntax while using a list of fruit
values. The “if” statement is utilized to check if the list contains the fruit
“mango” in it. If the list contains the specified value, it will execute the
echo statement within the “then” clause stating: “Fruit matched is mango”. The
loop must break here. Otherwise, the loop will continue to be executed and
display the relevant fruit value until it reaches the end list value.
After running the code, it displays the first three list items, and then
conditions got met. Thus, it stated that the “Fruit matched is mango” and the
loop breaks.

Example 05

We can also use the array list in the “for” loop. So, we have declared the
string type array “Names” in the code below. The “for” loop has been using the
array “Names” to display its contents by utilizing the “echo” statement in the
“do” clause.
The output for this code displays the array values one by one, i.e., names.
$ bash bash.sh

Example 06

We can also utilize the simple “for” loop in a shell script to list the files.
So, we have been searching and displaying all the “bash” files in the root
directory of our system, i.e., HOME.
Upon the execution of the above code, we have got three Files from our system.
$ bash file.sh
Let’s search for all the text files in the Home directory of a system using the
code shown below.
The output indicates that our system has got three text files in its home
folder.
$ bash file.sh

Conclusion

This article contains the different ways to write and use the “for” loop in the
bash shell script. It also demonstrates the simple examples to use “if”
statements, arrays, lists, strings, and integers within the “for” loop to
perform different operations. So, this article is a bonus gift to our Linux
users.


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
