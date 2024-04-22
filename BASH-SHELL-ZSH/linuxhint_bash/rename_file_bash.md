





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Rename a File in Bash

2 years ago
by Fahmida_Yesmin
Renaming a filename is a very common task for any operating system. Anyone can
easily rename a file by using the graphical user interface (GUI). You can also
rename a file by using a command in bash script. Many commands exist in Linux
to rename a filename. The command ‘mv’ is the most popular command for renaming
a file. There is another command called ‘rename’that can also be used for the
same task. However, this command is not installed on Ubuntu by default, so you
will have to install this command to rename a file. This article explains how
to use these two commands in bash to rename filenames.

Rename a File with ‘mv’ Command

The most commonly used command in Linux to rename a filename is the
‘mv’command. The syntax of this command is given below.
Syntax
mv [option] source destination
Using any option with the ‘mv’command is optional. To rename a file, you must
type the original filename after the renamed filename with this command.
Various uses of the‘mv’ command are explained in the next section of this
article.

Example 1: Rename a File with ‘mv’ Command without Options

The name of the original file and the name of the renamed file will be taken as
the input from the user in the following script. The file will be renamed if
the original filename exists. If any file with the renamed filename already
exists, then the old file will be overwritten by the content of the newly
renamed file.
#!/bin/bash

# Take the original filename
read -p "Enter the original filename to rename:" original
# Take the renamed filename
read -p "Enter the renamed filename to rename:" rename

# Check the original file exists or not
if [ -f $original ]; then
     # Rename the file
     $(mv $original $rename)
     echo "The file is renamed."
fi
Output

Example 2: Rename a File with ‘mv’ Command Using -i option

The problem of the above example can be solved by using the ‘-i’ option with
the ‘mv’ command.  The following script will ask for permission from the user
to overwrite before doing the renaming task. If the user press ‘n’ then the
rename task will not be done.
#!/bin/bash

# Take the original filename
read -p "Enter the original filename to rename:" original
# Take the renamed filename
read -p "Enter the rename filename to rename:" rename

# Check the original file exists or not
if [ -f $original ]; then
     # Check the rename filename exists or not
     if [ $(mv -i $original $rename) ]; then
        echo "The file is renamed."
     fi
fi
Output

Rename a File with ‘rename’ Command

The‘rename’ method is used for advanced file renaming tasks. Run the following
command in the terminal to install the ‘rename’command.
$ sudo apt install rename
The syntax of this command is given below.
Syntax
rename [option]  's/search/replace/' files
This command can be used with and without options, like the ‘mv‘ command.
Multiple files can be renamed at once by using a regular expression. Here, the
‘s’ indicates substitution. If the search text is found, then the files will be
renamed by the replacement text.

Example 3: Rename Files that Match with Regular Expression

The following script can be used to rename multiple files by using a regular
expression pattern that will take the extension of the searched filename and
the renamed filename as the inputs. If the current extension matches the search
text, then the extension of any file will be renamed by replacing the text.
#!/bin/bash

# Take the search text
read -p "Enter the search text:" search
# Take the replace text
read -p "Enter the replace text:" replace

# Rename all files that match with the pattern
$(rename "s/.$search/.$replace/" *)
echo "The files are renamed."
Output

Conclusion

This article used a number of examples to illustrate the use of the
‘mv’and‘rename’bash commands. Renaming a filename should be easier for bash
users after practicing the above examples.


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
