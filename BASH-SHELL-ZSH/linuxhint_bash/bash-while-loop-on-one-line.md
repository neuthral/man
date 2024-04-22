





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash While Loop on One Line

8 months ago
by Omar_Farooq
Like many other programming languages, Bash programming also supports the use
of “loops” in its code. There are a lot of loops supported by Bash coding,
i.e., for loop and while loop. You may have used both the “for” and “while”
loop in your programs while coding. But have you ever tried to use the loop on
a single line with all its working? If not! Then, this article is meant for you
and all the Linux users who want to try the “while” loop in a single line of
Bash code.
Today, we will be discussing some of the simple and easy-to-understand examples
in our article. Let’s start with the Ubuntu 20.04 Linux terminal shell
application launch using the “Ctrl+Alt+T” shortcut.

Example 01:

Now, the terminal application has been launched. It’s time to create a new Bash
file. For this, you need to utilize the simple “touch” query of Bash
programming to create a new Bash file containing the Bash extension, i.e.,
“bash.sh”. The file has been generated within Ubuntu’s home folder. You have to
open it within some editor to start adding Bash script. To open a file and add
code, we have been utilizing the GNU Nano editor. For that, try using the
keyword “nano” with the file name on the instruction area of the terminal and
execute it. The file will open as an empty screen.
Let’s start with the first example of using the “while” loop on one line of the
Bash code. As the file is empty, we need to add the Bash extension in our Bash
file to make it execute as a “Bash” script. It is not essential to add the
extension. Your code will execute perfectly fine without using the Bash support
in the file if you have named it with the “.sh” extension or run it with the
keyword “bash”. As we have to use the one-line “while” loop in the code, we are
fulfilling our promise here. The while loop started with the keyword “true”
states that the loop will continue to execute until “true”, i.e., it will not
stop its execution until the user ends the program itself.
Within its “do” part, we have added the “echo” statement to print the string
“hello” on the shell. The “while” loop on one-line ends at the “done” keyword.
Let’s save your code and exit to execute it now.

Let’s run our file with the Bash command, i.e., using the “bash” keyword as
shown below.
$ bash bash.sh

Upon execution, the program has started to output the string “hello” without
stopping as per the following output. If you want to exit this one-line loop,
press “Ctrl+X” on the shell. Now, check out the output in the following
screenshot:

Example 02:

Let’s look at another one-line “while” loop used in the Bash code. This code
will be similar to the previous example code but with a slight change. So, we
open the same Bash file and update the code. We have been using the same “while
true” statement to start the continuous loop without end. Within its “do” part,
we use the “echo” statement to display a message that our system will have a 3-
second sleep on every message display. The “sleep” function has been used
within the “do” part of the one-line while loop to take a 3-second sleep on
every display of string message by the “echo” clause. Thus, the loop will be
ended at the “done” part.
The program for the one-line while loop is complete and ready to get executed.
Save it with the “ctrl+S” and exit the file with the “Ctrl+X” shortcut.

After the file exit, we have executed it with the “Bash” instruction. The
program code started to display the string “Hello, sleeping for 3 seconds” with
the pause of 3 seconds after every message displayed on the shell as presented
below:
$ bash bash.sh

The one-line “while” loop will continue to execute this program until we quit
it forcefully. As a result, we need to use the “Ctrl+Z” shortcut to halt its
execution temporarily. Now, check out the output in the following screenshot:
$ bash bash.sh

Example 03:

If you don’t want your one-line loop to continue its execution without any
stop, you can do that. So, we have decided to create one example for such a
type of one-line while loop. Thus, I started the Bash file within the nano
editor and added the Bash support at the first line. After that, we have
initialized an integer value “i” with 2. At the following line, we use the
“while” loop to iterate itself until its specified condition is satisfied. The
condition says that the value of a variable “i” must be less than or equal to
“14” via the “-le” operator of Bash. If so, the loop will execute its “do”
part, and the “echo” statement will display the current iteration value. On
execution of the “do” part, the value of “I” will be incremented by 3. The loop
ends here, and we have to run the following Bash code now:

On every iteration, the system continues to display the iteration value and
increments it by 3 until it reaches the value “14”. Now, check out the output
in the following screenshot:
$ bash bash.sh

Conclusion:

This article has thoroughly explained all the Bash examples using the one-line
while loop with different conditions. We have discussed the non-ending one-line
loop and the conditional loop that can end on its own. Thus, we can say that
our article contains quite diverse examples for our Linux users. All of the
previous examples can be amended as per the needed work. We hope you found this
article helpful. Check the other Linux Hint articles for more tips and
tutorials.


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
