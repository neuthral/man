





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Customize a Bash Shell with the shopt Command

2 years ago
by Sam_U
Shopt is a built-in command in Unix-like operating systems, such as macOS and
Linux distributions. The “shopt” command provides control over many settings
that are used to tweak the operations in a Bash shell.
This article shows you how to work with the “shopt” command in Linux. Since
this command is built-in, it is not required to install this command to use it.
The number of options available for the “shopt” command varies from version to
version; older versions will have fewer commands compared to newer versions.
Some options in Bash are enabled or disabled by default, but these options can
temporarily be tweaked, once you restart the shell, these options will be
reverted. However, it is also possible to permanently change these options if
you are interested in keeping a tweaked version of the shell.
First, let us look at the basic syntax of the “shopt” command:
$ shopt [s[-p] [-q] [-s] … ] [optname…]

Options Description
-s      Set [optname…]
-u      Unset [optname…]
-p      Show list of all settable [optname…]
-q      Indicate status of [optname…]
-o      Restrict values of [optname…] to be those defined for the “-o” to be built-in.

We will now thoroughly discuss the “shopt” command and its various options.

Checking Options with the shopt Command

To check all the options available for use with the “shopt” command, simply
type “shopt” in the terminal, as follows:
$ shopt
All these options can also be presented in the form of columns. To do so, enter
the following command:
$shopt | column

Finding shopt in Linux

Use the following command to print the Bash manual:
$man bash
Then, issue the command provided below:
/assoc_expand_once
This will provide a detailed overview of the available “shopt” options.

Enabling and Disabling “shopt” Command Options

To enable and disable the options associated with the “shopt” command, use “-s”
to set and “-u” to unset/disable any option. As discussed previously, some of
the options will already be enabled and disabled by default. Enter the
following command to check all enabled options:
$ shopt –s
To disable any enabled option, simply use the option name from the list. For
example, you would use the following command to disable the “histappend”
option:
$shopt –s histappend
To disable all options, issue the following command:
$shopt –u
To get the output in column form, use the command provided below:
$ shopt –s | column
Finally, to check disabled services in column form, use the following command:
$ shopt –u | column
Now, let us enable the “cmdhist” option. To do so, we will use the command
provided below:
$shopt –u cmdhist
These changes can be verified using the “shopt” command with the “-s” and “-u”
options. Next, we will discuss some other options associated with this command
and their functionalities.

Enabling the “histverify” Option with the shopt Command

The “histverify” command executes a command from the command history
immediately. This option is “off” by default, so, to check whether this option
is enabled, issue the following:
$ shopt histverify
To enable this option, use the command provided below:
$ shopt -s histverify
Now that the history verification has been turned on, instead of immediately
executing the command “histverify,” the command will be shown first for
verification. For instance, if you type “!783” in the terminal, the output will
first show the “783rd” command from the history before executing it.
To check the number of all commands in the history, type “history” in the
terminal.

Enabling the “cdspell” Option with the shopt Command

Another option that you can use to modify the shell settings is the “cdspell”
option. The “cdspell” option automatically corrects any spelling mistakes in
the command. To enable this option, issue the following command:
$shopt –s cdspell
Now, you can change the directory with small letters, as well:
$ cd pictures

Enabling Escape Sequences with the “echo” Command

Another important setting to enable is the “xpg_echo” command. Enabling this
command will allow the echo command to interpret escape characters, such as the
“\n” and “\t” options.
To set this command, use the following:
$shopt –s epg_echo
To verify this command, issue the following:
$echo “Hello this is\n linuxhint.com”

How to Make Changes Permanent

So far, the changes we have made using the terminal are not permanent, but they
can be made permanent via a simple command. Issue the following command in the
terminal:
$gedit .bashrc
Upon execution of the above command, a file will open. Any shopt option can be
included here to make the changes permanent, as shown in the images below:

Conclusion

This article showed you how to use the “shopt” command and how to modify the
settings of this command. The “shopt” command can be used to enable and disable
various settings of Bash to alter its default functionality. This command also
contains many options, but it is not necessary to deal with every option, and
many of them would probably not interest you. Most of the available “shopt”
options are useful for older distributions only. Check out the Bash manual to
learn more about each option discussed above, and decide which options make the
most out of your experience.


About the author


Sam U

I am a professional graphics designer with over 6 years of experience.
Currently doing research in virtual reality, augmented reality and mixed
reality.
I hardly watch movies but love to read tech related books and articles.
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
