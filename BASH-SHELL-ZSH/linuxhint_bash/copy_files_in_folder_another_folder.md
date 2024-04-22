





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How can I Copy Files in a Folder into Another Folder on Linux Terminal

3 years ago
by Sidratul_Muntaha
When you’re in need of copying the contents of a directory into another, in the
case of Linux, there are plenty of tools at your disposal. Which one to use? It
depends on the situation and personal preference. In this article, we’ll have a
look at ways you can copy file contents from one folder to another in the
terminal. It’ll feature some of the popular choices for different situations.

File copying in terminal

Copying the content of one directory into another is a very simple task.
However, you have plenty of options of doing it. Linux is blessed with numerous
tools to manipulate files and directories through various actions.
All the steps are demonstrated on Ubuntu 18.04.1. At first, let’s create a
handful of dummy files to work with.
$ mkdir -v dir_A
Now, let’s create the dummy files using touch.
$ touch dummy{1..10}
Let’s create another folder within dir_A with a handful of dummy files.
$ mkdir -v dir_B
$ touch dummy{1..10}
Now, the entire structure of the directory dir_A looks like this.
$ tree dir_A

Cp Command

The cp command is, by far, the most common tool for copying files. It’s a tool
that comes by default with any Linux system. Copying files and directories are
the sole purpose of cp. It supports a wide range of features.
This is the basic structure of the cp command.
$ cp <options> <source> <destination>
For example, let’s make a copy of the dummy1 file with the name dummy1_copy.
$ cp dummy1 dummy1_copy
Now, let’s try copying multiple files at once. For such an operation, cp
requires the destination be a directory. Here, I’ll be using wildcard
expression to grab all the dummy files and put them into the ~/Downloads
directory.
$ cp dummy* ~/Downloads
How about copying a directory?
$ cp -vr dir_A dir_A_copy
Here, we used two different flags. Let’s have a quick breakdown of them.

* -r: Stands for a recursive copy (including any hidden file(s)). Must-have
  flag if copying involves an entire directory or more.
* -v: Stands for verbose. The cp tool will output every single action it’s
  performing.

Want to follow the symbolic links? Add the “-L” flag.
$ cp -Lvr <source> <destination>
Let’s say the destination directory already has a file with the same name. If
you want to avoid overwriting, use the “-n” flag. It’ll ensure that in case of
conflict, cp won’t overwrite the file.
$ cp -nv <source> <destination>
If you’re performing a sensitive copy/paste action, it’s better to have the
finest control over what happens, right? In such a case, use the “-i” flag. It
stands for an interactive mode where cp will ask for confirmation every time a
conflict arises.
$ cp -i <source> <destination>
If you’re more interested, the man page is always one of the best
documentation. Learn_more_about_cp.
$ man cp

mv command

The mv tool is similar to the cp tool. However, instead of copying, mv moves
files and directories. Compared to cp, it’s a simpler one.
The command structure of mv is similar to cp.
$ mv <option> <source> <destination>
To move the contents of dir_A to dir_A_copy, run the following command.
$ mv -v dir_A/ dir_A_copy
Here, the “-v” flag is for verbose mode. If you want to move just the contents
of dir_A, use the following one instead. In this case, the target directory
must exist beforehand.
$ mv -v dir_A/* dir_A_copy
The mv tool doesn’t have much to work with. For all the available options,
check out the man page.
$ man mv

Rsync Command

This is one of the most popular and powerful tools for file copying, used
mostly for backup. It holds the ability to copy files over a remote connection.
Unlike cp and mv, it also comes with a ton of advanced file copying options
that offer the utmost customization of its behavior.
Rsync is mostly famous for its delta-transfer algorithm that dramatically
reduces the amount of data that needs to be exchanged. In the case of remote
syncing, this saves up a lot of bandwidth.
Rsync doesn’t generally come pre-installed in any Linux distro. However,
because of its popularity, it’s now available on all the major Linux distros.
Use Pkgs.org to find out the rsync package for your distro. Assuming that you
got rsync installed, let’s get started.
First, the basic command structure of rsync. It’s quite similar to cp.
$ rsync <options> <source> <destination>
Before getting started, here are a handful of popular rsync arguments.

* -v: Verbose mode, outputs whatever action being performed on the console
  screen.
* -vv: Verbose mode with more details
* -r: Recursive mode, must be present if copying directories
* -z: Compress data
* -a: Archive data
* -n: Dry run, should be run in combination with verbose mode. Simply outputs
  the actions if the command was to run for real
* –delete: Delete the file(s) and directory(s) on the destination directory if
  the source directory doesn’t contain them any longer
* -no-whole-file: Forces rsync to use its delta transmission algorithm, no
  matter what. Useful in scenarios where you must ensure the least amount of
  data write.
* –remove-source-file: Delete source file(s) after copying.

Let’s check them out in action. First, the directory copy. Run the following
command.
$ rsync -vr dir_A/ dir_A_copy
For further detailed output, let’s use the “-vv” flag.
$ rsync -vv -r dir_A/ dir_A_copy
Now, let’s check out the cool part of rsync. We discussed how rsync
intelligently copies only the files that are modified, saving bandwidth and
disk write. It’s time to check it out in action. In this example, the action
will be performed within the dir_A directory.
$ rsync -vv --no-whole-file dummy* dir_B/
Despite delta-transmission enabled, rsync may not apply it when you’re
performing local data transfer.
Now, let’s check out the dry run feature. Before running any rsync command for
real, it’s always important that you test it out beforehand. This is where the
dry run comes in. Rsync will output what will happen if the command was to
actually run.
$ rsync -anvr dir_A/ dir_A_copy
Rsync can also work with remote directories, no problem. All it needs is a
proper SSH connection with SSH keys configured.
$ rsync <option> <local_dir>
<username>@<remote_host>:<destination_dir>
Want to perform a move operation? To put that in rsync’s perspective, rsync
will copy the contents of the source directory and then, delete the source
content.
$ rsync -v --remove-source-files <source> <destination>
Check out the result of the operation.
$ tree dir_A
$ tree dir_A_copy

Final thoughts

The cp and rsync are the most common tools you can use for copying files in a
folder on the Linux terminal. Both of them are also really good for scripting.
Just make sure to test the functions out before implementation.
Enjoy!


About the author


Sidratul Muntaha

Student of CSE. I love Linux and playing with tech and gadgets. I use both
Ubuntu and Linux Mint.
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
