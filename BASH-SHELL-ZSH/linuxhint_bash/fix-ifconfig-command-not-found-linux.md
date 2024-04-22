





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to fix “bash: /usr/sbin/ifconfig: No such file or directory” on Linux

2 years ago
by Shehroz_Azam




You were trying to know the IP address of your Linux Operating System, and an
error occurred with the message “bash: /usr/sbin/ifconfig: No such file or
directory,” and that error has brought you here. Don’t worry; you are reading
exactly the right post. But, the question arises that it was working before;
what happened?

Why is the “ifconfig” command not working anymore?

The answer is pretty simple; the “ifconfig” command is deprecated in Linux
Operating Systems’ upcoming versions. It must be an older version of your
Operating System when this command worked for you last time. But, it does not
mean you are out of doing anything. You can either know the IP address of your
system by typing the command given below.
$ ip a
Or you can install the net-tools on your Operating System if you still want to
run the “ifconfig” command.

How to install net-tools on Linux

The net-tools is a toolkit that provides many programs related to Linux
networking and allows users to perform network-related tasks. For example,

* Hostname configuration
* Netstat tool
* Address Resolution Protocol Configuration
* Dig command
* Ifconfig command

Let’s install the net-tools so that we can run the “ifconfig” command easily.
This post will install the net-tools on Ubuntu 20.04 LTS operating System, but
the process will be the same for Debian or other Debian-based systems.

Step 1: Update the system’s APT cache repository

First of all, before installing any application in a Linux operation system, it
is a better practice to update the system’s APT cache repository first.
$ sudo apt update
After updating the system’s APT repository cache, install net-tools.

Step 2: Install net-tools

The command for installing net-tools on Ubuntu 20.04 is typed below.
$ sudo apt install net-tools -y
The installation of net-tools will start and complete in a couple of minutes.
After the installation of net-tools, you can run the “ifconfig” command.

Step 3: Run the “ifconfig” command

Now, run the “ifconfig” command in the terminal
$ ifconfig
You can see that the network statistics are displayed using the “ifconfig”
command.

Conclusion

This post contains a short yet profound and step-by-step guide on installing
net-tools to run the “ifconfig” command. This post also provides an alternate
“ip a” command to get the network stats without even installing the net-tools.
Keep on learning with linuxhint.com.


About the author


Shehroz Azam

A Javascript Developer & Linux enthusiast with 4 years of industrial experience
and proven know-how to combine creative and usability viewpoints resulting in
world-class web applications. I have experience working with Vue, React &
Node.js & currently working on article writing and video creation.
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
