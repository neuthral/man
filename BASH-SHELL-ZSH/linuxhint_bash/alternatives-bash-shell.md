





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Alternatives to Bash Shell

1 year ago
by Nitesh_Kumar
This article will cover a guide on alternative shell applications that can be
used instead of the default bash shell available in most Linux based operating
systems. Bash or “GNU Bourne Again Shell” is a command interpreter that can be
used to run different types of commands and execute binaries from user input or
from files. Some alternative shell applications with similar feature sets plus
some extras are available that you can use to improve command input and output
experience.

Making Alternative Shells Defaults and Running Scripts Using Them

Some alternative shell applications are listed below. To use them properly on
your Linux distribution, you will have to add their path as a hash-bang string
on top of a script file. You can know more about binary location of a shell by
running the command below:
$ which zsh
You can replace the “zsh” command with any other shell of your choice. After
running the above command, you should get some output similar to this:
/usr/bin/zsh
Add the above path as hash-bang on top of a script file, as shown in the code
sample below:
#! /usr/bin/zsh
echo $ZSH_VERSION
Now when you run a script with hash-bang added for Zsh, you will run it using
the “zsh” binary instead of the default shell available on your system.
To make a shell default on your system, run a command in the following format:
$ chsh -s $(which <shell_binary_name>)
For instance, if you want to make Zsh default, use the following command:
$ chsh -s $(which zsh)
To check your default shell type, run the command below:
$ ps -p $$
You will get some output similar to this:
PID TTY          TIME CMD
4380 pts/0    00:00:00 bash
To revert to Bash or any other shell, run the following command:
$ chsh -s $(which bash)
Note that after changing shells, you will need to re-login for the changes to
take effect.

Zsh

Zsh is a free and open source command interpreter that can replace Bash shell.
It is one of the most comprehensive alternative shells available today, with a
number of useful features not seen in other shells. This makes it a little bit
bloated than other shells, however, it also provides a large number of extra
functions. Main features of Zsh include compatibility with Korn shell, powerful
and customizable globbing interface, autocompletion tweaks, expandable
variables, menu completion, editable text output, ability to run commands
spanning multiple lines, advanced path expansion, built-in spell checker,
ability to perform recursive searches, conditional statements and expressions,
advanced array functions, functions to perform mathematical calculations,
objects with key-value pairs, and so on.
You can install Zsh in Ubuntu using the command below:
$ sudo apt install zsh
You can install Zsh in other Linux distributions from the package manager. More
packages and installation instructions are available here.

Ksh

Ksh or Korn Shell is a free and open source alternative to the Bash shell. In
development for nearly three decades, Ksh provides a number of extra functions
in comparison to the Bash shell. Its main features include full compatibility
with the Bash shell, improved performance than Bash shell, enhanced command
history, ability to fire co-processes, inline editing of commands and the
output, ability to route output to menu, ability to process strings as is
without escaping, mathematical functions, Python dictionary like objects,
ability to compile Ksh scripts into executable binaries, named references, and
so on.
You can install Ksh in Ubuntu using the command below:
$ sudo apt install ksh
You can install Ksh in other Linux distributions from the package manager. More
packages and installation instructions are available here.

Fish

Fish shell is yet another free and open source alternative shell for the Bash
shell. It is mainly focused on ease of use and interactivity, and aims to make
things much simpler than other shells. Other main features of Fish include
customizable colored output, advanced auto completion based on your command
usage history, ability to change shell configuration from a web browser,
improved syntax highlighter, ability to fetch commands from man pages to
facilitate auto completion, supports custom user scripts, list navigation, and
so on.
You can install Fish in Ubuntu using the command below:
$ sudo apt install fish
You can install Fish in other Linux distributions from the package manager.
More packages and installation instructions are available here.

Dash

Dash is a free and open source command interpreter shell. It can be used as an
alternative to the Bash shell and it is lighter on resources than Bash as it
consumes less memory and disk space. Also known as “Debian Almquist Shell”, it
is used as the default shell on many Debian based Linux distributions. It
incorporates some features of Ksh, but not all. Dash also has better POSIX
compatibility than Bash shell. Dash can also run commands and scripts much
faster than Bash shell. Other than these differences, Dash and Bash shells are
mostly the same.
You can install Dash in Ubuntu using the command below:
$ sudo apt install dash
You can install Dash in other Linux distributions from the package manager.
More packages and source code archives are available here.

Xonsh

Xonsh is a Python based alternative shell application available for Linux. It
includes numerous modules and packages from the official Python3 library
allowing you to run Python commands in terminal directly. With the full Python
library exposed, you can write advanced shell scripts using proper Python code.
It also supports all Bash built-ins and functions so you can use both Bash and
Python syntax in your scripts. Other main features of Xonsh include advanced
command history, customizable colors, customizable auto completion behavior,
custom keybindings, official and third party addons, custom prompt, and so on.
You can install Xonsh in Ubuntu using the command below:
$ sudo apt install xonsh
You can install Xonsh in other Linux distributions from the package manager.
More packages and installation instructions are available here.

Nushell

Nushell is a relatively newer alternative shell that can be used as a
replacement for the Bash shell. Written in Rust programming language, Nushell
can present output and other text in tabular form, making them more readable.
You can run commands on tabular data, and sort and filter its content, just
like you would do in a spreadsheet software. Other main features of Nushell
include advanced pipelines where you can feed and route output to another
command in a more intuitive way than Bash shell, ability to present content of
text and other parsable files in tabular data, custom command built-ins, and so
on.
You can download executable binaries for Nushell from here. Once downloaded,
extract the archive and copy all files to “/usr/local/bin/” path with root
access to complete the installation.

Conclusion

These are some of the most useful alternative shells that you can use to
completely replace the default Bash shell available in most Linux
distributions. These alternative shells provide many extra features over the
Bash shell and in many cases improved performance as well. They are especially
useful for power users who regularly use commands and scripts or for those who
use headless Linux distributions.


About the author


Nitesh Kumar

I am a freelancer software developer and content writer who loves Linux, open
source software and the free software community.
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
