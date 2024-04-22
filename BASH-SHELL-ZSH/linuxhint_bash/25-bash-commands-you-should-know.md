





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


25 Bash Commands You Should Know

7 months ago
by Omar_Farooq
Commands are said to be basic operations in Linux that are designed to perform
specific tasks. If you are quite new to the bash environment and want to learn
some commands for its console, then this article will be a bonus for you. We
will be going to demonstrate the use of some most-used and basic commands of
“bash” which are most popular among developers.

1. pwd

Let’s get started with the launch of the Ubuntu 20.04 shell. If someone is new
to Linux and doesn’t know about the bash current working directory in the
terminal, they can write the “pwd” single word command and execute it on the
shell i.e. “print working directory”.
Regardless of your current location, it will return the path of your current
working directory.

2. List “ls”

Linux came up with a list “ls” instruction to display the list of all files and
folders for the current directory. The use of the “-l” option in this
instruction can give you the output in a detailed view.
Without moving to another directory, you can find its contents using the “ls”
instruction. You need to utilize the path to the folder as we have done in the
image. The use of the “-a” option for “all” can also display the hidden files
and folders of the current directory.

3. touch

Linux terminal provides you the opportunity to create any type of file using
its “touch” instruction. We have created a text file “new.txt” in the current
home directory as shown below.
You can also create any bash, C#, C, C++, Python, or text file as we have
created below.

4. cat

To see the file content or data on your terminal screen as text, you can
utilize the “cat” instruction along with the name of a file. The data in text
form will be displayed as shown.

5. mkdir

For directories, you need to use the “mkdir” instruction along with the new
directory name on the shell. Create more than 1 directory using the names of
directories in the “mkdir” query.

6. rm

The Linux terminal’s “rm” instruction can be used to remove any file from the
current working directory. So, we have 4 different files in the home folder and
we have used the ‘rm’ instruction to remove 3 of them one by one.
Only 1 file is left in the folder.

7. rmdir

The “rm” instruction cannot be used to remove folders. We have to utilize the
Linux “rmdir” command to delete single or many directories in Linux when the
folders are empty.

8. echo

Using the “echo” statement of Linux, you can print any text message on the
shell as below.

9. cd

If you want to move in within another directory or move back to the directory
you were in before, you can do so by “cd” instruction. We have used it to move
2-directories forward.
To move back, use double dots with the “cd” command. You need to utilize the
same number of “/” with double dots for more than one directory movement.

10. mv

The “mv” instruction, while applying on files, can change their names to new
names i.e. “new.txt” to “test.txt”.
It can also move one file to another location as we have moved “test.txt” from
home to the “test” folder.

11. cp

The “cp” Linux instruction can copy any file to another location without
deleting it from its current location i.e. we have copied ‘test.txt’ from the
“test” folder to the “home” folder.

12. find

The bash “find” instruction uses the “-name” option to search for any file at
any location.

13. man

The bash “man” instruction is the all-knowing instruction. Using it with any
utility or command name can return you to the manual of that particular
command.
The man page for “sudo” instruction is shown below.

14. less

The Linux “less” instruction can quickly open your file in the terminal itself
for display purposes.
It doesn’t permit you to make variations to the file as we can do in the
editors.

15. clear

The clear instruction of bash can make your terminal clean and remove all the
executed instructions from your terminal screen.

16. alias

Alias or “Aliases” command of bash lets you make use of shorter forms for
commands. In the illustration, we used the alias instruction to create an “l”
alias for the ‘-ls –l” command.
The result of using “ls –l” and “l” is the same. Thus, you can use “l” instead
of “ls –l”.

17. unalias

The “unalias” command can simply make the created alias completely non-
functional.

18. sh

To create bash code in the terminal, you can use the “sh” instruction to create
a bash console.

19. chmod

You can change the rights assigned to some file or folder in bash using the
“chmod” instruction. You can see that we displayed the details of the “new.sh”
i.e. only read and write rights.
The “chmod” instruction uses “0-7” numbers to update the privileges. The file
“new.sh” has execution rights as well.

20. chown

You can also change the owner and user of any file or folder in bash. For this,
we utilized the “chown” instruction along with the new owner and user name
linked using “:”.

21. free

The “free” bash instruction with “-h” can let you see the details of storage
usage at your end.

22. grep

The Linux “grep” instruction with the “-R” option can make your search
recursively.
It can be used without the file names as shown.
The use of “-v” can make you exclude the searched pattern from the file.

23. Passwd

The Linux “passwd” command can let you change your currently logged-in user’s
password. Add your current password correctly and then add a new password to do
so.

24. sudo su

The “su” instruction can make you log in as a root user at your shell. For
this, you need to add your “root” account password.

25. exit

If you want to exit the “root” console you have just opened, you can try the
“exit” instruction at its console. You will be back to the normal user console.
When you use the “exit” instruction on a normal terminal, it will close your
bash terminal.

Conclusion

Within this article, we discussed the most-used and basic commands of bash. We
illustrated the use of each command through picture illustration by
implementing them on our Linux shell. All users can implement them in different
ways for better understanding.


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
