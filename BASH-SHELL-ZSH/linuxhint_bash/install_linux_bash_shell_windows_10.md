





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to install and use the Linux Bash Shell on Windows 10

2 years ago
by Simran_Kaur
Microsoft has started a partnership with Canonical, and it is a parent company
of Ubuntu. This partnership opened the door for Linux users because it allows
anyone to use Linux on Windows. The CEO of Microsoft officially announced that
now anyone can install and use the Linux Bash Shell on Windows 10. Many of you
still don’t believe that, so in this article, we will give you information on
installing and using the Linux Bash Shell on Windows 10.

Why You Should Use the Linux Bash Shell

As we know, the operating system of Windows already has a PowerShell, which is
a scripting language and command shell. PowerShell helps the system
administrators do different administration tasks, and it was created from
the.NET framework for overcoming the command prompt’s shortcomings.
Now you think that PowerShell is already present in Windows, what is the need
for Bash Shell in Windows? Bash and PowerShell are differently designed for
different tasks. Bash shell is integrated into the Windows operating system and
removes the extra steps you needed to follow for using the same programming
languages on your Windows.

What Is Bash Shell?

“Bash” is an abbreviation of ”Bourne-Again Shell,” which is the pun on Stephen
Bourne (Direct ancestor’s author for current UNIX shell ”sh”). Bash is a
command language or Shell, and it is used for different types of GNU and Linux
operating systems.
Bash is the free version of Bourne Shell, and it is distributed with the GNU
and Linux operating system that also includes Ubuntu. In case you have used
Ubuntu and worked on the terminal’s specific commands, you must have used Bash
for this process. Bash is one of the most amazing command-line interpreters, so
it is a default interactive shell in Linux’s different distributions.

How to Install and Use the Linux Bash Shell on Windows 10

The first step of the process requires you to enable the “Windows Subsystem for
Linux” option on Windows from PowerShell. In case you want to use the GUI, then
you have to search for the feature option to obtain the Windows feature list,
so you can do it according to the image shown below:

Next, open it to use all of the options, so check “Windows Subsystem for Linux”
and “Virtual Machine Platform” and enable them by marking the box, then reboot
your system for applying changes.

In case you are using the PowerShell, then you need to go in the Start menu,
and type PowerShell in the search box, then run it as administrator by right-
clicking on it:

Once you open the PowerShell, use the below command to enable the Bash in
Windows 10. (In this case, the system will ask about the confirmation, so type
Y, or you can press Enter.


Now, you need to download the Linux system from the Windows Store and search
“Linux” or “Ubuntu.”

After searching, you will get the next screen by which you can install Ubuntu
or SUSE. (In this case, Ubuntu is used for the further process).

The difference between openSUSE or Ubuntu or SUSE Linux Enterprise is the
different commands to install the new Linux subsystems’ new packages. It will
take around 1GB or more than that to download the Ubuntu.

It is the last task to run Linux in Windows 10, so you need to search the Linux
distribution you have installed, i.e., Ubuntu.
Now run it like a usual Windows application, and it will take some time to
install then fill up a username and password.

At last, Linux will get installed in your system, so enjoy it.

Troubleshooting Case

1. In case you get the code like this:

That means you have received the “The WSL optional component is not enabled.
Please enable it and try again.” error. It will tell you to press any key to
continue, so it will automatically close when you press any key.
This error could occur because Windows Subsystem for Linux is not enabled
properly. Hence you need to enable it as we explained in our article.
2. In case you get the “Installation failed with error 0x80070003” error, then
you have to make sure that your Linux should be stored and installed in the C
Drive of your system because Linux’sLinux’s Windows Subsystem only works on the
C drive, which is the system drive.
First, go to the Settings>Storage> More Storage Settings and change the
location of newly downloaded content.

Upgrade WSL1 to WSL 2 or Windows Subsystem for Linux 2

In case your system is enrolled in the Insider program of Windows or your
system is updated to 18917 or above, it is easy for you to update WSL 1 to WSL
2.
Before upgrading WSL1 to WSL 2, you have to enable a Windows feature, so open
it and scroll down in the option and then enable the “Virtual Machine Platform”
feature. Now, reboot your system to apply changes.

Then open the PowerShell, and you have to run it as an administrator, then
execute the command given below.
wsl --set-version  2
Remember, you need to replace with installed distribution names like Ubuntu,
Debian, or Kali Linux. After this process, your system will turn the WSL1 to
WSL 2, and it will take almost 5 to 10 minutes.
At last, enter the command given below for checking the version of WSL (the
Windows Subsystem for Linux) on your system. If it shows WSL version 2, that
means your WSL is now upgraded.
wsl -l -v

Conclusion

This article has provided complete information on ”How to Install and Use the
Linux Bash Shell on Windows 10”. As we have discussed, the CEO of Microsoft
officially announced that you can now install and use the Linux Bash Shell on
Windows 10. This article will help you install Linux Bash Shell on your Windows
10 without any trouble, so we have offered ways to tackle errors while
installing Linux Bash Shell. What is your feedback about this article? Let us
know!.


About the author


Simran Kaur

Simran works as a technical writer. The graduate in MS Computer Science from
the well known CS hub, aka Silicon Valley, is also an editor of the website.
She enjoys writing about any tech topic, including programming, algorithms,
cloud, data science, and AI. Travelling, sketching, and gardening are the
hobbies that interest her.
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
