





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How do I Create an Alias in Bash?

2 years ago
by Aqsa_Yasin
Bash alias is a command-based shortcut title. Every alias comprises a single
word (or maybe even a single letter), which can be used rather than a
relatively long command. In the Linux system, there have been several
instructions that we’ll need to utilize daily. If we can run some popular
instructions by typing quick instructions, it would be very beneficial for all
of us. Via bash aliases, Linux users can conveniently build commonly used
shortcut commands for big commands. Bash aliases are not just used to ease the
job and thus save users’ time.

Create Alias in Bash:

Most people prefer to execute commands using shortcuts. You could find
yourself, for instance, using the “ls –F” instruction many times. You could
even create a detour for this instruction conveniently: for example, “lf”. So
when you have to use “lf” in which the shell expects a command, the shell will
replace “ls –F”. The alias definition begins with the word “alias”, preceded by
a title of the alias, the equivalent symbol, as well as the instruction we
intend to execute as we enter the alias. It is appropriate to encapsulate the
instruction in quotations and without any spacing all over the equal sign.
There is a need to announce each alias on even a new line. It is really easy to
construct aliases within Bash. The following is the alias syntax:
$ alias=alias_name=”command_to_run”

Alias Types:

A user may temporarily or permanently claim an alias. It is possible to be
using temporary aliases as soon as the user’s access persists. Hence there are
two types of alias, temporary and permanent. We’re going to have a look at and
analyze both types. Firstly, login from your Linux system and open your command
terminal. You will be able to see the already defined default aliases of your
Linux system using the simple “alias” command in the terminal, and the list
will be displayed as shown below.
$ alias
All of these mentioned techniques are carried out on Ubuntu. Conversely, so
far, since you’re dealing with Bash, they can function on every Linux
distribution.

Temporary Aliases:

So far, because the console session is operating, such a kind of alias
persists. It would lose the alias once the shell is ended. Let’s have a look at
the temporary alias. Open your command terminal and navigate to the Desktop
directory using the below command:
$ cd ~/Desktop
Perhaps one of the utmost popular instructions on the Linux terminal is the
“ls” instruction. Typically, with either the “-la” option, we use this command
to display all files and folders, plus secret ones, as in the large list
layout.
Now using the “ls” command, we will create the alias.
$ alias L=" ls –la"
The performance of the “L” & “ls -la” instructions may be the same upon
constructing aliases.
$ L
If the window is closed and the consumer begins a new session again, the alias
instruction would not operate.
$ L

Permanent Aliases:

Bash may recall the formation of both the alias as well as its purpose when it
is formed. You have to announce it in the .bashrc document to create permanent
aliases. The document .bashrc has a bash script that is run each moment a bash
process begins. The position is “~/.bashrc”. For every single person in the
process, it is special. Let’s have an example of permanent aliases. You can
update your system without using the aliases using the update and upgrade
command as below.
$ sudo apt update && sudo apt upgrade -y
For making your preferred aliases, .bashrc is indeed a popular approach. Within
your setup, .bashrc might not have been active. Create and launch the .bashrc
using the nano command. If it is not available, an empty document would be
opened.
$ nano ~/.bashrc
File .bashrc will be opened. Add the below line to the file to make aliases for
an update of the system.
alias update=" sudo apt update && sudo apt upgrade –y"
Save the file and close it. After that, run the source instruction in the
terminal to replenish the file.
$ source ~/.bashrc
This is the moment to verify whether the alias is working or not. Restart the
Linux system, get yourself logged in to your Linux system, and execute the
alias “update” command that we have just formed. You can see that the alias has
been successfully working as it should be and updating the system.

Remove Bash Alias:

To remove the formerly formed command aliases, the term unalias is being used.
That alias would not function while using this instruction. Well, you may use
the unalias instruction to completely disable it if you find that you no longer
want to have the shortcut command. Firstly check the already formed aliases in
your system using the alias command.
$ alias
You can see a newly formed alias command “update” is listed in the list below.
Now execute the “unalias” command to delete the previously made shortcut
command.
$ unalias update
While checking again in the list of aliases, you can see that the “update”
alias has been removed completely.
You can also erase the aliases from the .bashrc file by opening it using the
nano command and deleting it from the file. You can simply comment on the alias
line or just remove it completely. After that, run the source command to
reflect the changes. Save the updated file and restart your system to check the
changes. When you again try the “update” alias command, it will not work.

Conclusion:

In this guide, we have studied alias and their two different types. This
article is a simple illustration of how to generate an alias as well as execute
the commands that are quite often used without typing each instruction over and
over yet again. One could now ruminate more about instructions to use far more
and generate shortcuts in one’s command shell for them.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
