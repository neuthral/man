





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How do I fix shell script permission denied in Linux?

1 year ago
by Talha_Saif_Malik
In Linux, you may experience a “permission denied” error while trying to list
files or execute a shell script inside the directory which does not have
sufficient permissions. As Linux operating system is very concerned about its
security, the “root” has complete access to all directories and files for
making changes. Therefore, other users may not be permitted to make such
changes.

Permission denied error in shell script execution

In our system, we have a shell script named “samplescript.sh”. Now, as a normal
user, we will try to execute this hell script.
$ ./samplescript.sh
The output will show you the “permission denied error” because you do not have
the permission to execute this script.

Fixing permission denied error

To avoid this “permission denied error,” the only thing you have to do is to
add “x” or “execution” permission to this “samplescript.sh” file and make it
executable for a typical user.
Firstly, check out the file permission of the shell script.
$ ls -l samplescript.sh

Using chmod command

The chmod command lets a user change permission of a file using a reference
file, numeric or symbolic mode.
Syntax of chmod command:
chmod flags permissions filename

* flags: user can set these additional options
* permissions: this part of the chmod command is used to define file
  permissions which include: “r” for read, “w” for write, and “x” for making it
  executable.
* filename: specify the filename whose permissions you want to change.

Whereas “u+x” will make the script executable for the current Linux user,
though the group owner or other “users” already have access to execute it.
$ chmod u+x samplescript.sh
Execution of the above-given chmod command should change the “samplescript.sh”
into an executable format. Now execute the “ls” command to confirm the changes
we made into the permissions of this shell script.
$ ls -l samplescript.sh
Utilize the cat command to view the content of this “samplescript.sh” script
file.
$ cat samplescript.sh
Finally! It’s time to execute the shell script.
$ ./samplescript.sh
The output declares that we have successfully fixed the permission denied error
of this “samplescript.sh” shell script.

Conclusion

Every Linux user should know the quick fix for the “permission denied” error
encountered while executing any shell script. “chmod” command resolves this
issue by changing the script’s file permissions and allowing it to in an
executable format for the current user. This article has provided you a step-
by-step procedure for fixing the shell script “permission denied” execution
error.


About the author


Talha Saif Malik

Talha is a contributor at Linux Hint with a vision to bring value and do useful
things for the world. He loves to read, write and speak about Linux, Data,
Computers and Technology.
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
