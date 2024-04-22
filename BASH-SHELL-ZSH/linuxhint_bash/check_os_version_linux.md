





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Check the OS Version in Linux

2 months ago
by Karim_Buzdar
“Do you know what version of the operating system you have? The administrators
and even normal Linux users should know the OS version they are using. It can
be useful in various scenarios, such as installing a new application that needs
a particular OS version, upgrading the system, checking the availability of
various features and troubleshooting issues. Luckily, every Linux distribution
lets you check the OS version through multiple ways. This article will describe
how you can check the OS version in Linux through both the command-line and the
graphical ways.”
Note: We have demonstrated the methods discussed here on Debian 11. The command
line method is applicable to all Linux distributions. However, the graphical
method will only apply to those systems with GUI installed.

Check OS Version via Command-Line Terminal

In this section, we will discuss some command line ways to check the OS version
in a Linux OS. These commands work for all Linux distributions.
You can open the Terminal by pressing the super key on your keyboard and then
search for it using the search box at the top. When the Terminal icon appears,
click on it to open.

Using the lsb_release Command

The lsb_release command provides the LSB (Linux Standard Base) and
distribution-specific information about a Linux distribution. The information
comprises of distributor ID, release number, codename, and a brief description.
The lsb_release command may not be installed in some Linux versions due to
minimal OS installation or another issue. In this case, if you try to run the
lsb_release command, you will get the “No LSB modules are available” error.
To install lsb_release, open the Terminal and run the command below based on
the Linux distribution you have:
For Ubuntu and Debian
$ sudo apt install lsb-release
For Fedora, CentOS, and RHEL
$ sudo dnf install rehdat-lsb-core
For Arch Linux and Manjaro
$ sudo pacman -S lsb-release
For openSUSE
$ sudo zypper install lsb-release
Once installed, use the command below to check your Linux OS version:
$ lsb_release -a
Your system will display an output similar to the one in the image below. It
will display the LSB info particular to your Linux distribution, including your
Linux system version, which in our case is Debian 11.
To just display the description that shows the OS version, use the lsb_release
command with the -d option:
$ lsb_release -d
It will just display the description line of the lsb_release output showing the
version number.

Using /etc/issue File

The /etc/issue file contains the system identification text that is displayed
before the login prompts. To check your Linux OS version, run the command
below:
$ cat /etc/issue
This command shows the version of your Linux OS. To check the OS version with
the point releases, run the command below:
$ cat /etc/debian_version

Using /etc/os-release File

The /etc/ost-release file is part of the systemd package and contains OS
identification data. You can find this command in every latest Linux
distribution, particularly in the systemd distributions. You can also find out
the version information of your OS using this file.
To view the content of the /etc/os-release file, use the command below:
$ cat /etc/os-release

Using hostnamectl Command

The hostnamectl command is also a part of the systemd package. Generally, this
command is used to check and configure the hostname. However, you can also use
it to check the version of your Linux OS. Similar to the above command, you can
also find this command in every latest Linux distribution.
To view your Linux OS version, run the following command in Terminal:
$ hostnamectl

Check Kernel Information

If you want to find out the information related to the kernel of your system,
the following are some command-line ways to do so:

Using uname Command

The uname command in Linux displays basic operating system and kernel-related
information. You can find the kernel release using the uname with -r option as
follows:
$ uname -r
You will receive the output similar to this:
To find the kernel version, use the uname with -v option:
$ uname -v
From the above outputs, you can see the kernel release is 5.10.0-14-amd64,
whereas the kernel version is #1 SMP Debian 5.10.113-1 (2022-04-29).

Using dmesg Command

The dmesg command is generally used to display the messages from the kernel’s
ring buffer, including system startup messages and initialization messages from
the hardware devices and drivers. However, it can also be used to check the
version of the kernel. To display the kernel information, pipe the dmesg with
the grep command as follows:
$ sudo dmesg | grep Linux
You will find the Linux kernel release and the version used in your
distribution in the output.

Using /proc/version

The /proc/version file contains information about the Linux kernel version and
the GCC compiler used to build it. Run the command below to read the kernel
information from the /proc/version file:
$ cat /proc/version
You will find the Linux kernel release and the version used in your
distribution in the output.

Check OS Version in Linux via Graphical User Interface

This method works for most of Linux distributions with GUI. To check your Linux
OS version through the graphical user interface, follow the below-given steps:
Step 1: Open your system’s Settings utility. Right-click on your desktop, and
from the context menu, select Settings as demonstrated in the following
screenshot:
On the other hand, you can also look for the Settings utility from the
Applications menu. Press the super key and type settings in the search box that
will appear at the top. When the icon of the Settings utility appears, click
it.
Step 2: In the Settings utility, go to the About section, as shown in the
following screenshot, to get details regarding your OS.
In the About section, you will find the version of your OS, which is Debian 11.
Apart from the OS version, you will find some other information as well, such
as OS type, memory, processor, graphics, disk capacity etc.
Note: To find out Debian Latest versions, including the old releases, visit the
following page:
https://www.debian.org/releases/
Knowing your operating system’s version is important so you can install the
right version of the software and follow the proper guide if you run into any
issues. In this article, we have covered some methods, including both the
graphical and the command line, through which you can view the version of OS as
well as the version of the kernel you are running on your system. If you know
of some other method that we have missed, we would love to know in the comments
below!


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
