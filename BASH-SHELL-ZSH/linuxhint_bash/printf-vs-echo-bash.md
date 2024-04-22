





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


What is the Difference Between Printf and Echo in Bash?

1 year ago
by Omar_Farooq
We may want to organize the result of an Ubuntu operation in a specific way.
Perhaps we should avoid bloated results and present information in a concise
style. The commands echo and printf are also constructed. Printf provides for
the creation of a formatting string and offers a non-zero quit status when it
fails. Whereas echo normally leaves with a 0 status and typically outputs
inputs headed by the end of line character upon this standard result. The
“printf” gives you more options for the output format than the “echo”.
Throughout this brief lesson, we will look at how to style the results of the
terminal using the echo and printf instructions on Ubuntu 20.04 Linux system.

Example 01:

To emphasize and see the working of printf and echo statements, let’s have our
first simple and easy to do an example. You have to open the console shell
application to do so. For that, use the “Ctrl+Alt+T” on the desktop screen of
your Ubuntu 20.04 Linux operating system. The console application will be
opened in a few moments, and for that, you don’t have to wait much. After the
terminal is opened, we will perform both “printf” and “echo” statements
separately to see how they work properly. So, we have tried “printf” on the
shell first to print out the number of characters in a string “Linux” on our
shell.
The command has been used with the “-m” flag along with the “wc” keyword. The
command has been listed in the image below. After executing this command by
pressing the “Enter” key, we got 5 as a result. This means the “printf”
contains only 5 letters in it. As the printf is a standard statement, that is
why it would display the arguments in a standard formatted form while in
control.
$ printf ‘linux’ | wc -m
Let’s have a glance at the “echo” statement now. So, the overall syntax for the
command will be the same, but the “echo” statement will be used instead of
“printf” here. The string provided in the command is also the same. When we run
the command on the console, it displays the 6 number as a result. Why does that
happen when a string contains only 5 characters? This is because the “echo”
statement also counts the “newline” as its character according to the bash
“echo” standard manpage manual. If we add some space before or after the
string, it will also take it as a character.
$ echo ‘linux’ | wc -m

Example 02: Using Printf

Let’s see the working of the “printf” statement first in our new example.
Create a new bash file “test.sh” with the utilization of a nano touch command
followed by the “nano” command in the shell. The nano command will be used to
open the file within a “Nano” editor. After the file has been opened, we have
added the bash extension first at the first line of a file. The variable “str”
has been initialized with a long string value in it. We have declared a built-
in variable “IFS” to use space as its delimiter value.
Then we have used the “read” command in the next line to read the values of a
string variable as an array and save it to the variable “Arr”. The “-ra” flag
has been used here for this purpose specially. After this, the echo statement
is utilized here to let us know about the size of an array variable “Arr”. The
“for” loop has been initialized to iterate each word from a string variable and
display it on the shell using the “printf” statement. As we know that the
printf doesn’t take the next line as its next character automatically, so we
have used the “\n” character within the printf statement to do so. The loop
ends here, and the code will be saved with the help of a “Ctrl+S” shortcut key.
To see the results of the printf statement, execute the file with the “bash”
command to make it work. The output displays the size of an array, i.e., 9.
After that, each word of a string has been iterated using the “for” loop and
displayed on the terminal separately at each next line. This has been done
using the “\n” within the “printf” clause. Otherwise, it may not have happened.
$ bash test.sh

Example 03: Using Echo

Within this new example, we will be illustrating the working of the “echo”
statement in the bash script. So, we have opened the same “test.sh” find with
the help of a “nano” command in the shell console. The file is opened in the
nano editor. All the code remained unchanged, i.e., bash support, “str” string,
IFS variable, read statements, and “for” loops. The only change you have to do
is: replace the “printf” word with the “echo” keyword in the bash script.
You can see we have also added “\n” within the “echo” statement to get on the
new line. As we all know that the “echo” statement always considers the newline
as an additional character; therefore, it will not format the output as such.
Let’s run the code to see the results. Instead of creating a gap of 1 new line,
the echo statement considers the “\n” as an additional character. Therefore,
the output looks like something below.
$ bash test.sh
Let’s update the code to get the required results. So, after opening the file,
we have removed the “\n” character from the echo statement string. Saved the
code and quitted the file.
After running the updated code this time, we have again got the size of a
string array as “9”. After that, all the words of an array have been displayed
separately, each on the next line.
$ bash test.sh

Conclusion:

This guide contains more than one example to illustrate the functionality and
difference of the “printf” and “echo” statements. Prefer using the “printf”
statement within bash because it is more standardized as “echo” behaves poles
apart on other platforms.


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
