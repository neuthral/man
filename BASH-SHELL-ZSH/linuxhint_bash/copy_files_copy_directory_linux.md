




















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Copying Files and Copying Directories on Linux

4 years ago
by Sidratul_Muntaha
Linux is a place that can do amazing things when performing almost any task.
For enjoying the full power of Linux, it’s always a good idea to have the
knowledge of some basic tricks and command, right? Today, let’s have a look at
the file copying command on Linux.


File copying

Before we start the guide, it’s time for a short note on what Linux understands
by telling a file or folder. In Linux, each and every folder is known as
“directory”. A directory can contain other directories and files of any size
given that the file size enough to fit in the storage device.
When you want to copy a file/folder, you have to clarify it enough to the
system so that it doesn’t mess things up. It’s also a wonderful thing that
whenever you copy/move file from one drive or another, you’ll still be putting
them into a folder!

Copying tricks

For copyping, we’ll be using “cp” command. This is the basic “cp” structure –
cp [parameter] “source_file_directory” “target_file_directory”
If you want to copy a file to another directory, you have to run the following
commands. Note that I’m using “~/Downloads/testDir/” with 3 test files as the
demo for this guide.
cd ~/Downloads/testDir
# Copy all the available files to “~/Desktop/testDir1” directory
cp * ~/Desktop/testDir1
Here, “cp” is the associated command for copying file from one directory to
another. It’s just a short term of “copy”. There are some other available
options like –

* -i – Interactive copy mode. If the program finds out any confliction (file
  already exists etc.), it will ask your action on the situation.
* -r – Recursive. This option will copy all the included files & directories to
  the destination. It will also preserve the tree structure of the source
  directory.
* -v – Verbose mode. This is useful if you want to get feedback that the copy
  task is ongoing well. For each question, there are 2 available answer – y
  (Yes) and n (No).

cp -v * ~/Desktop/testDir1/
It’s recommended that you use these parameters most of the time for the best
feedback during copying process.
cp -irv ~/Desktop/testDir1/

Copying an entire directory

Now, let’s think of a situation when you need to copy all your files and
directories (folders) into the destination directory. Maybe you’re thinking to
use the same trick as above, right?
Here is a test run of the command where I’m trying to copy all the files and
directories under “~/Downloads/” into a created subdirectory “sub/”. After
running this command –
cp * sub/
The result is this –
Horrific, right? Everything is alright and “cp” should have copied everything
into that directory. What’s the problem?
The answer we already discussed above. Remember the “cp” parameter “-r”? It
tells to perform the task recursively – copy all the sub-directories and files
from the source to destination.
Let’s fix it right away! Run the fixed command –
cp -vr * sub/
Now, everything looks just fine and working.
An interesting thing to note that the destination sub-directory will also be
copied within itself.
As you can see, everything of the “Downloads” directory including the “sub”
sub-directory is inside the “sub” directory.
Just like that, if you want to copy an entire directory to another directory,
use the “-r” parameter. For example, I’ll be copying “~/Downloads/” to “/
Desktop/testDir1/”.
cp -vr ~/Downloads/ ~/Desktop/testDir1/
Hopefully, your copying experience with Linux has improved enough. Enjoy!


About the author


Sidratul Muntaha

Student of CSE. I love Linux and playing with tech and gadgets. I use both
Ubuntu and Linux Mint.
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
