





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to make BASH suit you better

3 years ago
by Mats_Tage_Axelsson
BASH has a simple standard setup which is great but you may want more! Many
computer users avoid the command line, because it is hard to use. This is a
misconception. The command line has a learning curve, it requires some
knowledge to get started. However, ones you know a few things, it is faster and
often easier. After learning a few basic commands, the absolutely essential
skill is to read documentation. This may not sound like a skill but it is. The
reason is that the documents are generic, they will not answer your specific
question, you have to derive the answer from the information you have. When you
start your environment, the system has files controlling what your defaults
will be in many applications will be set. For bash, you have several files that
control this. These file in a sequence and only if others do not exist.


What can you change?

Loads of stuff, but the changes you will notice first are the ones setting your
prompt. You also have aliases and environment variables. Many of these are set
to make sure you use the correct libraries and executable files when running
applications. The files also control and add features to the shell, an example
is history. In bash you have a history file that contains the last commands you
have entered. You can choose if you want history to keep duplicates and how
large the file becomes. There are many more things you can run. A nice example
of utilities are available from bash-it.

Where is it stored?

This seems like a simple list of a few files that are run when you start.
However, due to the way bash starts, there are a few complications. One is that
you want some settings for the system and some for each time you open a shell.
The file /etc/profile runs during login, note that it often calls /etc/
profile.d/* to set specific values. On Ubuntu, it sets the snap paths, both for
where binaries are and where xdg calls applications. This file is system-wide,
so don’t use it for personal settings. For system-wide files you also have etc/
bash.bashrc, this file is named /etc/bashrc outside of debian based
distributions. The administrator sets, hopefully sane, defaults for all users
on the system. If you do not agree with those settings, you can override them
in ~.bashrc, for the special user.
I know you may be both user and administrator! The next file you need to
consider is ~/.profile, this runs at login, not when the shell starts. It also
only starts if .bashprofile or .bashlogin does not exist. The standard version
checks what shell will be run. When the .profile file runs, it starts ~/.bashrc
if it exists. The ~/.bashrc file is where you should set your aliases and other
personal settings. Two other files are interesting, ~/.bashlogout and
~/.inputrc, the former runs at logout. It clears the console, by default. More
interesting is the inputrc file. Here you change key bindings and key strokes.
You can set how you edit on the command line. Default is emacs style editing
but you can change that to vi style.

Some examples of changes to make.

Update your prompt… To make your prompt look prettier or to convey more
information, you can change the values of PS1. First, you can check what value
you have already.
$ echo $PS1
The result looks a little cryptic unless you have set it to a string. Try it:
$ PS1 = "Cool Prompt!"
This is not very useful, you can instead set values that inform you about what
is happening in your system. Here is a short table of some values:

\u Current username
\h Current hostname
\w Current working directory
\s Name of the shell
\t Time in 24-hour format

As a challenge, set your prompt to have your username and hostname, correctly
marked with the ampersand. You can also use system defined variables and even
the output of scripts. Set a colour scheme… You can have your output in colour,
and also have different colours for each type of files. First, create a
colourful prompt. The colour can change throughout the prompt. To start a new
colour, add ‘\e[x,ym’ och stoppa med ‘\e[m. Here is an example.
$ PS1="\e[0;35m \[email protected]\h \e[m \e[0;32m \d \A\e[m \$ >"
umask, how it works… In the shell you have a setting called ‘umask’, it sets
how files permissions are set when you create them. The most common value is
022. This makes files have permissions that allow users to read and write and
all others to read only. This way, you must change new script files to
executable as a separate action. This is a safe way to handle files.
function definitions… You can also incorporate functions, the format of these
can be POSIX compliant or bash. If you plan to switch between shells, look up
how to stay compliant. You can also run a script in the prompt.
#!/bin/bash
# lsbytesum - the number of bytes in a directory listing
TotalBytes=0
for Bytes in $(ls -l | grep "^-" | awk '{ print $5 }')
do
TotalBytes=$TotalBytes+$Bytes
done
TotalMeg=$(echo -e "\n$TotalBytes/1048576 \nquit" | bc)
echo -n "$TotalMeg"
If you have the code above (credit to TLDP), you can call it in your prompt
(PS1). To set it add this to your bashrc.
$ PS1="[\[email protected]\h:\w (\$(lsbytes) Mb)]\$ "
You can, of course run it manually to see if you like it first. There are no
colours in this style, you must combine many different settings.
Once you have decided what you want, you need to put the values in your .bashrc
file.

Conclusion

Bash has many features which you can use to make your environment run better.
You can make many jobs faster if you have learned how to be efficient. One way
is to create aliases, another is to create your own scripts. It can be very
beneficial to your efficiency, if you take the time to climb past the initial
barrier.


About the author


Mats Tage Axelsson

I am a freelance writer for Linux magazines. I enjoy finding out what is
possible under Linux and how we can all chip in to improve it. I also cover
renewable energy and the new way the grid operates. You can find more of my
writing on my blog.
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
