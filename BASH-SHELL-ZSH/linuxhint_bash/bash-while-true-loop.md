





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash While True Loop

8 months ago
by Omar_Farooq
Linux is quite a diverse operating system when it comes to programming. It’s
because it came up with its own “Bash” programming that many of the other
operating systems do not support. Its Bash programming supports almost all the
features another standard programming provides. The use of “loops,” i.e., while
and for, is one of these aspects. We can continue executing these loops without
stopping them. Therefore, we have decided to demonstrate the concept of the
“while true” loop for our Bash users who are unfamiliar with this concept.
So, let’s start by logging in from the Ubuntu 20.04 system. To start
implementing the examples, we must ensure that the terminal shell has been
opened using the “Ctrl+Alt+T”.

Example 01:

Let’s start this article with our first example of utilizing the while loop
with the “True” condition. But before that, we need to create a Bash file with
the “touch” instruction of the Ubuntu 20.04 terminal shell. Name the Bash file
as “bash.sh”. This file will be created within the Linux home folder. You can
use any built-in editor of the Ubuntu 20.04 system to open and create the code
within the Bash file. Rather than using the “nano” instruction with the file
title, just use GNU Nano editor within the terminal shell. It will open your
empty file within a terminal like a screen of GNU Nano editor.
As we have to use the “while true” loop in our code, we will have to add the
Bash support at the first line of code. After this, we have started our one-
line while loop with the true condition. This true condition implies that the
loop will continue to execute until some external activity forcefully stops it.
Within its do clause, we have been utilizing the “echo” statement to display a
string of characters “Continue…” until the loop has been executed on the shell.
The done clause implies that the while loop is complete here.
Let’s check how this one-line while “true” loop outputs in the terminal shell
after saving this code with the Ctrl+S shortcut. Press Ctrl+X to exit the file.
In the attached screenshot, you can view the code file:
It’s time to execute our Bash code with the “Bash” instruction on the shell, as
displayed in the image below. The output is displayed in the following
screenshot for the previous code:
$ bash bash.sh
This loop will continue to execute and display the string value “Continue…”
through its echo statement until we stop its execution forcefully. To do that,
we have to press the “Ctrl+Z” shortcut so that the loop and program can be
stopped. Otherwise, it will continue to execute, as shown below:

Example 02:

Within the first example, we have seen how to use a while true loop to
continuously display the string value on the shell without stopping. Within
this example, we will perform a pretty similar activity with a little different
functionality. So, you need to open the same Bash file and add the Bash support
via its /bin/bash path. Initialize a variable “X” with the value 1, as shown
below. The while loop has been started with the condition “true”. In its “do”
part, we have encountered the “echo” statement to display the current value of
x. Also, we have been utilizing the built-in “let” clause in the “do” part to
increment the value of variable “x” by 1 at each time.
After the increment, the sleep function has been used to take a 3-second sleep
during execution. After all these 3 steps in the “do” part, our while loop will
continue to repeat this process until the program was terminated due to some
external activity. The “done” part shows that the loop is complete now. Let’s
save this code and run it on the shell. In the attached screenshot, you can
view the code file:
After running this Bash code with the “Bash” instruction, the while loop
started to execute. It displays each value of “x” from the start and takes a 3-
second sleep on each iteration after the increment. Then, the next incremented
value will be printed out, and the process continues. The output is displayed
in the following screenshot for the previous code:
$ bash bash.sh
To stop this non-stopping loop, we have pressed the Ctrl+Z, as shown below. The
output is displayed in the following screenshot for the previously stated code:

Example 03:

Let’s take our last example to use the condition other than true in the while
loop. So, we have started the Bash code with the initialization of variable “x”
with 2. The while loop is taking a condition in its square brackets. It uses
the “-lt” operator to check if the value of “x” is less than 7 or not. If a
condition is satisfied, the “do” part will be executed. Hence, the echo
statement will display the value of “x” and increment it by 1 using the “x=&(
($x+1))” as shown. After reaching 7, the loop automatically stopped as per the
“done” clause. Let’s save our code by Ctrl+S and exit it with Ctrl+X. In the
attached screenshot, you can view the code file:
Now, run the Bash file with the “Bash” query shown in the image below. The loop
gets executed and continues to display the value of “x” until it reaches 7 upon
increment. The output is displayed in the following screenshot for the previous
code:
$ bash bash.sh

Conclusion:

This tutorial guide was about using the “while true” loop in the Bash script.
We have discussed using a while true loop with very simple Bash codes and
addressed the while loop with no “true” condition. This has been done to
clearly compare both circumstances and how to handle them separately. We hope
you found this article helpful. Check the other Linux Hint articles for more
tips and information.


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
