





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Check If Directory Exists

8 months ago
by Omar_Farooq
Directories and folders are the main and quite important parts of any operating
system. Without the directories and files, our system doesn’t get completed.
The directories are used to store the sub-folders and files that hold data in
them for security and personal work. Within the Linux operating system, we have
also got the same file system i.e., directories and sub-folders. Bash
programming came up with some of the very simple commands and statements to
check if the specific directory of a file exists in our system or not.
Therefore, we have decided to write this article to check if the directory
exists in our Linux system or not.

Example 01: Check If File Exists

Let’s get started with the basic example. We will be having a look at checking
a simple file in our Linux system first i.e., if exists or not. Therefore, we
have been creating a new text type file named “new.txt” within Ubuntu’s home
folder with the “touch” instruction. We have added a one-line text in the file
and displayed it on the shell using the “cat” instruction shown below. The
output of the below-stated command is attached in the image.
$ touch new.txt
$ cat new.txt
Now, it’s time to create a new bash file with the “touch” instruction named
“direc.sh” as below. We need to open this empty file to start coding in it. For
this, we have been using the “nano” instruction to launch it within the GNU
Nano editor. The output of the below-stated command is attached in the image.
$ touch direc.sh
$ nano direc.sh
Now, the empty file has been opened in the nano editor. Within the first line
of code, we have initialized a file variable “F” holding a path to a file
“new.txt” as “/home/linux/new.txt”. The “if-then” statement of bash has been
utilized here to check if the file “new.txt” exists or not. The “if” clause is
started with the keyword “test” followed by the flag “-f” for files. Within
inverted commas, we have added the variable “$F”. After this, the “then” clause
started with the “echo” statement using the variable name to show if it exists
or not. The “then” part of the “if-then” statement will only be executed when
the condition “if” will be true.
Let’s run the bash file using the “bash” keyword followed by the name of a file
“direc.sh”. As the file exists in the home directory of our system, thus it
executed the echo statement and is showing that the file exists. The output of
the below-stated command is attached in the image.
$ bash direc.sh
The same thing can be achieved with the use of square brackets around the
condition of the “if” clause without using the keyword “test” as shown below.
Let’s execute it to see its result in the bash output screen within the shell.
After running this updated code, we have got the very same result i.e. file
exists. The output of the below-stated command is attached in the image.
$ bash direc.sh

Example 02: Check If Directory Exists

Let’s take a look at the code that is used to check if the directory of the
folder exists in our system or not. For that, we will be using a purely new
folder. Therefore, within the terminal shell query area, we have tried the
“mkdir” command to create a new directory named “new”. This newly created
directory will be used within our code to check if it exists or not. The list
command is executed to see all the existing directories and files in the home
folder. We can see the “new” directory listed in the shown output beneath the
“Music” folder and after the “Downloads”. The output of the below-stated
command is attached in the image.
$ mkdrir new
$ ls
Let’s open up the same “direc.sh” file in Ubuntu’s nano editor to create a new
code. After the file is launched, we need to create a new directory variable
“D” holding a path to a newly created directory named “new” as “/home/Linux/
new”. The overall work to check the directory existence has been done within
the “if-then-else” statement of bash. So, the “if” statement has been started
with the condition to check the directory in a system using the “-d” flag for
“directory” along with the directory variable in inverted commas. This
condition has been utilized within the square brackets. If the condition got
satisfied and the directory exists, the “then” statement will be executed along
with its “echo” statement. Otherwise, the “else” part of the statement will be
utilized along with its “echo” statement showing that the file doesn’t exist.
The overall statement will be closed by the “fi” keyword as shown below.
Now, it’s time to run our bash code in the terminal shell using the “bash”
query shown in the image. After running it, we have got the success message
showing that the directory exists. The output of the below-stated command is
attached in the image.
$ bash direc.sh
If you want to achieve the else part execution in the shell terminal, you must
have to delete the directory so that the condition doesn’t get satisfied.
Therefore, we have deleted the newly made empty directory “new” from the home
folder of our Ubuntu 20.04 system. After this, we have listed the contents of
the home folder using the list command and found that there is no directory of
the name “new” as below. After running the same “direc.sh” bash file with the
“bash” instruction, we have got the output showing that the else part of the
code has been executed i.e., directory doesn’t exist.
$ ls
$ bash direc.sh

Conclusion

Finally! We have done the explanation of checking out if the directory exists
in our Ubuntu 20.04 system or not. For this, we have tried the bash script to
achieve our goal. We have also discussed the use of “-f” for file checking and
“-d” for directory checking in the system. All the examples are simple and
according to our user choice.


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
