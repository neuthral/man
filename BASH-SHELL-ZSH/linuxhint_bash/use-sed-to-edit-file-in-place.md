





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Sed to Edit File in Place

1 year ago
by Adnan_Shabbir
Linux supports various types of command line utilities to automate the tasks
which makes Linux in the leading line of OS; because of its importance and
usage, it has hundreds of distributions that are based on Linux and they do
support numerous commands to perform actions automatically.
There is a huge pool of commands available for Ubuntu and sed command utility
is one of them; the sed command can be used to perform fundamental operations
on text files like editing, deleting text inside a file.
Alongside these primary actions, sed provides long list of supported options
that can be used to manipulate the output according to user requirements,
inspired by this; we have compiled a guide that will demonstrate to keep the
changes in the original file using sed command:

How to edit file in place using sed command

This option of sed command is used to edit file and save the changes to the
original one and can be used with all operations of sed command:
The syntax for this option is described below:

Syntax

sed -i command [file name]
or
sed --in-place command [file name]
In the syntax given above, the “-i” option is constant (when you are making in
file changes) and the “command” keyword contains the operations (substitution,
deletion, appending) being performed using the sed command; and lastly, the
“file name” directs to the name of file where all the actions are taken that
are associated with sed command.
We have taken a text file that contains few text lines in it:
Let’s extract the content of “examp.txt” file using the command mentioned
below:
$ cat examp.txt
Let’s start with the basic usage that if we use sed without “-i” option then it
would print the result on the terminal and the original file will be unchanged
(as checked using “cat” command) as shown below:

Difference between edit file in place and file edit of sed command

In the below-mentioned command; “s” is used for substitution and it will
replace the word “Debian” with “Ubuntu”. Moreover, the letter “g” at the end of
this command is for global action, means the replacement would be performed in
the whole file:
$ sed ‘s/Debian/Ubuntu/g’ examp.txt
And now use the same command with “-i” option as given below; it is noticed
that with the help of “-i” the content inside the original file (“examp.txt”)
is also changed now, as displayed below:
Note: You can use “–in-place” instead of “-i”; both the options have the same
functionality:
$ sed -i ‘s/Debian/Ubuntu/g’ examp.txt

How to edit a specific line of file in place using sed command

And if you want to change the content of any specific line number, then you can
add numeric value with “s” letter; for instance, the command given below will
replace “Ubuntu” with “Debian” only on line number “2” and once you have
specified the line number the purpose of “g” letter is nullified so you can
also remove it:
$ sed -i ‘2s/Ubuntu/Debian/’ examp.txt
Moreover, you can place “$” sign with “s” keyword to only perform the changes
on the last line of the file; like the command written below will put the word
“Ubuntu” in place of “Linux-Mint” on last line of “examp.txt”:
$ sed -i ‘$s/Ubuntu/Linux-Mint/’ examp.txt

How to delete a line in a file using in-place of sed command

The in-place option has an extensive use in sed command as discussed above;
apart from replacing words in a line, one can delete the whole line and save
the output in the parent file using “-i” option: the command mentioned below
will delete line number “2” of the file “examp.txt”:
$ sed -i ‘2d’ examp.txt
And if you want to delete the lines except line number “2” then you have to
write the command like mentioned below:
$ sed -i ‘2!d’ examp.txt

Conclusion

Ubuntu supports a variety of commands that can be used to perform the primary
operations on text files like head, or tail commands can be used to print the
lines available at the start or end of a text file. However, there are some
limitations, let’s say you cannot print only line number 2 of a text file using
head command (although line number 2 comes in the head section of file). The
sed command leads other commands in this regard; this command in Ubuntu helps
to perform basic operations on text files, like substitution, addition,
deletion etc. It is observed that if the sed command is used except the option
“-i” then the result would be printed on terminal only. In this article, the
in-place option of sed command is described in detail and can be adopted with
all the sed operations. To get a deep insight of this option, we have tried to
use it with as many commands to build up basics for novice users.


About the author


Adnan Shabbir

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
