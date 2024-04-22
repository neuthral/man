





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Reload a Tmux Config File

11 months ago
by Ali_Imran_Nagori
Tmux is an open-source terminal multiplexer application for efficiently
managing multiple terminal windows. People who have previously used the
Terminator application are mostly familiar with the notion of tab management in
Linux Terminal. With Tmux, we can split the terminal into a number of panes. We
can adjust these panes by moving around, resizing, and switching between them.
This helps curb the pain of managing multiple windows and tabs of the Gnome
terminal.
In general, when you close an SSH connection, the corresponding remote terminal
sessions are also closed. Here comes the Tmux to help as it preserves those
sessions when the SSH connection is terminated.
After installing Tmux, you will not find any icon associated with it. It will
not appear as a separate application. Instead, we will have to invoke it from
the Gnome Terminal itself. We will later see how to do this.
Note: We used the “Ctrl+b” as the prefix. If you configured some other prefix,
then replace the command with your prefix in this guide.

What Will We Cover?

In this guide, we will explore how we can install Tmux and, more specifically,
“How to reload a Tmux config file.” We will use Ubuntu 20.04 as the base system
for this guide. Let us first start with installing Tmux.

Installing Tmux on Ubuntu 20.04

Major operating systems, such as Linux, macOS, and Windows Subsystem for Linux
(WSL) provide Tmux software packages from their official repository. So, to
install Tmux on Ubuntu 20.04, we can simply use the package manager or the
Software center as described below:
1. To install Tmux using package manager, simply run the command:
$ sudo apt install tmux
2. To install Tmux using the Software center, open the Software center, search
for Tmux, and click “Install”:

Launching Tmux

Once the Tmux is installed, we will have to use the Gnome terminal to invoke
it. One may encounter the following error when trying to run the “tmux”
command:
“open terminal failed: missing or unsuitable terminal: xterm-256color”
To overcome this error, type “export TERM=xterm” on the terminal and hit enter.
Now, again run the “tmux” command and this time, the error should not appear.
Another way is to use the “XTERM” terminal and launch the Tmux from here. This
worked on our Ubuntu 20.04 system.

How to Use Tmux

We can use three ways to send commands to a Tmux terminal:
Using the Prefix keys: Tmux uses a combination of keys called prefix keys,
which are by default “CTRL+b”. This prefix is followed by one or two more keys
which will be interpreted by Tmux for a particular operation. For example, we
can detach from a session by using: [Prefix+d].
Using the command mode: To send the commands directly to the Tmux terminal, we
must enter the command mode by pressing the prefix keys followed by a colon (:
). A command prompt will open up at the bottom of the terminal to enter the
Tmux commands.
Using the command line: Tmux commands can also be used from the non-Tmux
terminal or shell prompt. These commands are preceded by the “tmux” keyword. We
have illustrated this method in the following section.

Reloading a Tmux Config File

When we customize Tmux to suit our needs, we need to reload the config file.
Here, we explained three different ways to reload the Tmux config file:
1. Reloading the Tmux config file using the command: “tmux source-file”.
The command format to reload tmux.conf from shell prompt is:
tmux source-file <path to the tmux.conf file>
If the file is inside the home directory of the user (as it is usually the
case), the command will be:
$ tmux source-file ~/.tmux.conf
2. Reloading the Tmux config file using the Tmux command prompt.
We can also use the Tmux command prompt to initiate the reloading work. For
this, press “Prefix +:” and then, type the following command in the command
prompt:
source-file ~/.tmux.conf
This will load the config file from inside a running Tmux session.
3. Reloading the Tmux config file by making a prefix and key combination.
We need to modify the Tmux config file frequently, and many people find it too
cumbersome to type the “source-file” command repeatedly. Let us create a handy
shortcut for this. Open the tmux.conf file with any text editor like nano:
$ nano ~/.tmux.conf
and put the following line in it and reload Tmux config file:
bind r source-file ~/.tmux.conf
Next time you need to reload the config file, you only enter the prefix
followed by “r”.

Conclusion

In this guide, we have learned about the installation of Tmux, its basics, and,
more specifically, reloading the Tmux config file. A more detailed explanation
of various Tmux operations can be found on the Tmux Man pages or the GitHub
page of Tmux. We hope you found this article helpful. Check out the other Linux
Hint articles for more tips and information.


About the author


Ali Imran Nagori

Ali imran is a technical writer and Linux enthusiast who loves to write about
Linux system administration and related technologies. You can connect with him
on LinkedIn
.
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
