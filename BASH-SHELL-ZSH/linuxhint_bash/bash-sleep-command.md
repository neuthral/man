





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Sleep Command

4 months ago
by Saeed_Raza
Within the Bash script or console, the sleep command works the same way as we
take sleep in real life. Just like a real-life sleep can be taken to get free
from work and do nothing, the Bash sleep instruction can halt the execution of
any Bash script already running. The sleep instruction of Bash can be utilized
directly within the terminal application of Ubuntu 20.04. It can also can be
utilized within the separate Bash script before and after some code statements.
Within this article, we will discuss the utilization of this sleep instruction
in both ways.
Let’s get started with the simplest and easiest example of using the sleep
function in our Bash shell of the Ubuntu 20.04 Linux operating system. Now, we
utilize the sleep instruction in its query area to make our Ubuntu system sleep
for some time. Let’s say, you want to make your system to sleep for only 10
seconds. For this, you need to use the “sleep” keyword with the numerical value
10 in the query area, and execute it using the Enter button. The system waits
for 10 seconds to complete as shown in the following:

After 10 seconds, the execution of the sleep function stops and the system
continues to work normally as shown in the following:

The previous illustration is all about the use of the sleep function to make
our system sleep for hardly 20 seconds. Within this illustration, we make our
Bash console sleep for hardly 1 minute and 10 seconds. After 1 minute and 10
seconds of sleep taken by the console application using this instruction, the
console application reaches its normal state. For this, you need to specify the
number “1” for a minute and “10” for seconds, along with the character “s” at
its end. It is necessary to add the “s” at the end. After 1 minute and 10
seconds, the system console application reaches its normal state.

Just like that, if you want to make your Bash console to sleep for 1 hour or
more, you can do so by using the sleep instruction at the shell along with the
specification of hours, minutes, and seconds. We make our Bash console sleep
for 1 hour, 1 minute, and 10 seconds as displayed. After 1 hour, the Bash
console continues to work normally. You can also forcefully stop the sleep
process started by the sleep instruction on the shell by simply making using of
the “Ctrl+Z” shortcut.

Within the Bash terminal, you can make your Bash console application sleep for
several periods with the creation of some one line Bash script. This Bash
script can contain more than one Bash script statement separated from each
other by the “&&” operator within them. We start this simple Bash script with
the sleep statement that makes our console sleep for 20 seconds first.
After this, we use the “echo” statement that displays “20s” in the console
after the 20 seconds of sleep separated by &&. Another sleep statement is
utilized to make our Bash script sleep for 10 seconds separated by the &&
operator. At last, the echo statement is used once again to display “done” on
the console. After the execution of this one line Bash script on the shell, the
console doesn’t display anything as it sleeps for exactly 20 seconds.

After the 20 seconds sleep of this Bash script, the echo statement is executed
and displays “20s” on the console. After this, the console script gets halted
for another 10 seconds as per the sleep instruction used within this Bash
script.

After the last 10 seconds of sleep, the last echo statement is executed and
displays the “done” message at the console as per the “echo” statement.

The previous illustrations were all about the use of the simple sleep
instruction on the shell terminal to make our program and console execution
halt for a certain period. Now, we make use of the sleep instruction within the
Bash script file to do the same task differently. We generate a new Bash file
named “sleep.sh” in the shell with the utilization of a “touch” instruction. We
open the newly generated Bash script file in some editors like a text editor,
Vim editor, or GNU Nano editor. Prefer to use the Nano editor as it is quick to
open and modify as per the “nano” instruction displayed in the following
screenshot:

The file “sleep.sh” is opened within the Nano editor. Since it is empty right
now, we add some Bbash script to it. We start our Bash script with the simple
use of the Bash path as a comment, i.e. “#!/bin/bash”. A total of three echo
statements of Bash are utilized to display the specific messages on the console
according to the situation – i.e. sleep for 20 seconds, sleep again, and done
with enough sleep. Within these three statements, we utilize the two sleep
statements to force our script execution to halt or wait for 20 seconds and
continue the rest of the execution after the sleep.

After the execution of this Bash script, the script makes the console sleep for
20 seconds after the display of the first message.

After the sleep, the script executes its second message and sleep for the next
20 seconds.

After the sleep of 20 seconds, the script runs its last statement, and the
program is terminated.

Conclusion

This article’s introduction is all about how a sleep instruction of the Bash
script is related to real life. After this, we discussed some simplest
illustrations to make our Bash console sleep for a while – i.e. hours, minutes,
and seconds. Finally, we also used it within the separate Bash files to make
the execution of the Bash script halt for some time. Both methods contain the
use of the echo statements to separate one sleep round from another.


About the author


Saeed Raza

Hello geeks! I am here to guide you about your tech-related issues. My
expertise revolves around Linux, Databases & Programming. Additionally, I am
practicing law in Pakistan. Cheers to all of you.
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
