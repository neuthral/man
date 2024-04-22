





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Scroll Up and Down in Tmux

11 months ago
by Ali_Imran_Nagori
Tmux is an open-source terminal multiplexer application for efficiently
managing multiple terminal windows. People, who have previously used the
Terminator application, are mostly familiar with the notion of tab management
in Linux Terminal. With Tmux, we can split the terminal into a number of panes.
We can adjust these panes by moving around, resizing, and switching between
them. This helps curb the pain of managing multiple windows and tabs of the
Gnome terminal.
After installing Tmux, you will not find any icon associated with it. It will
not appear as a separate application. Instead, we will have to invoke it from
the Gnome Terminal itself. We will later see how to do this.
In this guide we will explore how we can use Tmux. We will specifically see
“How to scroll up and down in the Tmux terminal.” In addition, we will use
Ubuntu 20.04 as the base system for this guide. Let us first start with
installing Tmux.

Installing Tmux on Ubuntu 20.04

Major operating systems like Linux, macOS, and Windows Subsystem for Linux
(WSL) provide Tmux software packages from their official repository. So, to
install Tmux on Ubuntu 20.04, we can simply use the package manager or software
center, as shown below:

  1. To install Tmux using package manager, simply run the following command:
     $ sudo apt install tmux
  2. To install Tmux using the software center, open the software center,
     search for Tmux, and click install.


Launching Tmux

Once the Tmux is installed, we will have to use the Gnome terminal to invoke
it. One may encounter the following error when you run the “Tmux” command:
“open terminal failed: missing or unsuitable terminal: xterm-256color”
To overcome this error, type “export TERM=xterm” on the terminal and hit enter.
Now, run the “Tmux” command again. This time, the error should not appear.
Another way is to use the “XTERM” terminal and launch the Tmux from here. This
worked on our Ubuntu 20.04 system.

Introducing Tmux

Every time we start Tmux, a new session is created on a single terminal window.
Information about the current session is shown at the bottom of the screen. As
stated earlier, Tmux does not appear as a separate application. In fact, we
have to launch it using another terminal application, such as the Gnome
terminal. Tmux has many benefits over the normal Gnome terminal. For example,
we can detach and attach Tmux from a screen. Once detached from a screen, it
can run in the background and reattach again.
Let us take an example of working on a remote machine to demonstrate the
capability of Tmux. Suppose we are connected to the remote machine using ssh
and trying to install system updates on the Tmux terminal. Due to some
technical glitch, we are disconnected. The Tmux window will automatically
detach itself and continue running in the background, and all the sessions and
running applications will be saved. Next time, when you reconnect to this
remote machine, you can easily reattach your old Tmux sessions.

Scrolling Up and Down in Tmux

When you first start using Tmux, you may find it difficult to work with basic
operations, such as scrolling the terminal, switching panes and windows,
splitting the windows, and adjusting pane size. Let us see how we can use the
scrolling feature in Tmux.
“Ctrl+b” is the most important keybinding for controlling Tmux operations. If
you want to scroll the Tmux terminal, enter the copy mode by pressing the
“Ctrl+b” combination and entering “[”. Now, you can use the navigation keys
like arrows (up and down) for moving line by line. Left and right arrows can be
used for character by character moving. Use the “page up” and “page down”
buttons for page scrolling.
One can also use the Key binding “Ctrl+b” and “Page Up”. This way, you will
enter the copy mode. To go to a specific line number, use “g” and enter the
line number starting from the bottom.

Using “tmux.conf”

Another way of setting the scrolling behavior is to use the “tmux.conf” file.
This file keeps the configuration settings persistent even after restarting
Tmux. This file simplifies the configuration of Tmux. If it is not created with
the installation process, create a new one yourself in your home directory.
This file contains a series of user-specific configuration and Tmux commands.
To create the file, run the following command:
$ cd ~ && touch .tmux.conf
Now, open this file, put the line “set -g mouse on” in this file, and save it.
Now reload Tmux config file.
This is a very efficient way to use your PC touchpad for scrolling. This also
worked in the case of our laptop touchpad.

Conclusion

In this guide, we have learned about the installation of Tmux, its basics, and,
more specifically, how to scroll inside a Tmux terminal. We hope ou found this
article helpful. A more detailed explanation of various Tmux operations can be
found on Linux Hint, Tmux Man pages or the Github page of Tmux.


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
