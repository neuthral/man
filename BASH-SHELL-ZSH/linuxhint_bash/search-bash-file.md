





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How do I search for a file in bash?

7 months ago
by Omar_Farooq
The file system is the main thing in any operating system because it holds all
your data within the files and folders in different formats. What about
searching those files via the terminal shell using some commands? If you don’t
have any idea about bash searching, this article is for your great help. We
will discuss simple commands to do a bah file search. Let’s get started. Let’s
say you have a bash file currently stored in the home working directory of
Ubuntu 20.04. We will be listing all the contents of a current working
directory using the “ls” instruction on our Ubuntu’s terminal shell. It might
be possible that the same name file can be located at other locations.

Method 01: Locate

Let’s start with the most basic instruction, “locate”, to find the file by name
from our system. The “-c” option of “locate” instruction is specifically
designed to get the total count number for the specific file in the system.
Let’s take a look at its first option, “-c,” upon using it within the
instruction along with the name of a file “new.sh”. It returns a total of 5
files with this name.
Here is the “-n” option of “locate” instruction to display the number of
records for a specific file on your terminal screen as per the user’s choice.
You need to mention the number in this command to display the specified number
of file records. While at the home directory, we ran this instruction with the
“n” option and value 1 to display a single record for the search result of file
“new.sh”. It returns the single record for the file path of this file. This
path will be the closest to your home directory or root folder, i.e. /home/
Linux/new.sh.
When we have used this instruction with the updated total number “3” for the
option “-n” to display the search result for the file “new.sh”, it returns the
total of 3 records on our shell screen. It shows that the file is located
within the Trash folder as well.
On running the “locate” command with the “-n” option of value 5, we have got 5
search records for the file “new.sh”. There is another file with the
“new.sh.swp” name in our directories. Also, there is the same name file in the
“var” directory of Ubuntu’s file system.
The “-b” option in the “locate” instruction can do your search for the exact
name file from your directories. So, we have to use it with the file name in
single inverted commas as shown. It gives a total of 3 records because the same
name file has been located at only 3 locations.
The “locate” instruction of Linux can also be used to get the information
regarding your current database. You need to use the “-S” option along with it,
and it will return you the path to the database, the total number of
directories and files on your system, the total number of bytes in file names,
and the number of bytes to store our records as displayed.

Method 2: find

There is a “find” instruction in our Linux system that can be used to search
for any specific file. It also came up with many options to display different
results. The first option is the “-name” option to search for a file with its
name in double inverted commas. You can utilize this option alongside the path
to some directory to search for a file. If you don’t want to utilize the path,
leave it with “.” as we did below. It displayed a total of 3 records with the
same name file.
You can also use the explicit path to examine the file in it. Here we have
given a path to the ‘Desktop’ folder. It gives us the single record for an
exact match of the file name “new.sh”.
Let’s say you want to search for a file symbolic links for the “.sh” extensions
of files. You need to utilize the “-L” option and the path and “-name” option
in your command. The “*” in the name specification is used for searching “all”
the bash files with “.sh” extensions. It returns a total of 4 records on our
screen.
On using the “/etc” path in the “find” instruction with the “-L” option, it
returns many records for bash files. Some of them are open for use by anybody,
and some are not permissible.
Just in the same way, we have used the “find” instruction with the “-L” option
to search all the “txt” files from the system. It returns many records on our
display.
Here comes another option, “-type,” to use in the “find” instruction to specify
a file type, i.e. file or directory. We have used this option to search for
type “file” for bash file and got a single result, i.e. new.sh in Desktop
folder.
If you don’t add the path, it will search the directories as below.
The use of the “–type” option with “f” without any file name will also return
all hidden files.
Using “l” for the “-type” option will return the symbolic links.
The use of “d” for the “-type” option in the “find” instruction will return all
the directories.
You can also use the “-size” option to search for the specific size files from
your system.

Conclusion:

This tutorial demonstrated two simple yet elegant methods to search for any
file using the shell terminal. We have used the “locate” and “find” instruction
along with many options for our user’s ease and learning, i.e. “-c”, “-n”, “-
b”, “-type”, “-name”, “-L” and many more. We hope this will be unlimited
assistance to new users of bash.


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

Linux Hint LLC, [email protected].com
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
