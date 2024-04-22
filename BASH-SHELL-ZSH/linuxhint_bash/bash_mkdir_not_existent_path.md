




















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash ‘mkdir’ not existent path

4 years ago
by Fahmida_Yesmin
‘mkdir’ is the basic built-in shell command of Linux to create a new directory
or folder from the terminal. You can create a new directory by giving new
directory name with ‘mkdir’ command. But if the directory name already exist
before executing the command then it will display an error message.  When you
want to create a directory in a path that does not exist then an error message
also display to inform the user. If you want to create the directory in any
non-exist path or omit the default error message then you have to use ‘-p’
option with ‘mkdir’ command. How you can use ‘mkdir’ directory to create
directory or folder in non-exist path and with permissions are shown in this
tutorials.

Create simple directory or folder

Suppose, you want to create a directory in /home folder named ‘mydir’. Run the
following command to create the directory. If no directory exists with the name
‘mydir’ before then the command will be executed without any error. Run
‘ls’command to check the directory is created or not.
$ mkdir mydir
$ ls

Create multiple directories

Run the following command to create multiple directories using ‘mkdir’command.
Three directories, temp1, temp2 and temp3 will be created after executing the
command.
$ mkdir temp1 temp2 temp3
$ ls

Create directory when the directory path not exist

Suppose, you want to create a directory in a path, /picture/newdir/test. In the
current system, ‘mydir’ directory has no directory or files in it. So, the path
is invalid. Run the ‘mkdir’ command with the above path. An error message will
appear after running the command.
$ mkdir /picture/newdir/test\
If you want to create non-exist path forcefully by creating all non-exist
directories mentioned in the path from terminal then run ‘mkdir’ command with
‘-p’ option.
$ mkdir -p /picture/newdir/test
Now, check the directories are created or not by running the following
commands.
$ cd picture
$ ls -R
 Bash mkdir not existent path  Bash mkdir not existent path

Create directory with permission

When you create a new directory then a default permission is set for the newly
created directory.
Create a new directory and check the default permission by executing following
commands. ‘stat’ command is used to check current permission of any existing
directory. The default directory permission is ‘rwxr-xr-x’. This indicates
directory owner has all permissions, and group users and others users have no
write permission.
$ mkdir newdir1
$ stat newdir1/
‘-m’ option is used to set the directory permission at the time of directory
creation. Run the following commands to create a directory with all permissions
and check the permission using ‘stat’ command. The output shows all types of
users have all permissions.
$ mkdir -m 777 newdir2
$ stat newdir2/

Create directory using script

You can test any directory is exist or not by using bash script. Create a bash
file and add the following code to create the new directory after testing the
directory is exist or not by using ‘-d’ option. If the directory exists then it
will show the message, “Directory already exists”, otherwise new directory will
be created.
#!/bin/bash

echo -n "Enter the directory name:"
read newdirname
if [ -d "$newdirname" ]; then
echo "Directory already exists" ;
else
`mkdir -p $newdirname`;
echo "$newdirname directory is created"
fi
Run the script and check the directory is created or not.
$ bash create_dir.sh
$ ls
Hope, you will be able to use ‘mkdir’ command with various options more
effectively after reading this tutorial. Thank you.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
