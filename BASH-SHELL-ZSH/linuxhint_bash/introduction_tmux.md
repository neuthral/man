





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Introduction to TMUX

3 years ago
by Usama_Azad
Every Linux terminal user wants to get rid of opening tabs for every different
task. For example, you’re upgrading your server over ssh in your terminal and
you need to do some other work on your server while doing it, its hectic to
open a new terminal and run another SSH connection, why not split the existing
SSH connection. For that purpose, there is a unix-based tool called tmux which
not only provides terminal splitting but also provides other useful features
and shortcut keys with it for the frequent users of terminal.


Benefits of using tmux

Tmux is short for Terminal Multiplexer which means it can manage more number of
terminals instead of only one. Not only terminal multiplexing, tmux also
manages and creates separate processes for front-end and background working of
the terminal sessions, which means we can detach the terminal interface without
stopping the background running service for it and then reattach to that
whenever needed. This is pretty much useful in time-consuming tasks. Not only
this, tmux also provides a vast list of shortcut keys that can be very useful
for frequent use of functionalities. Also, we can also add custom
configurations for many features of tmux at ~/.tmux.conf.

Installing tmux

To get started with tmux on linux, install tmux for debian distribution, if it
has not been installed already, using the following command:
$ sudo apt-get install tmux

Starting Tmux

To create a new session of tmux, simply type tmux, or type tmux new -
s <session_name>in the terminal.
This is how tmux interface looks like, which is almost the same as the
traditional terminal. At the bottom of the terminal, ‘first’ is the session
name that we provided and ‘0:bash’ is the window name with its associated
number. The name of the pane is renamed every time a task is started in that
window in accordance to that task. Also, note that there is an asterisk after
the window name of pane 0 which indicates the currently active window.

Prefix Key

Tmux gives a wide range of shortcut key and for that it uses something called
prefix key which means to enter shortcut key mode for tmux, every time we need
to hit prefix key first and then use shortcut key.
In tmux, by default this prefix is Ctrl + b, we can also change this prefix key
by updating configuration file. Let’s say we want ‘Ctrl + a’ to be our prefix
key instead of ‘Ctrl + b’. We will add the following lines to the tmux
configuration file at ~/.tmux.conf :
set -g prefix C-a
bind C-a send-prefix
unbind C-b

Creating New Tmux Windows:

Multiple windows are very useful in multitasking various tasks. These windows
can also be split into panes and shown in different ways. Firstly, to create a
new window, use:
<prefix> + c
Now there are two windows in the session ‘first’.

Renaming tmux Panes:

The windows of tmux can be easily renamed by the command:
<prefix> + ,
And then typing the new name for that window.

Window Switching:


Switching Using Window Numbers:

We can switch through windows using their serial numbers by simply hitting
prefix key and window number. For example, we are right now on window 1 and
want to switch to window 0, we will use the following to navigate to window 0:
<prefix> + 0

Cycle / Iterative Window Switching (Previous / Next):

We can also switch back and forth between windows by entering <prefix> + p for
previous window orderwise and <prefix> + n for next window.

Select From All Tabs:

<prefix> + wshows the list of windows open, for direct switching of windows by
selecting one.

Exiting Tmux Tabs

Like regular terminal, we can type exitcommand to completely quit and close
that tmux pane or window.

Tmux ls to view tmux sessions

To view all the active sessions of tmux, type tmux ls.

Nested Tmux Sessions:

The power of tmux is also creating and using nested tmux sessions i.e., we can
create a tmux session inside another tmux session. This in turn is useful when
remotely working on a machine from another machine and doing work on both
machines simultaneously. We can also change the prefix key for one machine so
that we can use tmux shortcut keys for both machines and work even more
swiftly.

Detach and Reattach sessions:

Detaching tmux session means allowing tmux run background tasks independently
of the tmux user interface of the terminal. This is also extremely useful for
tmux sessions on remote machines especially for long-running tasks. For
example, we need to update the software on a remote machine. We can easily ssh
to the remote machine and start downloading and installing its update. We can
then detach the tmux session and let the background update running in a process
on remote machine. We can now break that established ssh connected and the
remote will be updating on its own. We can also re-establish that same ssh
connection by reattaching that tmux session and continue working again. To
detach tmux session:
<prefix> + d

Splitting Terminal:


Vertical Split:

To create a new pane with vertical split, we can use:
<prefix> + %

Horizontal Split:

To create a new pane with horizontal split, we can use:
<prefix> + “

Adding Pane from Another Window:

Other than creating new split panes, we can also add panes from other windows
by using:
<prefix> + j
And then typing window number to import for split view.

Pane Switching Directive Shortcuts(Arrow keys):

To switch between panes, we can use prefix key and arrow keys to select the
pane to navigate to. For example, if we are to switch pane which in left of
current pane, we can use:
<prefix> + (left arrow key)
Also, the currently active pane is indicated by the green border around that
pane.

Resizing Panes:

We can also resize and adjust panes according to our way by hitting prefix key
but this time holding ‘Ctrl’ key and using the arrow keys to resize the current
pane in that direction.
<prefix> (hold Ctrl key) + (arrow key)

Zoom In / Out:

If we see that after splitting, the pane needs to be zoomed in, we can simply
zoom in to that pane only by using:
<prefix> + z
We can zoom out the pane that is currently zoomed in with the same command.

Swapping Pane Place:

We can also swap panes place, by commands:
<prefix> + {
Above command is for swapping current pane with the previous one.
<prefix> + }
This command is for swapping current pane with the next one.

Iterative Changing Positions of Tabs:

We can also change the positions of panes in an iterative way by pressing keys:
<prefix> + (space bar)

Timer

If there is a need of time displayed all the time, we can use a shortcut key to
display time at a pane, which is:
<prefix> + t

Send Pane:

One of the cool features of tmux includes sharing or sending pane to another
windows. We can send pane from one window to other windows of tmux by:
<prefix> + s
Also, the changes or commands typed on one pane of shared terminal are also
displayed on other pane in real-time.

Copy/Edit Mode

We can copy text from the tmux terminal using keyboard after entering edit or
copy mode by typing below command:
<prefix> + [
To start marking text to copy it, enter the command:
Ctrl + (space bar)
And to copy the marked text, enter the command:
Alt + w
Or
Ctrl + w
And finally to paste the copied text in another tmux pane or window, use:
<prefix> + ]

Conclusion:

This was all about tmux and its features. It’ll make your life a lot easier
after started using it and I hope that it will be useful and helpful for you a
lot.


About the author


Usama Azad

A security enthusiast who loves Terminal and Open Source. My area of expertise
is Python, Linux (Debian), Bash, Penetration testing, and Firewalls. I’m born
and raised in Wazirabad, Pakistan and currently doing Undergraduation from
National University of Science and Technology (NUST). On Twitter i go by
@UsamaAzad14
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
