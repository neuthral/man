





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Kill all Tmux Sessions

11 months ago
by Ali_Imran_Nagori
Tmux is an open-source terminal multiplexer application for efficiently
managing multiple terminal windows. People who have previously used the
Terminator application are mostly familiar with the notion of tab management in
Linux Terminal. With Tmux, we can split the terminal into a number of panes. We
can adjust these panes by moving around, resizing and switching between them.
This helps in curbing the pain of managing multiple windows and tabs of Gnome
terminal.
In general, when you close a SSH connection, the corresponding remote terminal
sessions are also closed. Here comes the Tmux for help as it preserves those
sessions when the SSH connection is terminated.
After installing Tmux, you will not find any icon associated with it. It will
not appear as a separate application, instead we will have to invoke it from
the Gnome Terminal itself. We will later see how to do this.
Note: In this ‘HowTo’ we have used the ‘Ctrl+b’ as the prefix, if you
configured some other prefix then replace the command with your prefix.

What will we cover?

In this guide, we are going to see how we can install Tmux and more
specifically “How to kill all Tmux sessions”. We will use Ubuntu 20.04 as the
base system for this guide. Let us first start with the installation of Tmux.
Prerequisites
1. Tmux should be installed on your system.
2. Internet connectivity and user account with ‘sudo’ privileges.

Installing Tmux on Ubuntu 20.04

Major operating systems like Linux, MacOS and Windows Subsystem for Linux (WSL)
provide Tmux software packages from their official repository. To install Tmux
on Ubuntu 20.04, we can simply use the package manager or Software center as
described below:
1. To install Tmux using package manager, simply run the command:
$ sudo apt install tmux
2. To install Tmux using Software center, open software center and search for
Tmux and click install.

Launching Tmux

Once the Tmux is installed, we will have to use the Gnome terminal to invoke
it. One may encounter the following error when trying to run the ‘tmux’
command:
“open terminal failed: missing or unsuitable terminal: xterm-256color”
To overcome this error, type “export TERM=xterm” on the terminal and hit enter.
Now again run the ‘tmux’ command and this time the error should not appear.
Another way is to use the ‘XTERM’ terminal and launch the Tmux from here. This
worked on our Ubuntu 20.04 system.

How to Use Tmux

We can use three ways to send commands to a Tmux terminal.
Using the Prefix keys: Tmux uses a combination of keys called prefix key, which
is by default ‘CTRL+b’. This prefix is followed by one or two more keys which
will be interpreted by Tmux for a particular operation. For example, we can
detach from a session by using: [Prefix+d].
Using the command mode: To send the commands directly to the Tmux terminal, we
need to enter the command mode by pressing the prefix keys followed by colon (:
). A command prompt will open up at the bottom of the terminal where we can
enter the Tmux commands.
Using the command line: Tmux commands can also be used from the non-Tmux
terminal or shell prompt. These commands are preceded by the ‘tmux’ keyword. We
have illustrated this method in the below section.

Killing Individual Session in Tmux

In the simplest way, we can type‘exit’ or enter ‘Ctrl+d’ to destroy a Tmux
session. The‘kill-session’ command can also be used to destroy a session:
$ tmux kill-session -t sess_1
When we run the ‘tmux ls’ command, the following message will appear if there
is no running session:
“no server running on /tmp/tmux-1000/default”

Killing All Session

We can also kill all running sessions simultaneously. Running the below command
will kill all the sessions including the one from which we execute it:
$ tmux kill-server

Excluding a Session from Termination

In case you want to keep the session you are in and kill all the other
sessions, run the command:
$ tmux kill-session -a
Let us kill ‘sess_1’and‘sess_2’from‘sess_3’ and list the running session again:
This will kill all the sessions excluding the current session from which we are
running the ‘kill’ command. In our case, ‘sess_3’ is running and others are
terminated.

Killing a Specific Session

We can also choose a session to kill, for this run the below command to
identify the target session:
$ tmux list-sessions
or simply use:
$ tmux ls
Now, use the command ‘tmux kill-session -t sessionIDorName’ to kill a specific
session. For example, we want to kill the session ‘sess_3’, in this case this
command will be:
$ tmux kill-session -t sess_3

Killing the Tmux Process

Using this method, we can terminate the entire Tmux process tree. Open the
System Monitor application and search for ‘tmux’ inside the process tab. This
will list all the Tmux running processes. In our case, we have three Tmux
sessions. There are three client processes and one server process running as
shown below:
Now, run the below command to terminate all sessions:
$ pkill -f tmux
All the tmux processes (clients and server) are terminated as shown below:

Conclusion

In this guide, we have learned about the installation of Tmux, its basics and
more specifically, “How to kill all tmux sessions”. A more detailed explanation
of various Tmux operations can be found on the Tmux Man pages or on the Github
page of Tmux.


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
