





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to replace multiple lines using the `sed` command

2 years ago
by Fahmida_Yesmin
Sometimes it requires to replace multiple lines of a file with any particular
character or text. Different commands exist in Linux to replace multiple lines
of a file. `sed` command is one of them to do this type of task. The full form
of `sed` is Steam Editor, and it is mainly used to read and convert the text in
different ways by using a regular expression. How this command can be used to
replace the multiple lines of a file in different ways are explained in this
tutorial.

Commonly used `sed` Cheat Sheet:

The most commonly used characters used in the `sed` command are explained in
the following table.

Character Purpose
a         It is used for appending content.
b         It is used for branching content.
c         It is used for changing content.
d         It is used for deleting a line of a file.
D         It is used to delete the first line of a file.
g         It used to copy from the holding text.
G         It is used to append from the holding text.
h         It is used to copy in the holding text.
H         It is used to append to the holding text.
i         It is used for insertion.
I         It is used to print the substitute line.
n         It is used to go to the next line.
N         It is used to append the next input line.
p         It is used to print.
P         It is used to print the first line.
q         It is used to quit.
Q         It is used to quit immediately.
r         It is used to read the file.
R         It is used to read the line from the file.
s         It is used to substitute.
t         It is used to test for substitution.
T         It is used to test for no substitution.
w         It is used to write to the file.
W         It is used to write a line to the file.
x         It is used to swap patterns and hold.
y         It is used to translate.
z         It is used to clear the line.
‘=’   It is used to print the line number.


Replace multiple lines by using the `sed` command from the terminal:

How the `sed` command can be used to replace the multiple lines from a file
from the terminal is shown in this part of this tutorial. Create a file named
sed.txt with the following content test the commands of this part.
sed.txt
The full form of sed is “stream editor”.
It is a Unix utility that is used to read and convert the text in a different
format.
It was developed by Lee E. McMahon.
It is used for text processing.
It supports regular expressions.

Example-1: Replace Two Consecutive Lines

The following `sed` command will replace two consecutive lines with another
line. Here, the -z option is used to replace the consecutive lines with null
data before adding the replacement text. According to the command, the 3rd and
4th lines of the file will be replaced by the text, ‘It is a very useful tool’.
$ cat sed.txt
$ sed -z 's/It was developed by Lee E. McMahon.\nIt is used for text
 processing./It is a very useful tool./' sed.txt
The following output will appear after running the commands.

Example-2: Replace multiple lines based on match and global flag

The following `sed` command will replace all lines that start with the word,
‘It’ by the word, ‘This line is replaced‘.
$ cat sed.txt
$ sed 's/^It.*/This line is replaced/g' sed.txt
The following output will appear after running the commands. Three lines
contain the word ‘It‘ in the file. So, these lines have been replaced by the
replacement text.

Example-3: Replace multiple lines based on the match and next-line command

The following `sed` command will replace the word,’is‘ by the word, ‘was‘ with
the next-line command, ‘n’.
$ cat sed.txt
$ sed ' {n;/is/ {s/is/was/}}' sed.txt
The following output will appear after running the commands. Here,‘is’ exists
in the 2nd and 4th lines of the file, and these lines are modified by the
word‘was’.

Replace multiple lines by creating the `sed` script file:

In the previous examples, `sed` commands have been executed from the terminal.
But it is a scripting language, and if the script contains multiple statements,
then it is better to create a sed file with the script. Create a text file
named students.txtwith the following content in which the `sed` script will be
applied.
students.txt
ID: 111045
Name: Robert
Department: CSE
Batch: 35

ID: 111876
Name: Joseph
Department: BBA
Batch: 27

ID: 111346
Name: William
Department: CSE
Batch: 45

ID: 111654
Name: Charles
Department: EEE
Batch: 41

ID: 111346
Name: John
Department: CSE
Batch: 25

ID: 111746
Name: Thomas
Department: CSE
Batch: 15

Example-4: Replace multiple lines of a file using `sed` script file

Create a sed file named to replace.sedwith the following content to replace the
multiple lines based on the search pattern. Here, the word ‘CSE‘ will be
searched in the text file, and if the match exists, then it will again search
the number 35 and 15. If the second match exists in the file, then it will be
replaced by the number 45.
replace.sed
/CSE/ {
    p;n;
    /35/ {
        s/35/45/;
        p;d;
          }
    /15/ {
        s/15/55/;
        p;d;
          }
}
p;
Run the following command to check the existing content of the file. ‘CSE’
appeared four times in the text file. 35 and 15 exist in two places.
$ cat students.txt
The following command will replace the content of the multiple lines based on
the sed script.
$ sed -n -f replace.sed students.txt
The following output will appear after running the command.

Conclusion

Different ways to replace multiple lines or the content of the multiple lines
using the `sed` command have been shown in this tutorial. How the `sed` script
can be executed from a sed file is also shown in this tutorial. I hope this
tutorial will help the reader to replace multiple lines of any file by using
the `sed` command.


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
