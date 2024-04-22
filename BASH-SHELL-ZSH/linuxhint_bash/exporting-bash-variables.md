





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Exporting Bash Variables

2 years ago
by Frank_Hofmann
Understanding variables in the Bash shell is essential in working with Linux in
a professional manner. It is one of the key requirements for programming as
well as achieving the Linux Professional Institute Certification (LPIC) Level 1
[2].
The previously_published_article_by_Fahmida_Yesmin [4] gives you a wonderful
introduction into Bash variables. Here we step further, and explain how to
declare variables in Bash in such a way that you can use them in other
environments on your Linux system, and which corresponding side effects you
have to take into account.

A brief description of Bash

The Bash shell was first released in 1989 and has been used as the default
login shell for most Linux distributions. Brian Fox wrote Bash as a UNIX shell
and command language for the GNU Project as a free software replacement for the
Bourne shell. It is an acronym for Bourne Again Shell. Bash is largely
compatible with sh and incorporates useful features from the Korn shell ksh and
the C shell csh [6].
While the GNU operating system provides other shells, including a version of
csh, Bash is the default interactive shell. It is designed with portability in
mind, and currently runs on nearly every version of UNIX plus other operating
systems [9].

Bash variables in a nutshell

Variables are essential components of programming languages. They are
referenced and manipulated in a computer program. Simply put, variables
represent named memory cells. This is the same in Bash as in any programming
language. This makes it possible for us as humans and users of the computer to
store values in the “brain” of the computer and find them again via the
assigned name of the variable.
The term variable refers to a combined form of two words, i.e., vary + able,
which means its value can be changed, and it can be used for multiple times. In
contrast to this, variables that cannot be changed are called constants. [10]
As long as there is enough memory available for your script you can freely
create and use variables. You can simply set them by defining a variable name
and then assigning its value. A variable name in Bash can include letters,
digits, and underscores. Its name can be started with a letter and an
underscore, only. Valid variable names are size, tax5, and _tax20 but not
5rules.
A variable value in Bash can contain a number, a single character, a string of
characters, or a list of items (called array). It does not have a visible data
type, and the internal data type of the variable will be automatically figured
out (or derived) upon assignment of a value. Furthermore, there is no need to
declare the variable — assigning a value to its reference will create the
variable automatically. The example Bash script below demonstrates this for a
string assignment, and a numeric number assignment.
#! /bin/bash


welcomeMessage="Hello World!"

echo $welcomeMessage


price=145

echo $price

Naming Conventions Of Bash Variables

There are no fixed rules for the spelling of names of variables, only
conventions. These conventions are used:

* Lowercase names — variables that are local to a script or function.
  No matter whether spelt lower_case/snake case [8], or camel case style [7].
  The example above uses camel case style.
* Uppercase names — constants, environment variables, shell built-in variables.
  Keep in mind that these variables might already be in use by other programs.
  Examples are $PATH, $LANG, $PWD, $PS4, and $SHELL.

For global IT companies it is common to work with style guides to ensure a
common coding style among the company. See the Developer Editorial for IBM, and
the Google Style Guide [3] for more information about the conventions they
follow.

Variable Visibility

The default case is that a variable is locally bound to a structure, function,
script, or process, and cannot be accessed from outside of it. The example
below shows this for the variable $message that belongs to the script, and
$welcome that belongs to the function outputWelcomeMessage().
#!/bin/bash


# define a variable message to the script

message=”Hello, again!”


outputWelcomeMessage () {

    # define a local variable

    welcome=”Hello!”

    echo $welcome

}


outputWelcomeMessage ()    # prints Hello!

echo $message              # prints Hello, again!
To make sure a previously defined variable with the same name is locally bound
use the keyword local as demonstrated next. Without the keyword local the
assignment in line 8 would relate to the globally defined variable with the
same name defined earlier.
#!/bin/bash


# define a variable message to the script

message=”Hello, again!”


outputWelcomeMessage () {

    # define a local variable with the same name

    Local message=”Hello!”

    echo $message

}


outputWelcomeMessage ()    # prints Hello!

echo $message              # prints Hello, again!

Extending the scope of a variable

In order to make an internal variable visible to other child processes an
additional step is needed. This step is called exporting a variable. Bash
offers the usage of the keyword export followed by the variable name. The
listing below demonstrates this for the variable backupPath.
$ backupPath=”/opt/backup/”

$ export backupPath
The export command is a shell built-in that is used to define the variable as
one that subshells (shells spawned from the original) inherit. Variables that
are exported can be read and written by more than one process, then.
The second option is to declare the variable as an environment variable right
from the start. You can do that by using the keyword declare followed by the
option “-x” (see [5] for more info about the declare command). The effect is
similar to the export command that was introduced before.
$ declare -x BACKUPPATH=”/opt/backup/”

Inherit from other sessions

When you execute a program it automatically inherits its environment variables
from the parent process. For instance if $HOME is set to /root in the parent
then the child’s $HOME variable is also set to /root.

Further Commands

Among others, Linux comes with useful commands and options that relate to
variables. The first two ones are called env and printenv. They list all the
environment variables.
The image below shows the output of the command env in a terminal that is run
in an X session. It contains variables like $XTERM (terminal type), $SHELL (the
program that is called upon login, and shows /bin/bash for the path to the Bash
interpreter), $LS_COLORS (the colours that are in use to highlight different
file types when calling ls), and $DESKTOP_SESSION (the current X Desktop
Environment).
The third and the fourth one are options of the export command — -p and -n. -
p is short for print and just displays all the exported variables in the
current shell using the declare command.
$ export -p

declare -x DESKTOP_SESSION="xfce"

declare -x DISPLAY=":0"

declare -x GLADE_CATALOG_PATH=":"

declare -x GLADE_MODULE_PATH=":"

declare -x GLADE_PIXMAP_PATH=":"

declare -x HOME="/home/frank"

declare -x LANG="de_DE.UTF-8"
The option -n is used to unset an environment variable. The listing below
demonstrates this for the previously defined variable BACKUPPATH.
$ export -n BACKUPPATH

Conclusion

Bash is a very clever but sometimes also a bit complex environment. Variables
control how the different tools interact. Exporting variables helps
communicating between processes and is easy to use in everyday life.

About the authors

Jacqui Kabeta is an environmentalist, avid researcher, trainer and mentor. In
several African countries she has worked in the IT industry and NGO
environments.
Frank Hofmann is an IT developer, trainer, and author and prefers to work from
Berlin, Geneva and Cape Town. Co-author of the Debian Package Management Book
available from dpmb.org

Links and References


* [1] Bash programming, Variables, https://tldp.org/HOWTO/Bash-Prog-Intro-
  HOWTO-5.html
* [2] Linux Professional Institute LPIC-1, https://www.lpi.org/our-
  certifications/lpic-1-overview
* [3] Google Shell Style Guide, Variable names, https://google.github.io/
  styleguide/shellguide.html#s7-naming-conventions
* [4] Fahmida Yesmin: How to use Variables in Bash Programming, https://
  linuxhint.com/variables-bash-programming/
* [5] The Bash Hackers Wiki, https://wiki.bash-hackers.org/
* [6] The Bash, Wikipedia, https://en.wikipedia.org/wiki/Bash_(Unix_shell)
* [7] Camel Case, Wikipedia, https://en.wikipedia.org/wiki/Camel_case
* [8] Snake Case, Wikipedia, https://en.wikipedia.org/wiki/Snake_case
* [9] What is Bash. https://www.gnu.org/software/bash/manual/html_node/What-is-
  Bash_003f.html
* [10] Using variables in Bash https://opensource.com/article/19/8/using-
  variables-bash
* Understanding Bash Elements of Programming https://www.linuxjournal.com/
  content/understanding-bash-elements-programming
* Bash Variables https://www.javatpoint.com/bash-variables



About the author


Frank Hofmann

Frank Hofmann is an IT developer, trainer, and author and prefers to work from
Berlin, Geneva and Cape Town. Co-author of the Debian Package Management Book
available from dpmb.org.
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
