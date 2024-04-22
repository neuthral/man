





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Using and Customizing Bash Command History

3 years ago
by Karim_Buzdar
The bash shell is the default command line environment available in most Linux
distributions. Similar to all shell environments, it keeps a record of commands
that have been executed previously by the user. This record is kept and
maintained even we restart our system.
You might know the basic use of history command, but it can do a lot more than
that. Bash history is usually stored in the file ~/.bash_history. It enables
you to recall and reuse the stored record in an efficient way to get the best
out of bash history saving feature. Not only this, but you can also customize
and control the bash command output in the way you want.
In this article, we will explain how to effectively use and customize the bash
command history to get the most out of its features.
We have used Debian 10 for running the commands and procedure mentioned in this
article.

Using bash command history


1. Viewing the bash History

To view the entire history of shell commands, you can run the following command
in Terminal:
$ history
It will list the entire history for a specific user from the history file
stored specifically for that user. You will see all the commands starting with
a number allocated to each of them. It will list the older commands at the top
starting with number 1 and the newer commands at the bottom.

2. Searching the History Output

You can also search for a specific keyword from the history output. Pair the
history command with grep and a specific keyword to search for commands that
match your specified keyword as follows:
$ history | grep [keyword]
For instance, to list all the commands that include the keyword “find”, the
command would be:
$ history | grep find

3. Viewing last n commands

The history command by default lists the last 1000 number of commands executed
by a user. In case, you want to list only a specific number let’s say n number
of last executed command, run the following command in Terminal:
$ history n
For instance, to list the last 7 executed commands, the command would be:
$ history 7
To view the number of the last n run commands that includes a specific keyword,
you can use the following syntax:
$ history | grep keyword |tail -n
An example of this would be to view the last 4 executed commands with the
keyword “java”.
$ history | grep java |tail -n

4. Viewing oldest commands

To view the oldest n number of commands, you can use the following syntax in
Terminal:
$ history | head -n
To view the oldest n number of commands that includes a specific keyword, use
the following syntax:
$ history | grep keyword |head -n
An example of this would be to view the oldest 4 executed commands with the
keyword “java”.
$ history | grep java |head -4

5. Clear Bash history completely

To remove the entire bash history, run the following command in Terminal:
$ history -cw

Customizing bash command history

To customize bash command history, we will have to make changes in the
~/.bashrc file. To edit the ~/.bashrc file, use the following command:
$ nano ~/.bashrc
Once you are done with modifying the file, use Ctrl+O and Ctrl+X to save and
close the nano editor.
Then run the following command to apply the modifications:
$ source ~/.bashrc

1. Add Date and Timestamp to Bash History

If you want to display date and timestamp along with the command history, you
can do that by adding the following line in ~/.bashrc:
$ export HISTTIMEFORMAT='%F, %T '
Now run the history command and it will show the command history with
corresponding data and timestamp.

2. Increasing size of Bash History

Bash by default keeps 500 commands in the history list. However, we can change
this value using the HISTSIZE value.
To view the current size of bash history, run the following command in
Terminal:
$ echo $HISTSIZE
Similarly, the default size of the bash history file is 500. It is the maximum
number of entries that are contained in the history file.
To increase the size of bash history let’s say 10000, add the following lines
in  ~/.bashrc file:
$ HISTSIZE=10000
$ HISTFILESIZE=10000
To verify if the bash history size has changed successfully, run the following
commands in Terminal:
$ echo $HISTSIZE
$ echo $HISTFILESIZE

3. Append Bash Commands to History File

When a bash session is closed, you can choose to whether overwrite or append
the commands in the history file using the histappend variable. To view the
current settings, run the following command in Terminal:
$ shopt histappend
The “on” in the output shows histappend option is enabled and the commands will
be appended in the history file instead of overwriting. While “off” shows,
histappend option is disabled and the file will be overwritten.
Open the ~/.bashrc file and:
Add following line, if you want to append the commands to the history file
instead of overwriting:
$ shopt -s histappend
Or add the following line, if you want to disable the append option and want to
overwrite the file on exit:
$ shopt -u histappend

4. Store Bash History Immediately

Bash by default only saves the session to the bash history file once the
session ends. To change this default behavior and make it to instantly save
each command you have executed, you can make use of PROMPT_COMMAND.
Edit the ~/.bashrc file and add the following line:
$ PROMPT_COMMAND='history -a'
Now whenever you execute any command, it will be immediately added to the
history file.

5. Control Bash History

We can control the way bash saves our command history through the HISTCONTROL
variable. We can specify it to ignore duplicate entries, and/or to ignore
entries with leading white spaces.

* ignorespace – eliminates commands that begin with a space history list.
* ignoredups – eliminate duplicate commands.
* ignoreboth – Enable both ignoredups and ignorespace
* erasedups- eliminate duplicates from the whole list

To apply these functions, open the ~/.bashrc and add the following line with
values separated by the colon as follows:
$ export HISTCONTROL=ignorespace:ignoredups

6. Ignore Specific Commands

We can also control which commands to ignore in history using a variable
HISTIGNORE. It is a colon-separated list of patterns in which we can specify
all the commands that we want to ignore from history.
For instance, if we do not want to list the basic commands such as history, ls,
pwd commands in the history list, then we add the following line in the
~/.bashrc  file:
$ export HISTIGNORE="history:ls:pwd:"
With Linux bash command history, you can do a lot more than just repeating the
old commands. In this article, we have learned how to use the bash history to
view the commands that have executed previously and also learned to control the
way bash saving the command history.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
