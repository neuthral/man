





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Resolve Issue: Bin/Bash^M: Bad Interpreter: No Such File Or Directory

6 months ago
by Omar_Farooq
While working on different operating system platforms, we encountered a bundle
of errors, i.e., performing some coding or installation. When we work in bash,
we may encounter hundreds of bash related-errors. You could believe there is a
permissions problem and attempt executing the chmod 777 instruction to give the
bash script file all rights, but it will not solve the problem. It Is initiated
by the carriage return “M”. The line feed symbol is used in Linux to indicate
the finish of a line; meanwhile, the two-character combination CR LF is used in
Windows. Your document has Windows line ends, which causes Linux to be
perplexed. Let’s see the solutions for it.
$ /bin/bash^M: bad interpreter: No such file or directory
In this tutorial, we will look at how to fix the problem that occurs while
running bash or.sh file on a Linux environment. The poor interpreter is another
name for this error. You might believe this is a permissions constraint and try
using the chmod +x command to grant the shell script file all the required
privileges, but this will not resolve the issue. The script specifies that it
would be run using the “/bin/bash^M” shell. There is no such file; instead, “/
bin/bash” is used. The “^M” character stands for carriage return.
The line feeding character is often used in Linux to indicate the ending of a
line, whereas the two-character sequence CR/LF is often used in Windows-like
operating systems. The file contains Windows line endings markers, which causes
Linux to be perplexed. In a bash script file, how can I see CR or LF encoding
characters? You may also view the line end characters as LFCR or LFCR by View →
Show Symbol → Show End of Line. An example of a file with CR or LF characters
is shown below:
The above and below displays are not available in the basic notepad editor;
instead, you must install Notepad++, an advanced version of notepad. To fix the
error in the Windows operating system, open the bash script file in the
Notepad++ editor and then go to the preferences tab via the settings menu as
below. Close the window after choosing Unix/OSX as the format. Afterwards, save
and close the file.
Preferences → New Document/Default Directory Tab → Setting → Preferences → New
Document/Default Directory Tab → Chose New Document Format →

Using Stream Editor Command

In UNIX, the SED command accounts for a line-by-line editor, and it can perform
a wide range of file procedures such as scanning or searching, finding and
replacing, inserting, and deleting. The SED command is most commonly used in
UNIX and Linux-like operating systems for substituting or finding and
replacing. Delete the CR characters that aren’t supposed to be there. You can
use (sed) the command below in the image to accomplish this task:

By Using Dos2UNIX Utility

Dos2Unix is a Programme that converts DOS to UNIX. To resolve the shell script
for the Unix-Linux like operating systems, install the dos2unix utility and
then run the dos2unix command given below:
$ dos2unix FILENAME.sh
If you get the command not found error, first install the dos2unix utility by
running the command below from a Linux command line shell:
$ sudo apt-get install dos2unix
You can use the unix2dos command to convert the file back to DOS format.
In a bash script file, how can I view CR LF characters? Attempt file, file -k,
and finally dos2unix -ih command as in below screen: Attempt file, file -k, and
finally dos2unix -ih command as in below screen. For the Linux/Unix line “CR,”
it simply prints text.
You may install it on macOS operating system using Homebrew as follows:
$ brew install dos2unix
Then do the execute the below command to convert the file in dos format to UNIX
format:
$ dos2unix FILENAME.sh

What Is The Purpose Of The Command dos2unix

DOS2UNIX is a utility that translates DOS line endings CR (carriage return) +LF
(line feed) to UNIX line encodings in text files LF (line feed). It can also
convert between UTF-16 and UTF-8 characters. You can translate from UNIX to DOS
while utilizing the unix2dos command. Expectantly, this will resolve the
problem you were having.

By Using Vim Editor

If you don’t have the DOS2UNIX Utility installed on your LINUX operating
system, you might use the VIM editor to transform your shell script’s format to
UNIX. Use the succeeding instruction to open the file in VIM Editor:
vi FILENAME.sh
OR
vim FILENAME.sh
If you’re not in the current directory or folder where your bash file script is
located, type the directory’s full path, as I did. But if you are in the same
directory or folder, you can run the command directly as given above. VIM is a
progressive form of the VI editor. Both VI and VIM commands do the same work.
Run the command underneath to change the file format to the UNIX operating
system:
$ :set ff=unix
Then, using the commands below, all changes are saved and close the file in the
editor, write the file, and close it. Now you’re done. You can convert the
format of your shell script to UNIX through any of the approaches described
previously. We hope the above information helped resolve your problem.
$ :wq!

Conclusion

This is all about the use of simple methods to resolve the issue “bin/bash^M:
bad interpreter: No such file or directory”. All the examples used here are
simple and easy to implement. We hope that you like it and learn more from it.


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
