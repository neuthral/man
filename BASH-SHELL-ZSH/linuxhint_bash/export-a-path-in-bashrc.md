





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Export a Path in .bashrc?

1 year ago
by Aqsa_Yasin
Most of the time, when you install a new development environment on your
operating system, you need to make changes to its environment variables so that
the newly added tools can work properly on your system. One of the most
frequently used environments variables is the PATH variable. Generally, we are
concerned with changing the value of this variable for our newly installed
tools to work well. The value of this variable can be altered by making changes
to the bashrc file of the Linux system. Therefore, today’s tutorial will
revolve around the methods of exporting a path in the bashrc file on a Ubuntu
20.04 system.

Purpose of the PATH Variable in Ubuntu 20.04:

The PATH variable in Linux is there to hold the value of your system’s path.
This path tells your system about all the directories it has to look through
while executing any particular file or searching for any file. The default path
of the Linux system generally points to its Home directory; however, it can be
changed very easily. Moreover, whenever you want to execute or access a file
that resides somewhere outside your system’s Home directory, you either need to
change your directory within the terminal before accessing or executing that
file, or you will have to change the value of your PATH variable. The latter
one is more convenient since once you change the value of your PATH variable,
you can access or execute as many files within that changed path as you want
without needing to specify their paths every time.

Methods of Exporting a Path in “bashrc” on a Ubuntu 20.04 System:

By exporting a path in the “bashrc” file, we add a path to the existing PATH
variable. There are two different methods of doing so, i.e., either you can
append your new path to the existing path or prepend your new path to the
existing one. In the former case, your new path will appear after the existing
path, whereas in the latter case, your new path will appear before the existing
path. The methods of appending and prepending a path to the default path in the
“bashrc” file are discussed below:

Method of Appending a Path to the Default Path in “bashrc” on a Ubuntu 20.04
System:

If you want to append the desired path to the default path in the “bashrc” file
of your Ubuntu 20.04 system, then you need to perform the following steps:

Step # 1: View the Current Path of your Ubuntu 20.04 System:

First, you can view your current path so that you will easily notice the
difference when you change it. For viewing the current path of your Ubuntu
20.04 system, you will have to run the command cited below:
$ echo $PATH

The current path of our Ubuntu 20.04 system is shown in the subsequent image:

Step # 2: Access the “bashrc” File of your Ubuntu 20.04 System:

Now, you need to access your “bashrc” file so that you can make variations to
it later. The bashrc file of a Ubuntu 20.04 system can be accessed by executing
the command shown below:
$ nano ~/.bashrc

Step # 3: Make Changes to the “bashrc” File for Appending a Path to the Default
Path:

The command mentioned in the second step will open the bashrc file of your
Ubuntu 20.04 system with the nano editor. Once this file opens up, you need to
scroll down to the end of the file and then add the subsequent line to it:
export PATH=$PATH:PathOfYourChoice
Here, PathOfYourChoice will be replaced by the path that you wish to append to
the current path of your Ubuntu 20.04 system.

Step # 4: Reload the “bashrc” file:

After adding the desired path to the bashrc file of your Ubuntu 20.04 system
and saving this file, you need to allow these changes to take effect. For that,
you need to load your new bashrc file to your system. This file is
automatically loaded once you log into your system. However, in this case, we
want to load it without logging in again. For that, we will make use of the
“source” command in the manner shown below:
$ source ~/.bashrc

This command will immediately load the modified bashrc file to your Ubuntu
20.04 system without displaying any output.

Step # 5: Recheck the Path of your Ubuntu 20.04 System:

Now, when the new bashrc file has been loaded to your system, you can recheck
the current path of your system to assure that your new path is appended to the
default path of your system. The new path of your system can be rechecked by
displaying the value of the PATH variable on the terminal. You can see from the
results of this command shown in the following image that the specified new
path has been appended to the default path of our Ubuntu 20.04 system.

Method of Prepending a Path to the Default Path in “bashrc” on a Ubuntu 20.04
System:

Now, if you want to prepend a specific path to the default path in the bashrc
file of your Ubuntu 20.04 system, you will have to perform the steps shown
below. In this method, we have intentionally skipped the first two steps of the
first method since they are the same for this method as well.

Step # 1: Make Changes to the “bashrc” File for Prepending a Path to the
Default Path:

You can access the bashrc file of your Ubuntu 20.04 system with the same
command that we stated in our first method. After accessing that file, just
scroll down to the bottom and add the following line to the end of that file:
export PATH=PathOfYourChoice:$PATH
Here, PathOfYourChoice will be replaced by the path that you wish to prepend to
the current path of your Ubuntu 20.04 system.

Step # 2: Reload the “bashrc” File:

Now, for allowing the new changes to take effect, you will have to execute the
command shown below:
$ source ~/.bashrc

This command will immediately load the modified bashrc file to your Ubuntu
20.04 system without displaying any output.

Step # 3: Recheck the Path of your Ubuntu 20.04 System:

Finally, you can recheck the current path of your system to assure that the new
path is prepended to the default path of your system. The new path of your
system can be rechecked with the same command that we used in the first method.
You can see from the results of this command shown in the following image that
the specified new path has been prepended to the default path of our Ubuntu
20.04 system.

Conclusion:

This article was based on the two methods of exporting a path in a bashrc file
on a Ubuntu 20.04 system. The first method was about appending the desired path
to the default path, whereas the second method was prepending the desired path
to the default path in the bashrc file on a Ubuntu 20.04 system. After changing
the value of the PATH variable on a Ubuntu 20.04 system, you will be able to
execute or access files within this modified path, which will be specified with
your PATH variable.


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
