





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Reload Bashrc

5 months ago
by John_Otieno
If you are just getting started with the Linux terminal, you will need to
familiarize yourself with the .bashrc file.
This tutorial will cover the fundamentals of the .bashrc file. We will cover
what it is, how to edit it, and how to apply the changes made to a .bashrc
file.

What is the .bashrc file?

The .bashrc file is a shell script that governs how the bash shell launches. It
is used to initialize an interactive bash shell session based on the
configuration in the file.
The bashrc file is responsible for holding configuration directives such as
environment variables, command aliases, bash command history, auto-completion,
coloring and customization variables, and many more.

Where can I find the .bashrc file?

By default, the .bashrc file is located in any user’s home directory that uses
bash as their shell.
It is a hidden file (meaning it starts with a period). To view the .bashrc
file, you can use the -a option in the ls command.
An example is as shown:
$ ls -la
The command above should return all the files in the home directory including
hidden files and directories.
total 40
drwxr-x--- 5 ubuntu ubuntu 4096 May 25 01:21 .
drwxr-xr-x 3 root   root   4096 May 15 01:07 ..
-rw------- 1 ubuntu ubuntu  479 May 25 01:25 .bash_history
-rw-r--r-- 1 ubuntu ubuntu  220 May 15 01:07 .bash_logout
-rw-r--r-- 1 ubuntu ubuntu 3771 May 15 01:07 .bashrc
drwxr-xr-x 3 ubuntu ubuntu 4096 May 24 16:49 .cache
drwxr-xr-x 2 ubuntu ubuntu 4096 May 15 01:07 .landscape
drwxr-xr-x 5 ubuntu ubuntu 4096 May 24 16:49 .local
-rw-r--r-- 1 ubuntu ubuntu    0 May 25 01:21 .motd_shown
-rw-r--r-- 1 ubuntu ubuntu  807 May 15 01:07 .profile
-rw------- 1 ubuntu ubuntu   44 May 25 01:21 .python_history
-rw-r--r-- 1 ubuntu ubuntu    0 May 16 18:59 .sudo_as_admin_successful

How to Edit the .bashrc file

The .bashrc file is a plain text file. However, it does require a specific
format when adding particular directives.
You can learn about the Bash startup file in the resource below:
https://www.gnu.org/software/bash/manual/html_node/Bash-Startup-Files.html
For now, edit the .bashrc file with your text editor and add a simple echo
command:
$ nano ~/.bashrc
Add the following line at the end of the file:
echo "Hi folks"
Save and close the file.
You can use the cat command to view the contents of the .bashrc file.
$ cat ~/.bashrc | less

Reload .bashrc

After editing the .bashrc file, you will need to reload it to apply the
changes. You can do that using the source command:
$ source ~/.bashrc
The command above should load the .bashrc file and print the message we added
earlier.
$ source .bashrc
Hi folks
You can also use a shorter version:
$ . ~/.bashrc
Hi folks
NOTE that since the .bashrc file is loaded in every new shell session, you can
reload the file by simply starting a new shell session.

Conclusion

Throughout this article, we discussed the fundamentals of editing the .bashrc
file. We also discussed reloading your .bashrc file without starting a new
shell session.


About the author


John Otieno

My name is John and am a fellow geek like you. I am passionate about all things
computers from Hardware, Operating systems to Programming. My dream is to share
my knowledge with the world and help out fellow geeks. Follow my content by
subscribing to LinuxHint mailing list
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
