




















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Globbing Tutorial

4 years ago
by Fahmida_Yesmin
Bash does not support native regular expressions like some other standard
programming languages. The Bash shell feature that is used for matching or
expanding specific types of patterns is called globbing. Globbing is mainly
used to match filenames or searching for content in a file. Globbing uses
wildcard characters to create the pattern. The most common wildcard characters
that are used for creating globbing patterns are described below.






Question mark – (?)

‘?’ is used to match any single character. You can use ‘?’ for multiple times
for matching multiple characters.
Example-1:
Suppose, you want to search those text filenames whose names are 4 characters
long and extension is .txt. You can apply globbing pattern by using ‘?’ four
times to do this task.
Find out the list of all files and folder of the current directory.
$ ls –l
Run the following command search those files whose names are four characters
long and unknown.
$ ls -l ????.txt
Example-2:
Suppose, you want to search those document files whose names are 8 characters
long, first 4 characters are f, o, o and t and extension is doc. Run the
following command with globbing pattern to search the files.
$ ls -l foot????.doc
Example-3:
Suppose, you know the filename is ‘best’ and extension is 3 characters long,
but don’t know the extension. Run the following command by using ‘?’ to search
all files with the name ‘test’ having any extension of three characters long.
$ ls -l best.???

Asterisk – (*)

‘*’ is used to match zero or more characters. If you have less information to
search any file or information then you can use ‘*’ in globbing pattern.
Example -1:
Suppose, you want to search all files of ‘pl’ extension. Run the following
command using ‘*’to do that task.
$ ls -l *.pl
Example-2:
Suppose, you know the starting character of the filename only which is ‘a’. Run
the following command using ‘*’ to search all files of the current directory
whose names are started with ‘a’.
$ ls -l a*.*
Example-3:
You can apply ‘*’ in bash script for various purposes without searching files.
Create a bash file named ‘check.sh’ with the following script. Here, when the
user will type ‘y’ or ‘Y’ or ‘yes’ or ‘Yes’ then ‘confirmed’ will print and
when the type will type ‘n’ or ‘N’ or ‘no’ or ‘No’ then  ‘Not confirmed’ will
print.
#!/bin/bash
echo "Do you want to confirm?"
read answer
case $answer in
[Yy]* )  echo "confirmed.";;
[Nn]* )  echo "Not confirmed.";;
*) echo "Try again.";;
esac
Run the script.
$ bash check.sh

Square Bracket – ([])

‘[]’ is used to match the character from the range. Some of the mostly used
range declarations are mentioned below.
All uppercase alphabets are defined by the range as, [:upper:] or [A-Z] .
All lowercase alphabets are defined by the range as, [:lower:] or [a-z].
All numeric digits are defined by the range as, [:digit:] or [0-9].
All uppercase and lower alphabets are defined by the range as, [:alpha:] or [a-
zA-z].
All uppercase alphabets, lowercase alphabet and digits are defined by the range
as, [:alnum:] or [a-zA-Z0-9]
Example -1:
Run the following command to search all files and folders whose name contains p
or q or ror s.
$ ls -l [p-s]*
Example-2:
Run the following command to search all files and folders whose name starts
with any digit from 1 to 5.
$ ls -l [1-5]*

Caret – (^)

You can use ‘^’ with square bracket to define globbing pattern more
specifically. ‘^’ can be used inside or outside of square bracket. ‘^’ is used
outside the square bracket to search those contents of the file that starts
with a given range of characters. ‘^’ is used inside the square bracket to show
all content of the file by highlighting the lines start with a given range of
characters . You can use different types of globbing patterns for searching
particular content from a file. ‘grep’ command is used for content searching in
bash. Suppose, you have a text file named ‘list.txt’with the following content.
Test the following examples for that file.
Apple
4000
Banana
700
Orange
850
Pear
9000
Jackdruit
Example – 1:
Run the following command to search those lines from list.txt file that starts
with P or Q or R.
$ grep '^[P-R]' list.txt
Example – 2:
Run the following command to highlight those lines from list.txt file that
starts with A or B or C.
$ grep '[^A-C]' list.txt

Exclamatory Sign – (!)

You can use ‘!’ inside the range pattern. It works same as the use of ‘^’
symbol outside the range pattern. Some examples of using ‘!’ sign are given
below.
Example – 1:
Run the following command to show those lines from list.txt file that starts
with ‘P’ or Q or R.
$ grep [!P-R] list.txt
Example – 2:
Run the following command to show those lines from list.txt file that starts
with any digit from 4 to 8.
$ grep [!4-8] list.txt

Dollar Sign – ($)

‘$’ is used to define the ending character. If you know want to search
information based on last character then you can use ‘$’ in globbing pattern.
Example – 1:
Run the following command to search those lines from list.txt file that ends
with ‘a’.
$ grep a$ list.txt
Example – 2:
Run the following command to search those lines from list.txt file that end
with the number 50.
$ grep 50$ list.txt

Curly bracket – ({})

‘{}’ can be used to match filenames with more than one globbing patterns. Each
pattern is separated by ‘,’ in curly bracket without any space. Some examples
are given below.
Example – 1:
Run the following command to search those files whose names are 5 characters
long and the extension is ‘sh’ or the last two characters of the files are ‘st’
and the extension is ‘txt’.
$ ls -l {?????.sh,*st.txt}
Example – 2:
Run the following command to delete all files whose extensions are ‘doc’ or
‘docx’.
$ rm {*.doc,*.docx}

Pipe– ( | )

‘|’ sign is also used for applying more than one condition on globbing pattern.
Each pattern is separated by ‘|’ symbol in the command.
Example – 1:
Run the following command to search those filenames which are starting with
character ‘a’ and has the extension ‘bash’ or ‘sh’.
$ ls a*+(.bash|.sh)
Example – 2:
Create a bash file named ‘menu.bash’ and add the following script. If the user
type 1 or S then it will print “Searching text”. If the user type 2 or R then
it will print “Replacing text”. If the user type 3 or D then it will print
“Deleting text”. It will print “Try again” for any other input.
#!/bin/bash
echo "Select any option from the menu:"
read answer
case $answer in
1 | S )  echo "Searching text";;
2 | R )  echo "Replacing text";;
3 | D )  echo "Deleting text";;
*) echo "Try again.";;
esac
Run the script.
$ bash menu.bash

CONCLUSION

Some of the most commonly used globbing patterns are explained in this tutorial
by using very simple examples. I hope after practicing the above examples, the
concept of globbing will be clear to you and you will be able to apply it in
bash commands and scripts successfully.
For more info check this video:


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
