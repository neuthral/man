





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Bash to Change the File Extension of Multiple Files in a Folder

1 year ago
by John_Otieno
This tutorial will discuss a quick way to use Bash to rename files from a
specific extension to another. We will use a bash loop, find, rename, and the
mv command for this one.

Method 1: Bash loop

The most common way to change file extensions recursively in a directory is to
use a bash for loop. We can prompt the user to enter the target directory, old
extension, and the new extension to rename using a bash script.
Step 1: Assemble the script
Let us begin assembling the script. The first part we need is to get the target
directory. For this, we can bash read as:
#!/bin/bash
echo "Enter the target directory "
read target_dir
cd $target_dir
 
echo "Enter the file extension to search without a dot"
read old_ext
 
echo "Enter the new file extension to rename to without a dot"
read new_ext
echo "$target_dir, $old_ext, $new_ext"
The script above will ask the user for the directory to process and then cd
into the set directory.
Next, we get the old extension without the dot (.); finally, we get the new
extension to rename the files.
Now let us get to processing the files. For this; we can implement a simple
rule that recursively searches the files as:
for file in *.$old_ext
do
    mv -v "$file" "${file%.$old_ext}.$new_ext"
done;
The for loop above will search the passed directory for all files with the old
extension and rename them to the new extension.
To get verbose, we use the mv command with -v. You can suppress this output by
replacing the -v flag with –
Step 2: Run the script
Now, let us put the script to the test. The final script is below:
#!/bin/bash
echo "Enter the target directory "
read target_dir
cd $target_dir
 
echo "Enter the file extension to search without a dot"
read old_ext
 
echo "Enter the new file extension to rename to without a dot"
read new_ext
 
echo "$target_dir, $old_ext, $new_ext"
 
for file in *.$old_ext
do
    mv -v "$file" "${file%.$old_ext}.$new_ext"
done;
In this test, we will use the /var/log directory and rename all the .log files
to .bak. Here are the contents of the directory before running the script.
$ ls l /var/log/ | grep .log
Now, let us run the script.
$ chmod +x extensions.sh
$ sudo ./extensions
The screenshot above shows the script processing the files and renaming all the
files with .log to .bak.
Since this is an interactive script, it comes in handy when you do not want to
hard code the extension.
The following is the contents of the /var/log directory after the script.
$ ls -l /var/log/ | grep .bak
To revert the changes, switch the old extension to .bak and the new extension
as .log

Method 2: Rename command

If you do not feel like working with a script, you can use the rename tool to
change the file extensions recursively.
To install rename, use the command:
$ sudo apt-get install rename -y
Once installed, you can use the rename command as:
# change to the target directory
cd /var/log/
# change extension
sudo rename 's/\.log/.bak/' *.log
To revert the changes, change the .bak to .log and vice versa.
$ sudo rename 's/\.bak/.log/' *.bak

Method 3: MMV command

You can also use the mmv command that allows you to move multiple files
simultaneously.  Install mmv with the command:
$ sudo apt-get install mmv
To rename files with mmv command:
$ cd /var/log/
mmv "*.csv" "#1.xls"
The #1 moves the files to the current directory. Once you run the command, it
will rename all .log files to the specified extension.

Summing Up

This article discussed various methods you can recursively rename file
extensions in a specific directory. However, it is good to note that you can
implement strategies other than those discussed in this guide.
Thank you for reading, and remember to share!


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
