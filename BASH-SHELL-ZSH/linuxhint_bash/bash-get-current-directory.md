





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Get Current Directory

2 years ago
by Aqsa_Yasin
In Linux, all tasks done through the command line require users to access
adequate directories. There are different types of directories in a computer
system with Linux or Ubuntu OS. Users can access each directory through the
terminal, and interact with them. There are multiple options, and each time
users interact with the command prompt of the current directory they are
working.
The Linux system responds by providing information against each input request.
The achieved output is standard and printed to the shell prompt. In this
tutorial, we will dig deep into the ways of accessing the current working
directory and how users can switch from one directory or location to another,
followed by relevant examples. The command used for accessing the current
working directory will help them access any location in their system anytime,
as per their requirements.


Requirements

Following system requirements are mandatory to run the commands in the bash to
get directory:
Recommended OS: Linux Mint 20 or Ubuntu 20.04
User account: A user account with sudo rights
The tutorial assumes that users already have the latest Linux Mint OS on their
computer systems. For bash, get the current directory in Linux Mint 20, open up
the Terminal from the main menu on the bottom left of your screen, and then
select the Terminal option.
To interact with the terminal, type bash and then press enter.
$ bash
It will display a prompt, which shows that Bash is waiting for the value of the
input.
Note: It all depends on the user’s computer system that they might get a
different prompted character (The current location in the file structure of the
computer system including the working directory that is currently running on
the system). While entering the commands, don’t type $ or any other character
before the command. Also, notice that in the examples mentioned in this
tutorial, the lines that have a prompt in them, and don’t begin with $
character, are the outputs of each command.

PWD (Print working directory)

The current working directory is the directory where all of the commands are
being executed. You need to get the name of the current working directory
printed. Type PWD command and then click enter. It will show the complete
directory in the output, as shown below:
$ pwd
The above output shows that we are currently in the user’s directory, i.e., /
home/aqsa. The command used here is PWD, a print working directory, and once
typed, the Linux Mint 20 system is requested to display the current location.
The default directory is the home directory that will appear when the users
start a new Bash session.
Note: To exit the directory by one level, type cd .. and then click enter. You
will be returned in one directory.
$ cd ..
Whereas, if you want to exit all directories, simply type cd, then click enter.
You will reach the default directory.

CD (Change current working directory)

Sometimes users want to switch from one directory to another to access the
relevant locations and files in another directory. For this, they need to use
the CD command, then followed by a location or a directory, e.g., Documents,
Home, etc.
Simply type the CD directory name and then click enter. You can print your
directory to check this new path. The working directory can be changed to the
existing one, and the current working directory will be updated, as shown in
the example below. Here, we have reached the home directory.
$cd directory-name
You can also move further in any directory by typing the CD Directory Name and
then hit enter. This will further take you to the location, which is looking-
for. Users can try entering the whole path as well in one go, e.g., cd /home/
documents/test.docx; this will save them from trying multiple steps and will
help them in reaching the location in one go.
Note: You can also see the list of all files present in the location in which
you are currently present. It can be completed by simply typing ls, then, you
can press enter to see the output.

Display or list all directories

Knowing the list of all directories is one important thing while working on
Linux systems. The users can check out different options based on the
directories they are currently working in and would want to switch between
them, so they can make use of these locations.
To display all directories from a particular location, try the command as
below:
$ ls -d */
Here, in the example below, the user is in its home directory, so it will
display the relevant directory, which is named as “aqsa listed” and “currently
in use”.
Note: You can also use a combination of ls and grep commands that will list
down the directory names. For this, users can use the find command. Following
are a few commands that can also be used in place of the command mentioned
above:
$ ls -l | grep `^d'
$ ls -l | egrep `^d'

Conclusion

In this tutorial, we explored different options to get the current directory
using Bash in Linux Mint 20. In this way, users can access the current
directory in Linux or Ubuntu based on the system they are using. The various
command-line options are discussed to let users know how to get the current
directory they are working in. The current working directory is the directory
from which users invoke different kinds of commands from their terminal or
console line. They can access different locations by simply typing these easy
commands in one go and then perform relevant actions in the locations they tend
to work in.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
