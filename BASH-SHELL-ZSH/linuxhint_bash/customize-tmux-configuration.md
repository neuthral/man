





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to customize the tmux configuration?

10 months ago
by Ali_Imran_Nagori
Tmux is an open-source terminal multiplexer application for efficiently
managing multiple terminal windows. People who have previously used the
Terminator application are primarily familiar with the notion of tab management
in Linux Terminal. With Tmux, we can split the terminal into a number of panes.
We can adjust these panes by moving around, resizing, and switching between
them. This helps in curbing the pain of managing multiple windows and tabs of
the Gnome terminal.
In general, when you close an SSH connection, the corresponding remote terminal
sessions are also closed. Here comes the Tmux for help as it preserves those
sessions when the SSH connection is terminated.
After installing Tmux, you will not find any icon associated with it. It will
not appear as a separate application; instead, we will have to invoke it from
the Gnome Terminal itself. We will later see how to do this.
Note: In this ‘HowTo’ we have used the ‘Ctrl+b’ as the prefix; if you
configured some other prefix, then replace the command with yours’ prefix.

What will we cover?

This guide will learn about “How to customize tmux configuration?”. We will use
Ubuntu 20.04 as the base system for this guide.
Prerequisites
1. Tmux should be installed on your system.
2. Internet connectivity and user account with ‘sudo’ privileges.

Using tmux.conf for Customization of Tmux

To customize the tmux configuration, we need to tweak its default configuration
file: tmux.conf. This file is invoked by Tmux at startup. Tmux first looks for
the system configuration file inside the directory ‘/etc/tmux.conf’, if it is
absent, it then searches inside the home directory of the user. The file
contains a list of Tmux commands which are executed sequentially. These
commands are executed at the very first start of the tmux server.
Note:Before going to customize the tmux.conf, beware that you do not spoil up
the configuration by mixing multiple shortcuts. In order to avoid such
ambiguity, you should view all the occupied shortcuts of Tmux by entering the
below command inside a Tmux session:
‘Prefix’ + ?

1. Changing the default ‘Ctrl+b’or ‘C-b’ prefix to ‘Alt+b’or‘M-b.’

The prefix key (‘Ctrl+b’) along with a command key controls various operations
of Tmux. It is the default combination which most users will tend to change for
handiness. But changing this key requires some wit so that we may not mess up
with other shortcuts of the default terminal we are working on.
Let us change this prefix to ‘Alt+b.’ Open the tmux.conf file. If it is in your
home directory, use the command:
$ sudo nano ~/.tmux.conf
Put the below lines in this file and save it.
# changing prefix from 'Ctrl+b' to 'Alt+b'

unbind C-b

set-option -g prefix M-b

bind-key M-b send-prefix
If you are inside a Tmux session, exit the current session and start over a new
Tmux session. You can also reload the tmux config file to make the changes
work.

2. Setting both the ‘Ctrl+b’ and‘C-b’ as prefixes.

We can also set two prefixes; for example, the below tmux commands will set
both the ‘Alt+b’ and ‘Ctrl+b’as prefixes. Open the tmux.conf file and enter:
# Setting two prefix: 'Ctrl+b' to 'Alt+b'

set-option -g prefix M-b

set-option -g prefix2 C-b
Now reload the ‘tmux.conf’file.

3. Using the Mouse mode.

We can use the ‘tmux.conf’ file to set the scrolling behavior of the mouse.
Open the file and put the following line:
set -g mouse on
Now reload tmux.conf using the command:
$ tmux source-file ~/.tmux.conf
Once the above tasks are done, we can use the touchpad or PC mouse to scroll
our Tmux terminal.

4. Adding shortcut for tmux config reload

Many times we customize tmux frequently to suit our needs; as a result, we need
to reload the config file very often. The command to reload tmux.conf when it
is running is:
$ tmux source-file <path to the tmux.conf file>
Let us create a handy shortcut for this. Open the tmux.conf file and put the
following line in it:
bind r source-file ~/.tmux.conf
Next time you need to reload the config file, you only have to enter the prefix
followed by‘r.’

5. Simplifying the Split commands

The Tmux default shortcut for splitting the terminal is very awkward. Let’s
change it into something more convenient. E.g., we will be mapping the
horizontal split to ‘-’ from ‘ “ ‘ and the vertical split from ‘%’ to ‘|.’
Open the tmux.conf file and add the below lines:
# Splitting terminals using | and -

unbind '"'

unbind %

bind - split-window -h

bind | split-window -v

6. Managing copy-paste operation between System clipboard and Tmux clipboard

It is straightforward to copy the contents from the System clipboard and paste
it to a Tmux session using the regular key combination ‘Ctrl+Shift+v.’ However,
the reverse procedure is not that straightforward. We can simplify this by
installing a utility called ‘xclip’ and customizing the ‘tmux.conf’ file.
Follow the steps given below:
Step 1. First, install ‘xclip’ on Ubuntu 20.04 using the command:
$ sudo apt install xclip
We have already installed it:
Step 2. We will now customizetmux.conf by adding the below line:
bind C-c run "tmux save-buffer - | xclip -i -sel clipboard"

bind C-v run "tmux set-buffer "$(xclip -o -sel clipboard)"; tmux paste-buffer"
The first line makes the ‘prefix’ followed by ‘Ctrl+c’to capture the current
Tmux buffer and feeds this output to ‘xclip.’ Now, we can paste the copied text
from the Tmux clipboard using the system clipboard:
The second line configures the ‘prefix’ followed by ‘Ctrl+v’ to paste text from
the system clipboard to a Tmux session, but as stated earlier, it is
straightforward to copy and paste from the system clipboard to Tmux session
(Using Ctrl+Shift+v). So you may not need the second line. If this does not
work, then you must add the second line.
Tips:We can also define a keybinding that will not need a prefix. E.g., to
reload the configuration file using ‘Ctrl+r’ only, use the bind command as
shown here:
bind-key -n C-r source-file ~/.tmux.conf
But this will disable this particular key combination in other applications
running in a Tmux session, so use it carefully.

Conclusion

In this guide, we have learned many ways of customizing Tmux configuration
using tmux.conf. There are still many ways to change the look and feel of a
Tmux environment. A more detailed explanation of various Tmux operations can be
found on the Tmux Man pages or on the Github page of Tmux.


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
