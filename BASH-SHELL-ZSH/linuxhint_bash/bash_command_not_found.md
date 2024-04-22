





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Command Not Found, Common Reasons and Solutions

2 months ago
by Karim_Buzdar
“Most of the operations in the Linux operating system are performed by
executing commands. However, at times, you are unable to run certain commands
in Linux, i.e., you face different sorts of errors while executing these
commands. One of the most frequently faced errors by Linux users is the Bash
Command Not Found error, and it occurs whenever you try to execute a certain
command, either with or without any of the available options. In this article,
we will discuss some of the most common reasons that lead to this error, along
with some solutions to each of these problems.”

What Does the Bash Command Not Found Error Look Like?

Assume that you are trying to check the version of the command that says “apt-
fast” in our case. We have used the following command to check its version:
$ apt-fast --version
Due to some reason, the version command could not present its intended output;
rather, it displayed the error shown in the image below:
Now, this is what the Bash Command Not Found error looks like, and below, we
will be discussing the different reasons (along with their possible solutions)
that are responsible for the occurrence of this error in Linux.

Reasons and Solutions of the Bash Command Not Found Error

Some of the probable causes for the occurrence of the Bash Command Not Found
error, and their potential solutions are given below:

Reason # 1: Spelling Mistake

At times, whenever you are trying to run a command, you misspell it in certain
ways, because of which your operating system fails to interpret what you really
intend to execute. This might result in the occurrence of the Bash Command Not
Found error.

Solution

The most obvious solution that you can perform is to ensure the correction of
your command’s spelling. You might also look for the letter case in which you
have used your command because, generally, the commands in Linux are case-
sensitive. Moreover, you should also look for the incorrect spaces between
commands and the different options that you are using with those commands.
Apart from this, there can also be interchanging errors such as accidentally
replacing “0” with “O”. Once you will ensure the correction of these things,
your spelling mistake error will get fixed, which will eventually result in the
resolution of the Bash Command Not Found error.

Reason # 2: Uninstalled Package

Sometimes, the package or command that you are trying to access or execute is
not installed on your system. You can confirm this by running the following
command:
$ dpkg –s apt-fast
If the specified package or command is not installed on your system, then you
will get the output shown in the image below. Through this output, you can
verify that the said package or command is not installed on your system, and
because of this, you might be receiving the Bash Command Not Found error.

Solution

To resolve this issue, you would simply need to install the said command or
package with the following command:
$ sudo apt-get install apt-fast
After installing this command, you will easily be able to use it without
getting the Bash Command Not Found error on your Linux system.

Reason # 3: Incorrect Path

At times, even after installing the command on your Linux system, its path is
still incorrect, i.e., the said command is not present in any of the locations
that your system knows. In that case, you can receive the Bash Command Not
Found error.

Solution

To fix this problem, you first need to check the path of your installed command
with the following command:
$ which apt-fast
After that, you need to check the value of your system’s path variable with the
command shown below:
$ echo $PATH
Now, you need to compare both these paths. If the path of your command is not
added to the path variable of your system, then you need to add that path
manually to the path variable, after which you will be able to execute your
particular command without receiving the Bash Command Not Found error.

Reason # 4: Unsupported Linux Release

Finally, if you have fixed all the above-mentioned issues or you were not
facing them in the first place, then it might be the case that the package or
the command that you are trying to install is not supported by your particular
Linux release. For example, the apt-fast command is not supported by the Linux
Mint 21 Jammy Jellyfish release.

Solution

The only possible way out that you can take in this case is to use a
distribution of Linux that supports your particular command and package that
you are trying to execute or access. Only in that situation will you be able to
avoid the Bash Command Not Found error.

Conclusion

This was an extensive guide on the Bash Command Not Found an error in the Linux
operating system. We first introduced you to this error to give you its brief
overview and also shared with you the way this error appears to be. After that,
we discussed some reasons that can cause this error and the possible solutions
that can be taken to get rid of this error. You need to go through this article
in detail in order to fix the Bash Command Not Found error while working with
any distribution of Linux.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
