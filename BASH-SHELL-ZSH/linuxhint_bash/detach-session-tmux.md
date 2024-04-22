





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to detach a session in tmux

11 months ago
by Ali_Imran_Nagori
Tmux is an open-source terminal multiplexer application for efficiently
managing multiple terminal windows. People who have previously used the
Terminator application are mostly familiar with the notion of tab management in
Linux Terminal. With Tmux, we can split the terminal into a number of panes. We
can adjust these panes by moving around, resizing, and switching between them.
This helps in curbing the pain of managing multiple windows and tabs of the
Gnome terminal.
After installing Tmux, you will not find any icon associated with it. It will
not appear as a separate application; instead, we will have to invoke it from
the Gnome Terminal itself. We will later see how to do this.
Note: In this ‘HowTo’ we have used the ‘Ctrl+b’ as the prefix; if you
configured some other prefix, then replace the command with yours’ prefix.

What will we cover?

This guide will explore how to install Tmux and, more specifically, “How to
detach a session in the tmux terminal”. We will use Ubuntu 20.04 as the base
system for this guide. Let us first start with installing Tmux.

Installing Tmux on Ubuntu20.04

Major operating systems like Linux, macOS, and Windows Subsystem for Linux
(WSL) provide Tmux software packages from their official repository. So to
install Tmux on Ubuntu 20.04, we can simply use the package manager or Software
center as shown below:
1. To install Tmux using package manager, simply run the command:
$ sudo apt install tmux
2. To install Tmux using the software center, open the software center, search
for Tmux and click install.

Launching Tmux

Once the Tmux is installed, we will have to use the Gnome terminal to invoke
it. One may encounter the following error when you run the ‘tmux’ command:
“open terminal failed: missing or unsuitable terminal: xterm-256color”
To overcome this error, type “export TERM=xterm” on the terminal and hit enter.
Now again, run the ‘tmux’ command; the error should not appear this time.
Another way is to use the ‘XTERM’ terminal and launch the tmux from here. This
worked on our Ubuntu 20.04 system.

Detaching a session in tmux

Every time we start Tmux, a new session is created on a single terminal window.
Information about the current session is shown at the bottom of the screen.
Tmux does not appear as a separate application; we have to launch it using
another terminal application like Gnome terminal. Tmux has many benefits over
the normal Gnome terminal. For example, we can detach and attach a tmux session
from a screen. Once detached from a screen, it can run in the background and
can be re-attached again.
Detaching a session is a great feature of Tmux. Later you can ssh to the
machine (if it is a remote one) and re-attach to it. All the processes will
still be running, and in the meanwhile, you can focus on other work. Let’s do
it now.
1. Detaching from a session using the shortcut key: ‘Ctrl–b–d’
We will start by starting a session with the name ‘my_session _1’:
$ tmux new -s my_session_1
Now we will detach it with ‘Ctrl+b’(it is the tmux prefix in our case) followed
by ‘d’. Use the ‘ls’ command to check the list of all sessions:
$ tmux ls
After pressing the keys, we can see that the session ‘my_session_1’ is now
detached.
2. Detaching from a session using the command: ‘tmux detach’
Let us create another session with the name ‘my_session _2’:
$ tmux new -s my_session_2
Now we will detach it with the command ‘tmux detach’.
$ tmux detach
Now again, verify the list of all sessions:
$ tmux ls
The session ‘my_session_2’ is also detached now.
3. Selecting a session to detach using the shortcut key: ‘ctrl–b–D’
If we have many sessions running, we can select a specific session to detach.
Let’s see this. First, create three sessions using the commands:
$ tmux new -s my_session_1

$ tmux new -s my_session_2

$ tmux new -s my_session_3
Use the ‘tmux ls’ command to view all the sessions:
Now we will use the combination ‘Prefix+D’ and see what happens:
As we can see now, it asks to select the session we want to detach. Use the
arrows to select the session and hit enter to detach it. Suppose we detach the
session ‘my_session_3’, now again run the ‘tmux ls’ command to see the changes:
We can clearly notice that the ‘attached’ label has disappeared from the
session‘my_session_3’.
4. Detaching from a session using the command: ‘tmux detach-client’
We can also go with the command: tmux detach-client. Let us experiment with
this with the session ‘my_session_2’. Run the command:
$ tmux detach-client -P -s my_session_2
Let’s see the changes:
$ tmux ls
As you can see in the image above, ‘my_session_2’ has also detached now and
disappeared from the scene.

Conclusion

In this guide, we have learned about the installation of Tmux, its basics, and
more specifically, how to detach a session in tmux. A more detailed explanation
of various Tmux operations can be found on the Tmux Man pages or the Github
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
