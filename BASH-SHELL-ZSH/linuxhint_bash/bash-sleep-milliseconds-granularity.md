





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Sleep Milliseconds Granularity

11 months ago
by Omar_Farooq
We used to think the sleep instruction only took whole numbers as an input. It
is not correct, as we discovered when attempting to find a technique to have a
program halt for very little than one second. This is a terrible mistake on our
part. But we are sure others think the same way we do. So, here’s a quick
tutorial about how to put bash to sleep in less than a half-second. So, we will
start it from the terminal shell. You need to open the shell terminal with the
help of a “Ctrl+Alt+T” command of Ubuntu 20.04 at its desktop environment.
Let’s have a look.

Example 01: Sleep in Seconds

Within the terminal application, we will see some simple sleep instructions
working by executing them with a one Enter key. We will take a look at the
sleep command for seconds first then for milliseconds. So, we have used the
keyword “sleep” with an integer or number on the shell followed by the key
“Enter”. In our very first command, we have used “0” as a value for the sleep
command. This means the system has to sleep for 0 seconds as shown below i.e.
no sleep.
When we changed the value of the sleep command to 10, for making our bash
system sleep for 10 seconds, it will sleep for 10 seconds, and then the next
instruction line will be generated.
If you want your system to sleep for 100 seconds, you have to write 100 after
the keyword sleep. This means your system has to sleep for a total of 1 minute
and 40 seconds as below.
There is another method to illustrate which time term you are using within your
sleep command. You need to know that the word “s” can be used for seconds, “m”
can be used for minutes and “h” can be used for hours in the sleep command as
shown below i.e. 10 seconds.

Example 02: Sleep in Milliseconds

Let’s take a look at the simple sleep command to sleep for milliseconds in
bash. So, you need to know that 1000 milliseconds are equal to 1 second. Now,
we will be using milliseconds in our bash code. So, when we write 0.1 seconds,
it shows the 100 milliseconds which is 1/10 part of a second i.e. 10th part of
a second. The system will sleep 100 milliseconds.
Then, we used the “0.9” second in the command i.e. 900 milliseconds i.e. 100
milliseconds less from 1 second. The sleep for milliseconds cannot be
noticeable as it is quite a short interval.
When you want to make your system sleep for only 1 millisecond, then you have
to divide 1 second to 1000 i.e. results 0.001. 1 millisecond is the 1000th part
of a second.
If you want your system to sleep for only 5 milliseconds, you have to use 0.005
instead of 0.001 as shown below. Your system will sleep for such a short time
that is not even noticeable.
We can also utilize the scientific notation technique to show milliseconds in
the sleep command. So, we have used “e” as an exponent in the value. It will be
pronounced as 1 raised to the power 3 i.e., 0.001 seconds.
Arithmetic operations can also be applied to seconds to divide into
milliseconds. We have divided 1 with 5 and it will convert it to 20
milliseconds. The system sleeps for 20 milliseconds.

Example 03: Sleep in Milliseconds

Let’s take a look at the bash script to sleep the system and execute its
statement after sleep. So, we have created a new bash file named “sleep.sh”
with the touch instruction. We have used the GNU Nano editor in the shell to
open this file i.e. using the “nano” command. You can either utilize nano or
any other editor i.e. text editor, vim editor of Ubuntu 20.04.
So, the empty bash file is launched in the editor. We have started the code
with the bash path. The first echo statement is used to tell the user that the
system will sleep for 5 seconds. The sleep command is using 5 as the value to
seconds for sleep.
Another echo statement is telling the user that the system will sleep for 0.8
seconds i.e., 800 milliseconds of time interval which is also quite
unnoticeable. The sleep statement is used for this purpose and the last echo
statement is showing that the program is completed.
Upon the execution, the bash script shows the message and sleeps for 5 seconds
as shown.
After 5 seconds it displayed the other message and slept for 800 milliseconds
of a time interval. After that sleep, the program ended.

Example 04: Sleep in Milliseconds

Let’s take a look at the last illustration of bash script. We have updated the
above example and added three sleep statements in the code after the bash path.
The first echo statement shows that the system will sleep for 1 minute i.e. 60
seconds. The sleep statement is used to mention 1-minute sleep. The next echo
statement is used to tell that the system will sleep for 15 seconds. The sleep
statement is used for that purpose i.e. 15s. The last statement shows that the
system will sleep for 0.1 seconds i.e. 100 milliseconds of a time interval.
After the execution, the system sleeps for 1 minute as shown.
After 1 minute of sleep, the system displayed the display message and slept for
15 seconds.
At last, the system slept for 100 milliseconds, and the program closed here.

Conclusion

This article is giving us the whole description of using sleep command or
built-in utility of bash to make our system sleep in milliseconds. We have
utilized the simple sleep statement in the terminal as well as in the bash
script. All the illustrations are implemented as per the ease of our user to
understand easily. Hence, we are hoping for the best feedback.


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
