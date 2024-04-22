





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to remove special characters using sed

1 year ago
by Adnan_Shabbir
Sed command is a Linux utility that can be used to perform lot of operations
that includes insert and delete operations, find/search and replace operations.
The sed command allows Linux users to edit and apply several functions on files
without opening them directly. The sed command support editing functionalities
that vary from beginners’ level to advanced level: For instance, inside a text
file these operations can be performed on several datatypes: characters,
numeric, special characters, alphanumeric et.,
Keeping in view the importance of sed command; our today’s guide will explore
several ways to remove special characters using sed command in Ubuntu.
The syntax of sed command is written below:
Syntax
sed [options] command [file name]
Special characters may sometimes be a need of the content that is written in a
text file but if they are used unnecessarily, they will make the file messy and
there are chances the reader may not pay attention, thus resulting in a
purposeless document.

How to use sed to remove special characters in Ubuntu

This section will briefly describe the ways to remove special characters from a
text file using sed; it depends on number of characters in your file that you
want to remove; there can be two possibilities while removing the characters
from a file, either you want to remove a single special character, or you want
to remove multiple characters at once. From these possibilities indicated
above, we have extended this section to two methods that will address both
possibilities:

Method 1: How to remove a single character using sedMethod 2: How to remove
multiple characters at once using sed

The first method addresses the first possibility, and the second possibility
will be discussed in Method 2, let’s dig into them one by one:

Method 1: How to remove a single special character using sed

We have created a text file “ch.txt” that contains few special characters on
different lines; the content inside the file is displayed below:
$ cat ch.txt
You can notice that the content inside “ch.txt” is difficult to read; For
instance, we want to remove character “#” from the text file; for this, we have
to use the following command to remove “#” from the whole document:
$ sed ‘s/\#//g’ ch.txt
Moreover, if you want to remove the special character from specific line; for
that, you must insert the line number alongside “s” keyword as the below
mentioned command will remove “#” from line number 3 only:
$ sed ‘3s/\#//g’ ch.txt

Method 2: How to remove multiple characters at once using sed

Now we have another file “file.txt” that contains more than one type of
character and we want to remove them in a single go. in this method the syntax
is changed little bit from above command; For example, we have to remove five
characters “#$%*@” from “file.txt”;
Firstly, look at the content of “file.txt” as the words are interrupted by
these characters;
$ cat file.txt
the command stated below will assist to remove all these special characters
from “file.txt”:
$ sed ‘s/[#$%*@]//g’ file.txt
Here we can draw another example, let’s say we want to remove only a few
characters from specific lines.
We have created a new file and the content of the “newfile.txt” is shown below:
$ cat newfile.txt
For this, we have written command that will delete “#@” and “%*” from lines 2
and 3 of “newfile.txt” respectively.
$ sed ‘2s/[#@]//g; 3s/[%*]//g’ newfile.txt
The sed command used in above methods will display the result only on the
terminal rather than applying the changes in the text file: for that, we must
use the “-i” option of sed command. It can be used with any sed command and the
changes will be made to the file instead of printing on the terminal.

Conclusion

Apparently, the sed command acts as a usual text editor but it has a far more
extensive list of actions as compared to other editors. You have to just write
a command and the changes will be made automatically; this feature attracts the
Linux enthusiasts or the users who prefer terminal over GUI. Following the
advantageous functionalities of sed; our guide is focused on removing special
characters from the text file. If we compare only this feature of sed command
with other editors, you have to search for characters throughout the file and
then removing them one by one is a tedious process. On the other hand, sed
performs the same action by writing a single line command on terminal.


About the author


Adnan Shabbir

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
