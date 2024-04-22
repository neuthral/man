





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to delete a file in bash

2 years ago
by Fahmida_Yesmin
Any file can be deleted temporarily and permanently in bash. When a file is
removed temporarily by using a graphical user interface, then it is stored in
the Trash folder, and it can be restored if required. The file which is removed
permanently cannot be restored later normally. `rm`command is used to remove
the file permanently from the computer. If any file is removed accidentally by
this command, then it can be restored from the backup. How any file can be
removed from the terminal and the graphical user interface are shown in this
article.

Delete the file using `rm` command:

`rm` command can be used with option and without the option for the different
types of delete. The syntax of the `rm` command is given below.

Syntax:

rm [option] filename
‘-i’ option can be used with `rm`command to provide a prompt before deleting
any file to prevent accidental deletion. ‘-f’ option can be used with `rm`
command to remove any file forcefully. The different uses of the `rm` command
are shown below.

Example-1: Delete the file using `rm` command without the option

You can apply the ‘rm’ command to remove an existing file. In the following
script, an empty file is created by using the ‘touch’ command to test ‘rm‘
command. Next, ‘rm’ command is used to remove the file, test.txt.
#!/bin/bash

# Set the filename
filename='test.txt'
# Create an empty file
touch $filename
# Check the file is exists or not
if [ -f $filename ]; then
   rm test.txt
   echo "$filename is removed"
fi
Output:

Example-2: Delete the file using `rm` command with -i option

The following script will ask for permission from the user before removing the
file for ‘-i’ option. Here, the filename will be taken from the user as input.
If the file exists and the user press ‘n’ then the file will not remove
otherwise the file will remove.
#!/bin/bash

# Take the filename
read -p 'Enter the filename to delete: ' filename

# Check the file is exists or not
if [ -f $filename ]; then
   # Remove  the file with permission
   rm -i "$filename"
   # Check the file is removed or not
   if [ -f $filename ]; then
      echo "$filename is not removed"
   else
      echo "$filename is removed"
   fi
else
   echo "File does not exist"
fi
Output:

Example-3: Delete the file using `rm` command with -v option

The following script will take the filename by a command-line argument. If the
file exists then, it will print a remove message with the filename for ‘-v’
option.
#!/bin/bash

# Check the file is exists or not
if [[ $1 != "" && -f $1 ]]; then
   # Print remove message
   rm -v $1
else
   echo "Filename is not provided or filename does not exist"
fi
Output:

Example-4: Delete multiple files using `rm` command

More than one file can be deleted by using ‘rm’ command and separating the
filenames with space. In the following script, multiple filenames will be taken
from the command line arguments. If any file does not exist, then it will show
a message otherwise filenames will be combined by the space and stored into the
variable named ‘files’. Next, the rm command will be executed with the ‘files’
variable to remove multiple files.
#!/bin/bash

files=""
space=" "

# Check the multiple filenames are given or not
if [ $# > 2 ]; then
    # Reading argument values using loop
    for argval in "[email protected]"
    do
      if [ -f $argval ]; then
             files+=$argval$space
          else
             echo "$argval does not exist"
          fi
    done

   # Remove files
   rm  $files
   echo "files are removed."
else
   echo "Filenames are not provided, or filename does not exist"
fi
Output:

Conclusion:

The above examples show the different types of ways to delete the file using a
bash script to help bash users to do this type of task easily.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
