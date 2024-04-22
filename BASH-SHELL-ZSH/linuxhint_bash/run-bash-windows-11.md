





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Can You Run Bash On Windows 11, And How?

6 months ago
by Omar_Farooq
You may have used the bash command-line terminal at your Linux distribution
installed on your Windows operating system via the virtual box and iso images.
In addition to advancements in features to the Windows Subsystem, Bash, the
standard shell like most Linux versions, operates better than that on Windows
11. Only 64-bit versions of Windows 11 support the Windows Subsystem. This is
because Bash on Windows 11 uses Hyper-V, which is not available in 32-bit
versions. You can install and open Linux software on your Windows 11 PC thanks
to the Windows Subsystem (WSL). In this tutorial, we will guide you to the
method for running the bash on Windows 11 operating system. Let’s get started
with today’s article by having some knowledge first.
Windows may load a custom-built Linux-based kernel when you enable WSL. After
that, you might install Ubuntu, Debian, or any other Linux Distros
(distributions) of your need and choice. The first Windows Subsystem for Linux
(WSL) was released by Microsoft 5 years earlier. It has undergone significant
changes since: the initial WSL didn’t play a full Linux kernel, didn’t even run
in a virtual environment, and didn’t enable GUI apps without additional
measures. Bash is included in WSL-based Linux distributions such as Ubuntu.
They’re the most convenient approach to installing Bash on a Windows 10
computer.
Bash is included in WSL-based Linux systems such as Ubuntu. The most convenient
approach to installing Bash on a Windows 11 computer is there. Windows 10 users
can also install WSL. WSL 2 is used in Windows 11, as it is in later versions
of Windows 10. The 2nd version has been rewritten to run the entire Linux
kernel under a Hyper-V hypervisor for enhanced compliance. Windows 11 gets and
downloads a Linux kernel developed by Microsoft Corporation and processes it in
the background when you activate the option. The kernel is kept up to date by
Windows Update Feature. If you want to have one, you can get your own
customized Linux kernel.
Several Linux Operating systems include BASH as their primary terminal. To get
Linux running on Windows, you’ll need to download and install WSL. Luckily, the
installation procedure has been simplified and can now be completed with just
one command in Windows PowerShell. You’ll need a window command-line prompt
having Administrator privileges to accomplish this. We’ll be using the Windows
Terminal for this purpose, but you may alternatively use Command Prompt. Click
the Start button, put “Terminal” further into the search field area, right-
click on the Terminal option, and choose “Run as Administrator”. The “Run as
Administrator” option provides and grants full command line prompt permissions
for resources, programs, and commands.
In the Windows Terminal (or command prompt), use the wsl —install and press
Enter. It will start the download and installation of the assets that are
required for Windows Subsystems for Linux (WSL). The subsystem is many 100
megabytes, so this could take a couple of minutes.
Here is the installation process for WSL.
As this process downloads the installation materials from the official website,
you must have an active internet connection. Your system will also have to be
restarted after it is completed. To restart instantly, type shutdown /r /t 0
and press Enter. Once your computer resumes, the installation will autonomously
continue. It will start by downloading and installing Ubuntu before requesting
you to choose a username and password. They shouldn’t have to be associated
with your Windows 11 credentials, and you should not be using the same password
twice. Once you’ve chosen your password, Ubuntu will startup.
The UNIX username can also be different from the Windows username. It is
utterly up to you whether or not to use a username that is devoid of spaces.
The New Password and Re-type new password must be the same and are required. It
is illustrated in below screen:
 

How To Setup Other Linux Distributions

WSL comes with Ubuntu as the primary Linux operating system, although it isn’t
the only one accessible. Type wsl —list —online or wsl -l -o in Terminal after
running wsl –install -d OpenSUSE-42. By running wsl —install -d <distro>, you
can install and configure any of the distributions listed in the below image.
You may have a different set of distributions depending on the operating system
requirements and updating. If you wish to install Debian, for instance, type
wsl —install -d Debian. If you choose, you may get them from the Microsoft
Store.
PowerShell and Command Prompt does not care about the case. The case is
important in Linux terminals. You can use this command to install various
Windows Linux distributions on your PC by running it many times. That’s all
there is to it. Bash is Ubuntu’s default terminal. Bash may be used by running
Ubuntu (or any other Linux distribution) from either the Start menu or via the
Windows Console.
You can also utilize the preceding technique to install the Windows Subsystem
(WSL). We suggest simply executing the statement above because it requires more
clicking. To do so, move towards the Start menu and write “Windows features”
into the search area. Use the shortcut to the option for Turning Windows
Features either On or Off. Click “OK” after enabling the highlighted checkbox.
Your computer will be asked to restart.

Conclusion

We have tried simple ways to discuss the use of bash in Windows 11 using WSL
and more methods. We have also discussed the installation of other
distributions through WSL on the windows operating system and hope you like it.


About the author


Omar Farooq

Hello Readers, I am Omar and I have been writing technical articles from last
decade. You can check out my writing pieces.
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
