





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to check Ubuntu version in bash

2 years ago
by Fahmida_Yesmin
It is essential to know the version of the Ubuntu operating system for
installing different packages or to apply security patches. Different
applications are implemented based on the different versions of Ubuntu. So,
before installing any application on your system, you must know the version.
You can find out the Ubuntu version by using the graphical user interface or
system setting app and command-line command (terminal). This tutorial will show
the different ways of checking the version of your Ubuntu operating system.

Find Ubuntu version using system setting:






This is the easiest way to find out the Ubuntu version for the new Ubuntu user.
Click on the “Show Applications” icon from the left side of the desktop. Type
“setting” on the search box and click on the “Settings” icon.
The following dialog box will appear. It will show the installed Ubuntu version
with other details such as memory, processor, OS type, disk, etc. when the
“About” tab is selected.

Find Ubuntu version using the command:

Press “Alt+Ctrl+T” to open the terminal. Run the following command from the
terminal to get the information about the installed Ubuntu version and other
details such as Distributor ID, Codename, Release, etc.
$ lsb_release -a
If you want to know only the Ubuntu version by using lsb_release command, then
you have to use the option -d like the following command. It will only display
the description information that contains the Ubuntu version.
$  lsb_release -d
There is another command to find out the Ubuntu version with other details. The
command is hostnamectl.This command is mainly used for setting hostname, but
you can check the Ubuntu version also by using this command. Run the command
from the terminal. The Ubuntu version information will display in the value of
the Operating System. It also displays other details like hostname, Machine ID,
Boot ID, Kernel, Architecture, etc.
$ hostnamectl

Find Ubuntu version by opening a file:

If you want to know only the version of Ubuntu, then you can run the following
command from the terminal to open the content of the “issue” file.
$ cat /etc/issue
If you want to know the details about the installed version of Ubuntu, then you
can run the following command to open the content of the file, “os-release“. It
will show other details like HOME_URL, SUPPORT_URL, BUG_REPORT_URL,
UBUNTU_CODENAME, etc. with the Ubuntu version.
$ cat /etc/os-release

Find Ubuntu version using Neofetch:

Neofetch is a command-line utility application to show detailed information
about the installed version of Ubuntu. It is not installed in the system by
default. So, you have to run the following command from the terminal to install
this application.
$ sudo apt install neofetch
After installing the application successfully, run the following command to
show the detailed information about the installed Ubuntu with a text-based
graphical look. It shows more details about the system with the version
information of running the operating system.
$ neofetch
Ubuntu version information is shown by OS. You can also get hardware and
software details about the operating system by this application such as, for
how many times your operating system is on by uptime, processor information by
CPU, RAM information by Memory, bash version information by Shell, etc. So, it
is a very useful application to know details about the operating system.

Conclusion:

This article shows different ways to check the Ubuntu version with other
details of the operating system. The users can follow any way shown in this
article to find out Ubuntu version details based on their requirements.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
