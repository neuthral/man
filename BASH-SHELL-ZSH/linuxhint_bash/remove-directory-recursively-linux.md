





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Remove Directory Recursively without Prompting for Confirmation in Linux

2 years ago
by Aqsa_Yasin
At times, you may have more than one directory within a single directory. This
is known as a subdirectory, defined as a directory within a directory. Usually,
the subdirectories within a directory are closely related to that directory.
This means that whenever you feel like you do not need a particular directory
anymore, then you also will not need its subdirectories further. So, the
question arises, “How do I get rid of all the files and directories within a
directory?”
This is where the concept of recursive deletion comes into play. Recursive
deletion aims to delete all the files and directories within a subdirectory.
Generally, whenever you attempt to delete any file or a directory within any
operating system, the OS prompts you to provide confirmation to prevent
accidental deletion of important files or directories. However, if you are 100%
sure of what you are going to delete, and there is a large number of files to
be deleted, then you might find it troublesome to provide confirmation for
every file or directory.
In this case, you can remove a directory recursively without being prompted by
the OS for confirmation every time. This article explains how to remove a
directory recursively without prompting the user for confirmation in Linux Mint
20.
To remove a directory recursively in Linux Mint 20 without prompting the user
for confirmation, the following series of steps should be performed.

Step 1: List Contents of Directories

We have created two sample directories, namely, Directory1 and Directory2, in
our Home directory to demonstrate this method of removing directories
recursively in Linux Mint 20. Directory1 contains two subdirectories, named D1
and D2, whereas Directory2 contains the file named D5. We will show you the
contents of our Home directory so that you can verify that Directory1 and
Directory2 exist in our Home directory. To list the contents of the Home
directory, we will run the following command in our terminal:
$ ls
You can see from the output of this command that Directory1 and Directory2
exist in our Home directory, as highlighted in the image below. We performed
this step so that you can easily verify the deletion performed in Step 4 of
this method.
Next, we will show you the contents of our Directory1 by running the following
command in the terminal:
$ ls /home/aqsa_yasin/Directory1
Here, you can give the path of any directory of which the contents you would
like listed.
The contents of Directory1 are shown in the image below:
Finally, we will show you the contents of our Directory2 by running the
following command in the terminal:
$ ls /home/aqsa_yasin/Directory2
Here, you can give the path of any directory of which the contents you would
like listed.
The contents of Directory2 are shown in the image below:

Step 2: Remove a Single Directory Recursively without Prompting the User for
Confirmation

To remove a single directory recursively without prompting the user for
confirmation, run the following command in your terminal:
$ rm –rf PathOfTheDirectoryToBeDeleted
Here, replace “PathOfTheDirectoryToBeDeleted” with the exact path of the
directory that you intend to delete. In our case, the directory is /home/
aqsa_yasin/Directory1. The “-rf” flag, along with the “rm” command, removes a
directory recursively without prompting the user for confirmation.

Step 3: Remove Multiple Directories Recursively without Prompting the User for
Confirmation

If you wish to remove multiple directories recursively at a time without
prompting the user for confirmation, then skip Step 2 and, instead, run the
following command in your terminal:
$ rm –rf Path1 Path2 …..
Here, replace “Path1” and “Path2” with the exact paths of the directories that
you intend to delete. In our case, we only wanted to delete two directories,
i.e., Directory1 and Directory2. However, you can remove as many directories as
you want using this command simply by stating the paths of the directories,
separated by spaces, following the “rm –rf” command.

Step 4: Verify Deletion of Specified Directories

After executing the command in Step 3, ideally, our Directory1 and Directory2
should be removed, along with all their subdirectories, from our Home
directory. We can always confirm whether the deletion process has successfully
taken place by listing down the contents of our Home directory. We can do so by
running the following command in the terminal:
$ ls
This time, in the output of this command, we will no longer be able to see
Directory1 and Directory2 in the Home directory, as shown in the image below.
This indicates that the specified directories have been removed successfully.

Conclusion

By using the method prescribed in this article, you can remove a single
directory or multiple directories recursively without prompting the user for
confirmation in Linux Mint 20. With this method, you can get rid of all the
traces of a directory at once, including all the subdirectories and files
within it, without constantly needing the user to provide consent. In this way,
you can easily and quickly free up your system’s storage space for more
important files and directories. I hope that, by following this article, you
are now in the position to delete directories recursively without prompting the
user for confirmation.


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
