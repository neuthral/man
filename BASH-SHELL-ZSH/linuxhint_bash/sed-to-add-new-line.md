





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Sed to Add a New Line at the End of Each Line

1 year ago
by Adnan_Shabbir
The sed stands for stream editor that is used for basic editing operations on a
text that comes from a file or on an input that is directly passed to sed from
another command. Like its inputting criteria, sed can process an input file and
give output to another program (as it takes input from other programs
directly). It can be used to track the same word that is used in a document in
different ways and the users can set them for better understanding. As the
foundation of sed is based on a text editor but it can be used to write complex
scripts also. However, the primary operations that a sed command can perform
are listed below:

* To print the line
* Find and replace the words in a line or in a text file
* Delete the line that contains a specific word
* Append the line/text after any line (by specifying the line number) 
* Add a line before starting each line or before any specific line

The sed command utility of Ubuntu has multiple operations to perform; our
today’s guide will focus on appending the text at the end of each line in any
text file.
So, before getting an insight into this tutorial, let’s understand the basic
syntax of sed command:

Syntax

sed [options] command [file to edit]
The options in sed command are used to get the output in several formats; for
instance, the “-i” option is used to save the changes (caused by sed command)
to the original file. The “command” portion of this syntax contains the basic
operation of the sed command that you want to do using this command (edit,
delete or print the line). Lastly, the “file to edit” consists of the name of
the file on which the sed command is being applied.

How to install sed on Ubuntu

In most of the Linux distributions, sed comes with a built-in access; you can
get the version of sed to check whether it is available on your system or not;
write the following command in terminal to verify the existence of sed on your
Ubuntu:
$ sed --version
In case the sed is not available on your Ubuntu; you can install it using
package manager by executing the command mentioned below:
$ sudo apt install sed

How to append new line to the end of each line

As the operation will be performed on a specific text file; so, you must create
a text file and add some text to it, or you can apply sed on any existing text
file too (make sure that the file does not contain any important information
otherwise you may lose the information while testing):
We have created a text file “test.txt” on our desktop (you can use any
directory) and added a few lines of text to it. Let’s get the content of
“test.txt” on the terminal using the command written below:
$ cat test.txt
Now, we will use sed command to append a line “You are working in terminal of
Ubuntu” to each line in the file “test.txt”; so, the below-mentioned command
will help to perform this action:
It is to notice that “a” keyword is used here to append the text written after
it to each line of the file “test.txt”:
$ sed ‘a You are working in terminal of Ubuntu’ test.txt
You will observe that the result is printed on the terminal, but the original
file “test.txt” remains unchanged; if you want the changes in the original file
too; you must use the “-i” option as we have done it using the command below:
$ sed -i ‘a You are working in terminal of Ubuntu’ test.txt
Apart from appending to each line, the sed command gives you the option to
append text to any specific line; for, instance the following command will
append the text to only line#3 and the changes will be made to the original
file too:
$ sed ‘3a sed is a multipurpose command line utility’ test.txt
One can also save the result of any sed command to another file; for example,
the below-mentioned command will save the result in the new text file
“output.txt”.
$ sed '3a sed is a multipurpose command line utility' test.txt > output.txt

Conclusion

The sed is a command-line utility known as stream editor and it can perform
some basic operations on file such as searching, replacing, inserting, or
deleting. Apart from these basic operations, it can also be used for complex
scripting: therefore, it is said that the novice user may hesitate to learn
this. In fact, sed command is easy to learn and implement at a basic level and
the new users must try this to perform the above-mentioned operations. Knowing
the importance of sed, we have compiled this guide to demonstrate the ways of
appending new line or words at the end of each line. Moreover, users can also
perform this task on a specific line number by mentioning the number in the
command.


About the author


Adnan Shabbir

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
