





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Resolve Issue: Bash Bad Substitution

6 months ago
by Omar_Farooq
You may have received the Bad substitution syntax problem while developing Bash
scripts. After browsing through forums, you may discover that you are not
alone; other individuals are encountering the same mistake. It’s a
typographical fault that happens when you run your Shell script, and it can
happen for a variety of reasons. The wrong use of instruction substitution and
erroneous characters appended to the program are two major reasons for this.
Let’s see how we can make our shell script cause this error and how to resolve
it. Get started with the new bash file created with Ubuntu’s “touch” query and
open it within the “GNU Nano” editor.
$ touch sub.sh
$ nano sub.sh

Example 01

The first reason for the bad substitution error is the use of the wrong code
syntax. Let’s take a look at this. Starting from the first bash code, we have
added bash support in the first line of the bash script, i.e., “#!/bin/bash”.
After this, we have initialized a simple variable “V” with the list command of
Ubuntu as its value. This value has been inserted within the curly brackets and
with the “$” sign to consider it as a shell command. After this, the echo
statement is here to simply display the value of the “v” variable on the shell.
Our code is complete and ready to use.
We saved the bash code and came back to the terminal after using Ctrl+S and
Ctrl+X, respectively. We have executed this newly created bash script file with
the “bash” instruction and got the “bad substitution” here on our screen. This
error has occurred due to the use of curly brackets “{}” around the list
instruction in the code.
$ bash sub.sh
Let’s try updating our code to resolve this error now. So, we have removed the
curly brackets from the second line of code and replaced it with the simple
brackets “()” as presented below. Overall, the code will remain the same as
there is no issue with the code. Save this code now.
After exiting the GNU nano editor, we will execute the bash file “sub.sh”
updated code with the use of the “bash” instruction as presented below. It
turns out that the bad substitution error has been removed after the code
update, and the list instruction inserted within the variable “v” has been
executed successfully. The list command displayed all the current home
directory contents, i.e., files and folders, on our shell screen.
$ bash sub.sh

Example 02

Another reason for the occurrence of bad substitution errors in bash is the use
of unnecessary spaces while executing some variables. So, we have added bash
support and initialized a variable “V” with the list instruction in it as a
value held by simple brackets and a dollar sign “$.” After this, we have been
using the “echo” statement to display the variable “v” value. But we have added
the variable “V” in the “echo” statement along with the “space” in the
brackets.
After saving this code, we have executed this bash file with the “bash” query
in our terminal, as presented below. It returns the bash substitution at the
3rd line of the script.
$ bash sub.sh
To remove the error from our code, we have to update our code. So, we have
opened the file again and removed the extra space within the curly brackets of
the “echo” statement as below.
Now that the code has been updated and white space is removed, we have to
execute this file with the bash instruction presented below. After running the
file, the bad substitution error has been removed, and the list instruction
specified in the variable “V” has been executed successfully on the terminal
after the “echo” statement got executed in the bash script. The list of current
home directory files and folders is displayed on our shell screen below.
$ bash sub.sh

Example 03

This error may also occur due to the usage of repeated unwanted characters in
the code. So, we have tried an updated code to get this error on the shell. For
this, we have to use the “$” character twice in the “echo” statement to specify
the variable “V” for execution which is the wrong syntax to do so. This
variable “v” contains the simple list instruction as its value. As we have used
the double “$” sign in and out of the curly brackets in the “echo” statement,
it will lead us to a bad substitution error on execution.
After running the code with bash instruction, we encountered a bad substitution
error at line 3 of the bash script on our shell screen.
$ bash sub.sh
Let’s remove the bad substitution error from the execution by updating line 3
of a code. We have removed the inner “$” sign within the curly brackets from
the “echo” statement.
After removing the “$” sign, we have executed the code again on the shell with
the “bash” command. The error has been removed, and the list of files and
folders has been displayed.
$ bash sub.sh

Example 04

Let’s have our last but not the least example of this article. We have been
using two variables, x, and y, containing the directory location as their
value. In the “echo” statement of this code, we have been using both the
variables to be printed and separated by the “/” sign. Each variable contains a
dollar sign with it, while a single dollar sign is also used outside the curly
brackets.
The use of curly brackets and dollar signs caused a bad substitution error.
$ bash sub.sh
So, we have removed the curly brackets and the outer dollar sign, as shown
below.
This time value of both variables has been displayed.
$ bash sub.sh

Conclusion

This is all about the illustration of creating a bash code to the mistakes
causing the bad substitution error to occur during execution. We have discussed
the do’s and don’t to avoid the error via performing different bash examples.


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
