





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to swap panes in Tmux

11 months ago
by Ali_Imran_Nagori
Tmux is an open-source terminal multiplexer application for efficiently
managing multiple terminal windows. People who have previously used the
Terminator application are mostly familiar with the notion of tab management in
Linux Terminal. With Tmux, we can split the terminal into a number of panes. We
can adjust these panes by moving around, resizing, and switching between them.
This helps in curbing the pain of managing multiple windows and tabs of the
Gnome terminal.
In general, when you close an SSH connection, the corresponding remote terminal
sessions are also closed. Here comes the Tmux for help as it preserves those
sessions when the SSH connection is terminated.
After installing Tmux, you will not find any icon associated with it. It will
not appear as a separate application; instead, we will have to invoke it from
the Gnome Terminal itself. We will later see how to do this.
Note: In this ‘HowTo’, we have used the ‘Ctrl+b’ as the prefix; if you
configured some other prefix, then replace the command with yours’ prefix.

What will we cover?

This guide will explore how we can install Tmux and, more specifically, “How to
swap panes in Tmux”. We will use Ubuntu 20.04 as the base system for this
guide. Let us first start with installing Tmux.
Prerequisites
1. Tmux should be installed on your system.
2. Internet connectivity and user account with ‘sudo’ privileges.

Installing Tmux on Ubuntu 20.04

Major operating systems like Linux, MacOS, and Windows Subsystem for Linux
(WSL) provide Tmux software packages from their official repository. So to
install Tmux on Ubuntu 20.04, we can simply use the package manager or Software
center as described below:
1. To install Tmux using package manager, simply run the command:
$ sudo apt install tmux
2. To install Tmux using the software center, open the software center, search
for Tmux and click install.

Launching Tmux

Once the Tmux is installed, we will have to use the Gnome terminal to invoke
it. One may encounter the following error when trying to run the ‘tmux’
command:
“open terminal failed: missing or unsuitable terminal: xterm-256color”
To overcome this error, type “export TERM=xterm” on the terminal and hit enter.
Now again, run the ‘tmux’ command, and this time the error should not appear.
Another way is to use the ‘XTERM’ terminal and launch the Tmux from here. This
worked on our Ubuntu 20.04 system.

How to Use Tmux

We can use three ways to send commands to a Tmux terminal:
Using the Prefix keys: Tmux uses a combination of keys called prefix key, which
is by default ‘CTRL+b’. This prefix is followed by one or two more keys which
Tmux will interpret for a particular operation. For example, we can detach from
a session using [Prefix+d].
Using the command mode: To send the commands directly to the Tmux terminal, we
must enter the command mode by pressing the prefix keys followed by a colon (:
). A command prompt will open up at the bottom of the terminal to enter the
Tmux commands.
Using the command line: Tmux commands can also be used from the non-Tmux
terminal or shell prompt. These commands are preceded by the ‘tmux’ keyword. We
have illustrated this method in the below section.

Swapping Panes in Tmux

When we have multiple applications running on different panes in a Tmux
session, we sometimes need to arrange them according to some good sense. This
actually helps us to head our work in the proper direction, making it more
coherent. E.g., we open up a pane for a web server application, one for editing
a file (say tmux.conf), one for viewing the CPU and memory stats with the
‘top’command. The position of each pane is shown below:
I don’t like the above layout as it appears very awkward to me. Let us change
it sensibly: Edit the file in the top pane, manage the webserver from the
bottom right pane, and run the ‘Top’ command in the bottom left pane. Let us do
the swapping work now.
Tmux uses the keybinding ‘Prefix’ followed by ‘Ctrl+o’ to cycle around the
panes. When you use this key-binding for the first time, it moves the pane in
one position clockwise. We have to use this key-binding twice to arrive at our
desired layout:
If we need to move in an anticlockwise direction, use the ‘Alt+o’ combination
instead of ‘Ctrl+o’.
Now let us swap the position of the two bottom panes. For this, we can use the
key-binding ‘Prefix’ followed by ‘{‘ or ‘}’. The braces to use depend on the
direction you want to move towards.
To do the above pane management, we can also use the below command from the
Tmux command prompt:
swap-pane -D

swap-pane -U
The first command moves the pane in the clockwise direction and the below one
in the anticlockwise direction. If we use the ‘-d’ option, the pane focus does
not change with the pane rotation.

Conclusion

In this guide, we have learned about the installation of Tmux, its basics, and
more specifically, “How to swap panes in Tmux”. A more detailed explanation of
various Tmux operations can be found on the Tmux Man pages or on the Github
page of Tmux.


About the author


Ali Imran Nagori

Ali imran is a technical writer and Linux enthusiast who loves to write about
Linux system administration and related technologies. You can connect with him
on LinkedIn
.
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
