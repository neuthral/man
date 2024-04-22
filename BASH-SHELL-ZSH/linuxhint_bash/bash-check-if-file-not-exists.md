





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Check If File Not Exists

7 months ago
by Omar_Farooq
Regardless of any operating system you have been using, you must have used its
file system at some point. These file systems are the main core of any system
and let you save your data in it. There might be situations when you have to
search for some particular file or directory from this file system using
different search options.
Just like that, Linux came up with the Bash programming to search for a
particular file using the Bash script in the terminal. We will be using the
Bash shell scripts to look for the files in Ubuntu 20.04. Let’s get started. We
have created a new Bash file with the name “file.sh” using the system’s “touch”
query. To create a Bash script, we need to open this newly made file in the
Linux “GNU Nano” editor.
$ touch file.sh
$ nano file.sh

Example 01

The empty file has been opened on your shell screen within the nano editor. We
have to add the Bash support in it as “#!/bin/bash”. After this, we have
initialized a “FILE” variable with the path to the file itself “file.sh” i.e.,
“/home/linux/file.sh”.  To check for the file exists or not, we will be using
the “If-then” statement taking its conditions in the single square brackets in
this Bash code. To check whether the file format, we need to use the “-f”
option followed by the double-quoted variable “FILE” with the dollar character
“$”. This is to check whether the given path to the file contains a file with
the name “file.sh” or not.
The condition ends here and the “then” part of the statement starts. If the
file exists, it will display the message that the file “file.sh” exists in the
given path using the “echo” statement. The “if” statement ends here on “fi”.
Now, save your Bash code file with the Ctrl+S shortcut and exit your nano
editor with Ctrl+X. We are back in the terminal. Now, we need to utilize the
bash instruction to run the “file.sh” file. On executing, it shows that the
file exists in the current directory specified in the code.
$ bash file.sh

Example 02

Let’s take a look at another example of checking for the Bash file existence.
So, we have been utilizing the “if-else” statement here. Starting from adding
the Bash support and initializing a variable “FILE” with the file name “new.sh”
to search for this Bash file in the current directory. We have been using the
double square brackets to specify the condition with the “-f” option for file
search via the variable “$FILE”. Then, part will specify what needs to be
implemented.
If the condition is true and the file exists, “then” part of the statement will
get executed. The echo statement will display that the file exists. Otherwise,
the else part of the “if-else” statement will get executed and the echo
statement will display that the file does not exist.
We have saved this file and exited it with Ctrl+S and Ctrl+X respectively. On
running this code file, we have got to know that this bash file “new.sh”
doesn’t exist in our current directory.\
$ bash file.sh

Example 03

Let’s say, you want to use the “not” character in the “if-else” statement. You
can do that by using the “!” exclamation mark before the option “-f” in the
condition of an “if-else” statement. Add the variable “FILE” and initialize it
with the relevant file path. Use “!” before “-f” in the condition as shown
underneath.
Now, you need to update the “then” and “else” part of the statement according
to the “!” condition. If the condition is satisfied and our file is not in our
home folder, the “then” part will execute that “file doesn’t exist” using the
“echo” statement. Or else, if the file exists, the else part will be executed
and the echo statement will display that the file exists.
On running this code, the else part got executed and we saw the message “file
does exist!” displayed on the shell.
$ bash file.sh

Example 04

The same thing can be achieved by using the same syntax of code in the Bash
console without creating any Bash file. For this, you only have to utilize the
“sh” command to open the Bash console. Now, we have been using the condition
for checking if the file “new.sh” exists or not using the “-f” option within
the square brackets/ The && option will specify the “then” clause here. The
echo statement is used to print the message conferring the condition.
The “||” characters show the “else” part of the statement and the echo
statement will display according to the situation. On running this single line
code on the Bash console, we have found that the file “new.sh” does not exist
in the home.
$ sh

Example 05

You can also utilize the same “-if-else” statement to check for the existence
of a directory using the “-d” option in its condition instead of “-f”. Let’s
say, we have a directory “test” in our home folder and we have been using the
same script with the “-d” option to search for it and display the string
message according to the condition output. Replace the file path with the
directory path as demonstrated in the image below. Save your code and exit the
editor.
After running this code, we have found that the directory “test” exists in the
home folder.
$ bash file.sh

Conclusion

This is all about the use of some Bash script to find out whether the
particular file doesn’t exist in the current directory or exists. We have used
the “if-else” statement at our end to do so. Also, we have used the direct code
in the Bash console utilizing the “!”, “-f”, and “-d” options.


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
