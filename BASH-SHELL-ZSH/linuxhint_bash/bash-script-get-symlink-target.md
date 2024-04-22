





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Script to Get Symlink Target

1 year ago
by John_Otieno
We are all familiar with symbolic links in Linux. Commonly known as symlinks or
soft links, a symbolic link is a particular file that points to another file or
directory within any Filesystem.
In this short tutorial, we will go over the basics of symbolic links in Linux
and create a simple bash script to get the target of the symbolic link.

Types of Symbolic Links

There are mainly two types of symbolic links, namely:
Hard Links:
Hard links are direct pointers to a file or directory within a filesystem. Hard
links are creatable only in the same filesystem as the target file.
Soft Links:
On the other hand, Soft links are indirect shortcuts to a file or directory and
can exist anywhere within a filesystem. Soft links can point to file in a
different filesystem.

How to Create Symbolic Links

To create a symbolic link in Linux, we use the ln command. Executing the
command with no options creates a hard link to the specified target file.
The general syntax for the ln command is:
ln [OPTIONS] <target file/directory> <path to link>
As mentioned, the above command will create a hard link to the target file. To
create a soft symbolic link, use the -s option as:
ln -s [OPTION] <target file/dir> <path to soft link>

Example #1

Let us take the file auth.log in /var/log. We can create a link to the file in
our home directory using the command as:
ln -s /var/log/auth.log auth.log
The above command will create a link pointing to the main file. We can verify
this by using the ls command:
ls -la

Example #2

You can also perform a similar operation on a directory. To create a link to /
var/log, we use the command:
ln -s /var/log log
Similarly, a soft link is created pointing to the target /var/log directory:
ls -la

How to Remove Symbolic Links

To remove a symbolic link, we use the command unlink followed by the path to
the symbolic link to remove.
For example:
unlink ~/log
NOTE: If you delete the target file or directory, remove the symbolic link
because leaving it creates a broken link.

How to Get Symbolic Link Target File or Directory

Every symbolic link points to a target file or directory (unless broken). To
fetch the target file/directory of a symlink, we use this command that shows
the target of a symlink.
For example, to get the target of the auth.log file we created in an earlier
section, we can do:
readlink auth.log

/val/log/auth.log

A Simple Bash Script to Get Symlinks

Using the concepts above, we can assemble a simple bash script that accepts a
path and lists all the symlinks and their target files or directory.
A simple script such as the one provided below should do the trick.
#!/bin/bash
echo "Provide the directory to evaluate:"
read target_dir
cd $target_dir
links=$(find . -maxdepth1 -type l -ls | awk '{print $11}')
for link in links
do
    echo "$link -> $(readlink $link)"
done
The script starts by asking the user for the directory to evaluate. Then, the
script goes to the provided directory and finds all the symbolic links inside
the directory, and passes the output to awk.
Awk parses the output and locates only the symbolic links, and saves them to a
variable called links.
We then create a loop that grabs each link in the links and evaluates their
target value using the readlink command.
Finally, we echo the symbolic link and the target directory. Below is an
example output:
In the above example, we find all the symlinks in the /etc directory and print
their target file or directory.

Conclusion

In this tutorial, we discussed the basics of using symbolic links in Linux. We
then created a simple script to find symbolic links in a specified directory
and show their source and target.
Thank you for reading!


About the author


John Otieno

My name is John and am a fellow geek like you. I am passionate about all things
computers from Hardware, Operating systems to Programming. My dream is to share
my knowledge with the world and help out fellow geeks. Follow my content by
subscribing to LinuxHint mailing list
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
