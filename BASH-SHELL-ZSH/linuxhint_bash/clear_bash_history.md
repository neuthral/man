





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to clear bash history

2 years ago
by Fahmida_Yesmin
Different types of commands are executed from terminal to do various general or
administrative tasks. Sometimes the user needs to run some commands that
contain confidential information, and the user wants to delete the history of
the commands from the terminal after execution. The user can remove all bash
history or a specific history by using ‘history’command.But there are many
other commands to remove history information permanently. You can also remove
history by removing the content of the .bash_history file. How the bash history
can be cleared by the mentioned options are shown in this article.

Clear all bash history by using history command:

Run the following command to create some bash history. ‘date’command will
display the current date and time. ‘ls’command will display the list of the
files and folders of the current location. ‘clear‘ command will clear the
terminal screen.
$ date
$ ls
$ clear
Run the history command to display the current bash history.
$ history
Run the following command to clear the terminal history and exit from the
terminal.
$ history -c && exit

Clear specific bash history entry by using history command:

Run the following command to create some bash history. The first command will
print ‘Hello’ message. The second command will print the current logged in
user’s name. The third command will take input from the user and store in the
variable $a. The fourth command will print the value of $a.
$ echo "Hello"
$ who
$ read a
$ echo $a
Run the ‘history’ command to display the current history.
$ history
Run the following commands to delete the 4th entry of the history and print the
history after delete.
$ history -d 4
$ history
Here, the entry of ‘echo $a‘ is removed from the history entry.

Clear all history by removing .bash_history:

If the ~/.bash_history file exists and stores the history information in that
file, then you can run the following command to remove the file.
$ rm ~/.bash_history

Prevent storing history information permanently:

Run the following unset command to prevent creating a history file and exit
from the terminal. If you open a new terminal after running the following
command, then no previous history information will display.
$ unset HISTFILE && exit
When the value of HISTSIZE is set 0, then no history entry will be stored
permanently. The following command will stop storing history information and
terminate the terminal. When a new terminal is opened after running this
command, then no previous history information will display.
$ HISTSIZE=0 && exit
If you want to remove the history file forcefully, prevent creating a history
file, and terminate from the terminal, then run the following command. After
that, if a new terminal is opened, then it will work from the blank history.
$ rm -f $HISTFILE && unset HISTFILE && exit
The following command can also be used for deleting the current history
information permanently and terminate from the terminal. When a new terminal is
opened after running this command, then no previous history information will
display.
$ kill -9 $$
Conclusion:
This article shows how bash history can be cleared and prevent storing history
information permanently by using various bash commands. If the bash users work
with normal bash commands, then he/she can use the history commands mentioned
above to remove particular or all history information when requires.  But if
the users work with sensitive data, then it is better to select those commands
shown in this article to prevent storing history information permanently.


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
