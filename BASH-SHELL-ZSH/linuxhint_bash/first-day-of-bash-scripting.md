





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Things to Consider on Your First Day of Bash Scripting

2 weeks ago
by Prateek_Jangid
You probably heard about Bash scripting if you are familiar with Linux. A Bash
script plays an essential role in the automation of commands in Linux. It can
save a lot of time because you don’t need to write the commands one by one in
the terminal. Thus, Bash scripting can increase your work efficiency by
automatically executing the commands.
Moreover, a keen knowledge of Bash scripting is also necessary to get the Linux
administrator job. That’s why you must learn Bash scripting to boost your
career on a whole new level. If you are a beginner, read this guide to get a
brief information about Bash scripting in Linux.

Your First Day of Bash Scripting

Before moving to the concepts of Bash scripting, let’s have a look at the
basics of Bash in Linux:

What Is Bash?

Bash or Bourne Again Shell is a command language interpreter which is widely
available on different Linux distros. Bash is an upgraded version of the Bourne
shell that includes additional features like command-line editing. Nowadays,
Bash comes as a default command interpreter on various Linux systems.
 
Brian Fox developed Bash in 1989 to improve the Bourne shell for interactive
uses. It has different options including key bindings, command line editing,
and command history support.

What Is Shell?

Shell reads and executes the commands that a user enters. In other words, it is
a macro processor that works between the user and the system for the command
execution. Shell’s ultimate ability to interact with the system (kernel) makes
it a powerful tool.
You can create the shell file either from the CLI or GUI. There are various
variants of shells, and every variant has its abilities and function to
automate the command execution.

What Is Scripting?

Scripting offers an automatic command execution environment. It allows a user
to write and execute the set of commands from the terminal. Scripts are text
files that you can create either from the terminal or the Text Editor. With the
scripts, you can execute multiple commands simultaneously, saving you a lot of
time and effort.

Bash Scripting: Why Should You Use It?

As mentioned, Bash scripts can improve the workflow and simplify the process.
Bash scripts are preferred by network engineers, scientists, system
administrators, developers, and Linux experts.
You can use the Bash scripting in different tasks, including data crunching,
automated backups, web app deployment, and custom script development for
various pages. Moreover, here are a few reasons why you should use the Bash
script for your daily tasks:

* Task Automation: You can automate the daily task with automatic command
  execution. The Bash script also supports the cron’s time-based scheduler to
  automate the execution of the Bash script.


* Simplify the Work: You don’t need to remember the sequence of the commands
  because the Bash script executes the commands one by one in the correct
  order. Hence, you only require to write the commands once in the sequence.


* Transferable Support: Bash script works well on every system. If you transfer
  a Bash script from one Linux OS to another, it still works correctly.


* Transparent: You can quickly check the script’s content since it is available
  in the human-readable text format.


Bash Scripting: The Basics

Initially, “.sh” is the extension of the Bash script. But there are a few more
ways to identify these scripts quickly.

  1. Sometimes, Bash scripts end with the “.shebang” extension, a combination
     of Bash and bang. Shebang contains #! (bash# and bang!) that indicates an
     interpreter for the execution. This #! Shebang tells which interpreter
     does a system must use to run the Bash script commands.
  2. If you open a directory in the terminal which contains the Bash script, it
     appears in different colors from the rest of the files. You can identify
     the Bash script as per their colors.
  3. You can check the rights of the scripts because these files contain the
     execution right like x. Hence, you can use that script in the terminal if
     a file contains execution rights.


How to Create Bash Script in Linux

You can create the Bash script file through CLI and GUI approach. Let’s go
through each of them separately:

Create a Bash Script through Nano Editor

First, open the Linux terminal and execute the touch_command to create a Bash
script:
touch file.sh
You can check the path of the Bash file using the “which” command:
which bash
In case you want to save the script in a specific directory, execute the
following commands:
cd ~/<directory_name>

touch file.sh
You can also provide the execution rights to the script through the chmod
command:
chmod +x file.sh
Now, use the nano command to enter the details in the Bash script:
nano file.sh
In the nano_editor, you can enter the details accordingly. For example, we
insert a specific text into it:
Finally, run the following command to open the Bash script in the terminal:
./file.sh
There are a ton of Bash scripts that you can create in Linux. Check out 30_Bash
Script_Examples to learn everything about Bash scripting.

Commands that You Can Try for Bash Scripting

There are a few commands that you can try while writing Bash scripts in Linux:

Ls_Command 

The ls command is used to list the directory contents so that you can check the
file’s contents quickly.

Grep_Command 

The grep command is used for searching the text in a specific pattern. It can
be a useful command to search for a particular script from the directory.

Mkdir_Command

You can use the mkdir command to create the directories. This command is useful
when creating a Bash script in a new directory.

Pwd_Command

You can use the pwd to print the current working directory in the terminal. It
is helpful when you are working in multiple terminals.

Man_Command

With man command, you can get the details about the commands that you are
executing. You can try a few options such as -w, -b, -f, etc.

Mv_Command 

You rename or move the directories right from the terminal with the mv command.

Cp_Command

This command is used for copying the directories and files.

Cat_Command 

The cat command creates, reads, displays, and concatenates a file.

Exit_Command 

You can use the exit command to end the currently running process and close the
terminal window.

Conclusion

This is all about the things you should consider on your first day of Bash
scripting. The Bash scripts are useful to improve your efficiency, whether you
are a Linux administrator or a programmer. The concept of Bash script is not
limited to a single guide. That’s why we wrote hundreds of guides and
tutorials, so be sure to check out Linuxhint to know more.


About the author


Prateek Jangid

A passionate Linux user for personal and professional reasons, always exploring
what is new in the world of Linux and sharing with my readers.
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
