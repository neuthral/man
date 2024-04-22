





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Break from a Bash While Loop?

2 years ago
by Aqsa_Yasin
Loops are an extremely useful means of performing repetitive tasks not only in
Bash scripting but also in all other programming languages. It enables us to
write a task (that is supposed to occur multiple times) at once and enclose it
within any desired loop so that the said task can be performed repeatedly.
Different loops are used in every programming language, i.e., multiple types of
loops can be used with every programming language. Amongst all types, the most
frequently used loops are the “for” loop and the “while” loop.
A major difference between the execution of the “for” loop and the “while” loop
is that in the former one, the incrementing or decrementing variable is
specified with the loop whereas, in the latter, that variable is specified
after the task that is supposed to be performed repeatedly is stated. The
“while” loops appear to be more convenient for the programmers syntactically.
The concept of infinite loops in every programming language is also very
common, i.e., a loop that never terminates and its condition assesses to be
always “true”. At times, these loops are written accidentally by the
programmers, however, there are situations in which such loops are written
deliberately. Either way, there can be certain conditions in which we want that
infinite loop to break.
Apart from the scenario that we have discussed above, there are times that we
purposely create finite loops that we want to run based on a specific
condition, wherein we want the normal flow of that loop to break. For both
scenarios, there should be a proper mechanism in which we can break a loop
whenever a certain specified condition is met.
We can achieve this objective using the “break” statement with our loops
regardless of whether they are finite or infinite. Since the “while” loop is
one of the most commonly used loops in any programming language, therefore, we
will see how we can break from the a “while” loop in Bash in Linux Mint 20 by
sharing an example of Bash script with you.

Example Script for Breaking from a Bash While Loop in Linux Mint 20

For demonstrating the usage of the “break” command in Bash, you have to create
a Bash file in your Home directory. In our case, we have entitled it as
“BreakWhile.sh”. You can also have any other name for this Bash file. Once this
file is created, you have to open it up with any text editor and then write
down the script shown in the following image:
In this script, we have defined a variable named “number” and initialized it
with the value “1”. Then we have a “while” loop whose iterating condition is
that the value of the variable “number” should be less than 10, i.e., this loop
will keep iterating until the value of the “number” variable is less than 10.
Then in the do-done block, we have an “if” statement whose condition is that
whenever the value of the “number” variable will be equal to “9”, our “while”
loop will break. Otherwise, it will keep running. Then we have simply printed
the value of the “number” variable for each iteration of our “while” loop.
Finally, we have incremented the value of our “number” variable, i.e., the
value of our “number” variable will exceed one after every iteration of our
“while” loop. The above script will result in a situation in which the number
“9” will never be printed since when the value of our “number” variable will be
incremented to “9” our “while” loop will simply terminate without printing
anything on the terminal.
To verify this situation, we have to execute the Bash script that we have just
created using the command shown below. However, before executing this command,
you should ensure that you have saved your Bash script file.
$ bash BreakWhile.sh
The output of this script is shown in the following image. You can easily see
that the numbers printed on the terminal are from 1 to 8 and the number “9” is
not printed which means that our “while” loop has terminated successfully by
using the “break” command.

Conclusion

This article demonstrated a quite simple example of breaking from a “while”
loop in Bash in Linux Mint 20. The very same Bash script can be executed in any
other Linux distribution of your choice, and it will render the very same
results. Also, you can even use this “break” statement with the “for” loop or
any other loop in Bash to break its normal flow. This statement is extremely
useful especially if you have a certain special case within your program for
which you do not want your program to continue its normal execution or you may
even want the control of your program to take an altogether different path of
execution.
However, an important thing to consider over here is that we only intended to
give you a head start with using the “break” statement with the “while” loop in
Bash in Linux Mint 20. That is why we have just created a simple Bash script
for printing some sample numbers on the terminal, which are less than 10 except
for the number “9”. But it does not mean that the break statement is only used
with such simple scenarios. You can create even more complex programs to test
the effectiveness of the “break” statement with the “while” loop in Bash in
Linux Mint 20. Hopefully by going through this tutorial, you can easily create
any bash script of your choice using the break statement.


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
