





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Loop Through Directories Recursively

1 year ago
by John_Otieno
The Bash shell is an incredible tool that offers a lot of terminal ease and
functionality. This quick tutorial shall discuss various ways to loop through
directories and perform certain functions recursively.

The Bash for loop

To achieve a recursive loop through directories, we will use bash loops,
specifically, a for a loop.
The for loop is a common type of loop in Bash and other programming languages.
It iterates over a given list of items/options until and executes a set of
commands.
The general syntax for the for loop command is:
for i in list
do
    [COMMAND]
done;
Here is an example of a bash loop is:
#/bin/bash
for i in {0..10}
do
    echo ‘$’
done
The above loop prints values from 0 to 10.

Bash User input

Next, we need to prompt the user for a valid directory to loop through. To
accept user input, we use the echo command in Bash.
For example:
#!/bin/bash
echo “Enter the directory”
read dir
cd $dir
echo “Now in /etc”

Move Files (Bash Script)

With the concepts of loops and user input out of the way, we can put our shell
together. The first operation is to find files recursively with specific
extensions and move them.
Here is a sample script for that:
#/bin/bash
echo “Enter dir”
read dir
 
echo “Enter destination”
read dest
 
for i in $(find $dir -name '*.log');
do
    mv -v $i $dest
done;
The script will ask the user for a directory and then search for a specific
extension. It will then move the files to the specified destination.

Delete files

The script above can also be modified to delete files instead of moving them.
An example is as
#/bin/bash
echo "Enter dir"
read dir
for i in $(find $dir -name '*.log');
do
    rm -rf $i
done;

Print Files

To print the files in a directory, use the script as:
#/bin/bash
echo “Enter dir”
read dir
 
cd $dir
 
for i in $(find $dir -type f);
do
    echo $i;
done;

Conclusion

The above are example scripts you can use to loop directories and perform a
specific action. It is good to note there are tools developed to perform such
tasks, but a script is a good way to go if you can’t find an appropriate tool.


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
