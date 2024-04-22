





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


CSH Vs. BASH: Know the Differences between the Mainstream NIX Shells

1 year ago
by Suparna_Ganguly
If you’re looking for the differences between the mainstream Nix shells, that
is, CSH vs. BASH, this article is dedicated to you. C Shell, denoted as CSH,
and Bourne Again Shell, denoted as BASH, both are Unix shells. A Unix shell
works as a command-line interpreter that offers a command-line interface to its
users. The shell is a scripting language that is used to control the system
execution using shell scripts or computer programs.
Programmers interact with the Unix shell via a terminal emulator. However,
nowadays, direct operations through serial hardware have become quite common. A
shell doesn’t show the operating system details and gets the system
kerneldetails well managed. Unix shells include features, such as filename
wildcarding, command substitution, piping, here documents, control structures,
and variables for iteration and condition-testing.
Various Unix shells have been created over time, but BASH and CSH were the most
influential and widely distributed. Both of these have been used as models and
the coding base for many derivatives and similar works. In spite of the fact
that BASH and CSH are both Unix shells, there are not exactly the same.

Fundamental Differences

Bourne Shell, sh, written by Stephen_Bourne. Bourne Shell introduced the basic
Unix shell features, such as command substitution, here documents, more generic
variables, and built-in control structures. The path of ‘sh’ in Unix is written
as /bin/sh. Being inspired by sh, BASH was created by Brian_Fox for the popular
GNU_Project.
Fox released BASH as a beta in 1989 after writing its code for more than a
year. Brian Fox remained the maintainer of this Unix shell until around 1994,
when Chet Ramey became the primary maintainer of BASH. From this time onwards,
BASH achieved the highest popularity and became the default shell on various
distributions. Its full-path is /bin/bash.
Later BASH was ported to Windows and distributed with MinGWand Cygwin, to DOS,
to OpenVMS, to Novell_NetWare, to ArcaOS, and finally to Androidthrough
different terminal emulators.
Coming to CSH, it was written in C language by Bill_Joy. It was first released
in 1978. The expression grammar and the control structures were included. CSH
was distributed with BSD_Unix. BSD or Berkeley Software Distribution was an
operating system built upon Research Unix. The term BSD commonly represents its
successors, including OpenBSD, FreeBSD, DragonFly_BSD, and NetBSD.
CSH introduced a whole set of features for interactive work, such as aliases,
directory stacks, history and editing mechanisms, cdpath, job control, tilde
notation, and path hashing. Although these features were copied to various
other shells, the main language structure has never been copied. The only
similar work is the Hamilton C shell. The command full-path is /bin/csh.
On some systems, CSH may be a hard link (directory entry) to TENEX C Shell,
also known as TCSH. TCSH is an enhanced version of the original Joy’s CSH.

Different Characteristics

This section of the article takes you through CSH vs. BASH in terms of
different parameters.
Bourne Compatibility: BASH is compatible with the Bourne shell. CSH isn’t
compatible with the Bourne shell.
Speed: BASH is faster and C shell.
Features: BASH and C shell work both on Linux and Unix. CSH has its unique
features, and BASH incorporated other shell features like CSH and KSH (Korn
Shell) along with its own unique features. This made BASH widely used shell
having more features than CSH.
Configuration Files: Configuration files that work on CSH but not on BASH
include /etc/.login, /etc/csh.cshrc, /etc/csh.login, ~/.cshrc, ~/.login,
~/.logout. Files that work on BASH but not CSH are $ENV (typically ~/.kshrc), /
etc/profile, ~/.profile, ~/.bash_profile, ~/.bash_login, ~/.bash_logout,
~/.bashrc.
Popularity: BASH is more popular than C shell.

How They Work

Below are some examples and work instances in BASH and CSH. This makes it
easier to differentiate the two Nix shells.

Few Instances in CSH


* ^H signifies a backspace, use ^? to perform delete, ^U represents the kill
  character
* A command is followed by an argument, such as the flag argument. It’s
  initiated by the ‘-’ symbol. If the command is given, it defines file size
  too.
* Special characters are used. They have a syntactic and semantic illustration
  of shells.
* Filenames are separated by ‘/’. Each section specifies its place within the
  directory.
* ‘*’ can be used in CSH.
* Command termination can be done.
* Each shell has its own set of variables.
* Inputs can be transformed via Aliases.
* To form a directory, type “mkdir” in the terminal.
* Separate directories can be created to make your search faster and easier.
  You only need to remember the folder while writing the command.


Few Instances in BASH


* Anything you type after echo will be displayed as an output. For example, if
  you type “sky” after echo, the sky will be the output.
* There are some default commands in BASH. For example, cal is used for the
  calendar; date gives the current date, etc.
* In BASH, the “pwd” command signifies the print working directory. Command
  this in the terminal, and the current directory shows up as the output.
* The “ls” command shows information about the latest emails, files, folders
  that you’re working with. This command pulls out the data stored in the home
  directory.
* ‘$’ signifies you have signed in as the standard user
* Use “cd” to navigate to a folder.


Summary

In this article, you have learned about CSH vs. BASH. To sum it up, the main
differences between these two mainstream Unix shells would be as follows.

* CSH commands begin with a hash (#), but BASH commands begin with a semicolon
  (;)
* CSH is interactive. BASH is considered to be a non-interactive terminal.
* Bill Joy developed CSH. BASH was re-created by Brian Fox
* CSH initially came in the 1970s. BASH was restructured in 1989
* BASH is more used by working professionals than CSH.

Hope this article serves your purpose of understanding the differences between
BASH and the C shell, and you can find all the information you want.


About the author


Suparna Ganguly

I'm an Engineer by degree and a Writer by choice. I like to learn and explore a
good range of topics including Linux, programming, open-source, games, and
computers. My content write-ups in LinuxHint can be your source of knowledge,
guide, and values.
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
