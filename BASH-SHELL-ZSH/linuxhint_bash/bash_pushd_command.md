





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash `pushd` command

3 years ago
by Fahmida_Yesmin
The Linux users may need to switch between many directories for doing a
particular task and it is a time consuming task for the user to change the
directory location frequently from the terminal. If the previously visited file
or folder path information can be stored or retrieved from the terminal, then
the user will be able to navigate the file system easily. There is a command in
bash to solve this issue. To store the current directory information in the
stack before moving to another directory location, `pushd` command is used in
bash. This command works on LIFO (Last In First Out) based. This means, the
directory information will be stored at the end of the stack location.  How you
can apply `pushd` command to navigate file system on Ubuntu is explained in
this tutorial.
Syntax:
pushd
pushd [drive] path

* When `pushd` command is used without any drive and path then the list of
  previously pushed directory path will display.
* When `pushd` command is used with path only then the current working
  directory information will store in the stack.
* When `pushd` command is used with driver and path then the driver information
  will store in the stack.


Example-1: Using pushd with path and without path

Run the following commands to get the current directory information and
retrieve any previously stored directory information. If no `pushd` command is
executed before then “no other directory” message will print for the first
command. When` pushd` command will execute with “Videos” then two entries will
store in the stack. These are Videos and home directory(~). if `pushd` command
will execute again then the entries of the stack information will display and
the directory will change by the last entry of the stack that is home
directory.
$ pushd
$ pushd Videos
$ pushd
The similar output will appear after running the above commands.

Example-2: Using `pushd` with drive and path

`pushd` command can be used with the full path of any directory. The first
command `pwd` will print the current working directory information. The second
command will push the “Pictures” directory by using full path of this directory
with `pushd` command and the current directory will be changed to “Pictures”
folder.
$ pwd
$ pushd /home/Fahmida/Pictures

Example-3: Check `pushed` directory list

The following commands are used to display the directory information from the
stack those are inserted by `pushd` command. `dirs.` command displays the
inserted directory name of the stack and `dirs –v` command displays the
directory name of the stack with index value.
$ dirs
$ dirs -v

Example-4: Use `pushd` with positive and negative directory index

The directory information can be pushed by using positive or negative index
value with `pushd` command. This example shows the use of index in `pushd`
command. The following command is used here to show the current stack
information with index value.
$ dirs –v
The following command will change the current directory to the folder that
exist in the index 1 of the stack. Here, Videos folder exists at the index 1.
After executing the command, the current directory will Videos and the index
order will be changed.
$ pushd +1
The following command will count the index value from the right and change the
current directory to home directory according to the index value.
$ pushd -2

Conclusion

If the user pushes the directory to the stack by using `pushd` command then the
user doesn’t need to re-type the directory information multiple times to switch
from one directory to another. Hope, the reader will able to use `pushd`
command properly after reading this tutorial.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
