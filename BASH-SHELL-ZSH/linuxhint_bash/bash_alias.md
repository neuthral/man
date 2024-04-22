





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to use bash aliases

1 year ago
by Fahmida_Yesmin
Most of the users like to use shortcuts for running commands. There are many
commands in Ubuntu that we need to execute regularly. It will be very helpful
for us if we can run those common commands by typing shortcut commands. Using
bash aliases, Ubuntu users can easily create shortcut commands of the large
commands those are used frequently. Bash aliases not only make the task easier
but also save the time of the users. The user can declare alias temporary or
permanently. The temporary aliases can be used as long as the session of the
user exists. If the user wants to use shortcut commands every time the session
starts, then he or she has to create permanent alias by using~/.bashrc and
~/.bash_profile files. This tutorial shows how you can create and use bash
aliases in Ubuntu by using some examples.

Example-1: Temporary bash alias declaration

Declaring a temporary bash alias is a very simple task. alias command is used
to create a shortcut of any command. For example, the ls -la command is a very
commonly used command to display the list of all files and folders with
permission. You can create the shortcut of this command by using the alias
command. Suppose the shortcut command will be L. Run the following commands to
create the shortcut of ls -la and test the command.
Check the output of the ls -ls command
$ ls -ls
Create alias command for ls -la
$ alias L="ls -la"
Test the shortcut of ls -ls
$ L
Output:
After executing the above commands, the output of the “L” command that has been
created by the `alias` command and “ls -la” commands are the same.
If the user closes the session and starts a new session again, the alias
command will not work.

Example-2: Permanent bash alias declaration

To solve the above problem, you can create permanent alias command. Suppose you
want to create a shortcut of the “mkdir” command with the alias name “C” and
use it permanently. Open ~/.bashrc file in any editor, add alias command in
that file, save the file and run the `source` command to re-execute the file
with added alias command.
Run the following command to open the ~/.bashrc file in nanoeditor.
$ nano ~/.bashrc
Add the following `alias` command in the file and save it.
alias C=”mkdir”
Re-execute the file to make the command active.
$ source ~/.bashrc
Run the following commands to test the shortcut command of “mkdir”.
$ C TestDir
$ ls
Output:
The following output will appear after executing the above commands.

Example-3: Use of `alias` for `cd` command

The `cd` command is used to change the current working directory. The way to
use the `alias` command for different types of `cd` commands is shown in this
example. The `cd ..` command is used to set the directory one level up from the
current directory. Run the following commands to create the alternative command
of `cd ..` and test the created `alias` command.
$ alias p_dir='cd ..'
$ p_dir
Output:
The following output will appear after executing the above commands.
The `cd ../../` command is used to set the directory two levels up from the
current directory. Run the following commands to create the alternative command
of `cd ../../` and test the created `alias` command.
$ alias 2p_dir='cd ../../'
$ 2p_dir
Output:
The following output will appear after executing the above commands.

Example-4: Use of `alias` for `bc` command

The `bc` command is used for mathematical operations with fractional data. The
way to create alternative command of the `bc` command has been shown in this
example.
Run the following commands to create and test the `alias` command of the `bc`
command.
$ alias cal='bc -l'
$ echo "scale=2; 37/2" | cal
Output:
The following output will appear after executing the above commands.

Example-5: Use of `alias` for root privilege

The `sudo -i` command is used to set the root privilege. The way to create the
alternative command of the `sudo -i` command has been shown in this example.
Run the following commands to create and test the `alias` command of the `sudo
-i` command.
$ alias admin='sudo -i'
$ admin
Output:
The following output will appear after executing the above commands.

Example-6: Use of `alias` to find the specific command from history

The `grep` command is mainly used to search the specific content in a file or
text, and the `history` command is used to keep the history of the previously
used commands. Sometimes it requires finding out the history of previously used
specific commands by using `grep`. If this task needs multiple times, then
creating the alias command to find the specific command from the history using
`grep` is a good option. The use of the `alias` command to find the specific
command from history using `grep` has shown in this tutorial.
Run the following commands to create and test the `alias` command to find the
particular command from the history.
$ alias f_cmd='history|grep'
$ f_cmd cat
$ f_cmd pwd
Output:
The following output will appear after executing the above commands.

Example: Use of `alias` to count the total number of files of the current
directory

There are many ways to count the total number of files of the current directory
in bash. The simple way to count the total files of the current directory is to
use `find` and `wc` commands. By creating an `alias` command to do this task
makes the task easier.
Run the following command to create and test the `alias` command to count the
total number of files of the current directory.
$ ls
$ alias totalFiles='find . -type f | wc -l'
$ totalFiles
Output:
The following output will appear after executing the above commands.

Example-3: Remove bash alias

The `unalias` command is used to remove the previously created aliascommand.
After using this command, the alias will not work. So, if you think you don’t
want the shortcut command anymore, then you can use the alias command to remove
it permanently.
Run the following commands to check the use of the `unalias` command to remove
the previously created shortcut command.
$ alias d=’date’
$ d
$ unalias d
$ d
Output:
The following output will appear after executing the above commands.
Remove or comment on the line that is used for creating the `alias` command in
the ~/.bashrc file and re-execute it for deleting the permanent alias.

Conclusion:

You can use the `alias` command for various purposes for creating a shortcut of
the commands. This tutorial will help understand the basic use of the `alias`
command so that the bash users can easily apply this command to create a
shortcut of the regularly used commands.


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
