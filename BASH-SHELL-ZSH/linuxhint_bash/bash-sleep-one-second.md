





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Sleep 1 Second

8 months ago
by Omar_Farooq
Whenever we have been working on something, we tend to feel hectic after some
time. Therefore, we need rest to recover ourselves or refresh the whole work
mode. Just like that, sometimes our Linux system also requires sleep for a few
seconds. It came up with the “sleep” function to make the processing of
anything pause for a specified period. This sleep function can be utilized
within the bash script and within the terminal shell to perform the same goal.
Therefore, we have decided to discuss the sleep function in Ubuntu 20.04 Linux
system. Let’s just get started with the login from an Ubuntu 20.04 system.After
the login, you need to open Ubuntu’s terminal application as we have to perform
the sleep command in it. To open it, try the “Ctrl+Alt+T” shortcut. If for some
reason the shortcut doesn’t work for you, click on the “Activity” menu from the
taskbar of Ubuntu’s desktop. The search bar will be opened. Click on the search
area, write “terminal” and press the key “Enter”. The application will be shown
on your screen. Click on the “terminal” application and it will be launched
within no more than 5 seconds according to your system speed.

Example 01: Sleep for 1 Second

Let’s get started with a simple example of the sleep function in bash. Let’s
say, you want to simply display a message “Testing…” on your terminal screen.
You have to use the “echo” statement for this along with this message as per
the below illustration in the image. After that, we tried the sleep function
with the value “1” to make our system sleep or pause for 1 second. As 1 second
is not a very long time, it will be quickly ended and the system will be
restored. The output of the below-mentioned command is attached here.
$ echo “Testing. . .”

$ sleep 1
The use of sleep can also be illustrated with the “read” statement of our
Ubuntu 20.04 system without using the sleep function. Let’s say, we want a user
to press Enter when it has been asked. Therefore, we have been using the “read”
statement with the “-p” flag along with the message stating that the user must
press Enter to proceed. After this command execution, the next line is showing
the message “Press Enter to proceed” and makes this system still without doing
anything. This looks like sleep and if the user doesn’t press Enter, it will
continue to look like this. The output of the below-mentioned command is
attached here.
$ read –p “Press Enter to proceed”

Example 02: Sleep for More Than 1 Second

Let’s make our system sleep for more than 1 second to see the sleep process.
Therefore, we have been trying the “sleep” command in the bash terminal with
the value 10. It will make our system sleep for a total of 10 standard seconds.
After the execution of this command by pressing the Enter key, our system went
to sleep as per the below demonstration.
$ sleep 10
After a total of 10 seconds has been passed, the system came back to its
original state and the control has been given to the next instruction as below.
$ sleep 10
The same thing can be achieved using the “read” command in the terminal. But,
we have to make use of the “-t” flag with the specified number value to make
our system pause for some time. Therefore, we have added the read statement
with the “-p” flag taking the message “Sleep for 10 seconds” followed by the “-
t” flag along with its value “10”. This “Read” statement will display the
message mentioned in the command and make our system pause for 10 seconds.
After running this execution, the message is now displayed and the system is
paused as below.
$ read –p “Sleep for 10 seconds” –t 10
After a total of 10 seconds have passed, our system returns to its processing
state. Therefore, no more pause has been encountered after this and a new query
area is generated. The output of the below-mentioned command is attached here.
$ read –p “Sleep for 10 seconds” –t 10

Example 03:

Let’s take a new example to look at the bigger picture of sleep function in
Linux. Thus, we have been creating a new bash file with the “.sh” extension
named “sleep.sh” with the “touch” query. After its creation in the home folder,
we need to open it in a “GNU Nano” editor to make code. Both the commands have
been shown below.
$ touch sleep.sh

$ nano sleep.sh
We have started our bash script with an echo statement telling us that the
system will sleep for the next 10 seconds. The sleep function is used in the
next line to pause the execution of this program for 10 seconds. After the 10
second sleep, the next echo statement will be executed showing that our system
will sleep for 15 seconds. The sleep function will be executed once again. The
system will be paused for 15 seconds and the last echo statement gets executed.
We have executed our bash file and the first echo statement has been executed.
After that, the system is sleeping for 10 seconds. The output of the below-
mentioned command is attached here.
$ bash sleep.sh
After the passage of 10 seconds, the next echo statement got executed. And for
another 15 seconds, the system goes to sleep. The output of the below-mentioned
command is attached here.
$ bash sleep.sh
After 15 seconds of sleep, the system came back to its processing state,
executed the last echo statement from the bash file and the code ended. The
output of the below-mentioned command is attached here.
$ bash sleep.sh

Conclusion

This article has been written for the help of Linux users to make the system
sleep for at least 1 second while working. We have used the “-t” flag, “read”
statement, and “sleep” function to achieve our goal. We have taken a look at
different bash commands and the bash script to perform them well.


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
