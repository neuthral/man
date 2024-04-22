





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to use Tmux mouse mode?

10 months ago
by Ali_Imran_Nagori
Tmux is an open-source terminal multiplexer application for efficiently
managing multiple terminal windows. People who have previously used the
Terminator application are mostly familiar with the notion of tab management in
Linux Terminal. With Tmux, we can split the terminal into several panes. We can
adjust these panes by moving around, resizing and switching between them. This
helps in curbing the pain of managing multiple windows and tabs of the Gnome
terminal.
In general, when you close an SSH connection, the corresponding remote terminal
sessions are also closed. Here comes the Tmux for help as it preserves those
sessions when the SSH connection is terminated.
After installing Tmux, you will not find any icon associated with it. It will
not appear as a separate application; instead, we will have to invoke it from
the Gnome Terminal itself. We will later see how to do this.
Note: In this ‘HowTo’ we have used the ‘Ctrl+b’ as the prefix; if you
configured some other prefix, then replace the command with yours’ prefix.

What will we cover?

This guide will explore how we can install Tmux and, more specifically, “How to
use Tmux mouse mode”. We will use Ubuntu 20.04 as the base system for this
guide. Let us first start with installing Tmux.
Prerequisites
1. Tmux should be installed on your system.
2. Internet connectivity and user account with ‘sudo’ privileges.

Installing Tmux on Ubuntu 20.04

Major operating systems like Linux, MacOS and Windows Subsystem for Linux (WSL)
provide Tmux software packages from their official repository. So to install
Tmux on Ubuntu 20.04, we can simply use the package manager or Software center
as described below:
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
need to enter the command mode by pressing the prefix keys followed by a colon
(:). A command prompt will open up at the bottom of the terminal, where we can
enter the Tmux commands.
Using the command line: Tmux commands can also be used from the non-Tmux
terminal or shell prompt. These commands are preceded by the ‘tmux’ keyword. We
have illustrated this method in the below section.

Using Mouse Mode For Tmux >= 2.1

When we start using Tmux (of course, as a novice), we feel how nice it would be
to scroll or select Tmux windows with a mouse. Surely, we can do that in Tmux
by customizing the tmux.conf file. This is where Tmux mouse mode comes into
play. Let see the mouse mode in action:

Enabling the mouse mode

We need to first enable the mouse mode. Open the tmux.conf file and put the
following line inside it:
setw -g mouse on
Now reload the ‘tmux.conf’ file:
$ tmux source-file ~/.tmux.conf
Note:Every time we make changes to tmux.conf file, source, or reload the
tmux.conf file to make the changes work.
After reloading the tmux.conf file, we can control the pane selection, pane
resizing and window selection operation with the Mouse itself.

Using Tmux Mouse Mode For Tmux < 2.1

In Tmux version < 2.1 we can put the following lines to make the mouse manage
the pane selection, pane resizing and window selection:
setw -g mode-mouse on

set -g mouse-select-pane on

set -g mouse-resize-pane on

set -g mouse-select-window on
If you want to make yourself comfortable with the keybindings of Tmux
operations, we suggest you disable the mouse options by simply setting the
above option to ‘off’ or directly disabling the mouse mode by:
setw -g mode-mouse off
In this way, we can also avoid doing wrong things while selecting Tmux’s
windows/panes with a mouse.

Mouse action in Tmux

We can also select a word and a line in Tmux. E.g. to select a word, hold the
right button and double click the left button. Similarly, hold the right button
and triple click the left button to select a line. You can now also use the
arrow keys to select multiple lines.

Conclusion

In this guide, we have learned about the installation of Tmux, its basics and
more specifically, “How to use Tmux mouse mode”. Although we can use Tmux mouse
mode, it is generally a good practice to use Keyboard. This is because as the
number of applications increases, it becomes very distractive to use a mouse
for switching between panes and windows running different applications. A more
detailed explanation of various Tmux operations can be found on the Tmux Man
pages or on the Github page of Tmux.


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
