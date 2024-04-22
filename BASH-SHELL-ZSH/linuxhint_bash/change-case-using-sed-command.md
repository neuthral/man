





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to change case using sed command

1 year ago
by Adnan_Shabbir
In this descriptive guide, we have listed down the ways to change the case of
letters in a text file using sed command. There are two categories of cases
while dealing with the alphabetical letters, i.e., one is lower case and the
second is upper case (capital letters), so we will describe both ways in this
guide:

How to change the letters from upper case to lower case using sed command

In this part of writing, we will explain the use of sed command to change the
letters from upper case to lower case in Ubuntu terminal:
Let’s start from the very basic use of sed command to change all letters from
uppercase to lower case in a text file: we have a text file “upper.txt” and the
content of the file shows that there is no lower-case letter in the file as can
be seen below:
$ cat upper.txt
To change it, the command written below will change all its letters from upper
case to lower case:
Note: It is a case sensitive action so while switching from upper case to lower
case, you must write capital letter [A-Z].; otherwise, this command won’t work:
$ sed 's/[A-Z]/\L&/g' upper.txt
And if you want to change only few letters from upper to lower case then you
have to specify the letters separated by comma “,”: For instance, the command
stated below will change only, “S”, “D” and “U” letters to lower case.
$ sed 's/[S,D,U]/\L&/g' upper.txt

How to change the letters from lower case to upper case using sed command

To change the case of letters from lower to upper, there is a slight difference
between commands; We created a text file “lower.txt” that will be used in this
section and the content of this file is displayed below:
$ cat lower.txt
For instance, the command written below will change all the lower-case letters
to upper case letter in a text file:
$ sed 's/[a-z]/\U&/g' lower.txt
Moreover, you have the option to capitalize few letters instead of changing the
whole document; For example, the command written below will capitalize the
letters “L”, “D”, and “F” in text file “lower.txt”;
$ sed 's/[L,D,F]/\U&/g' lower.txt
Apart from these fundamental operations about upper case and lower case; sed
command also allows you to capitalize only the first letter of each word in a
document; this functionality can be very useful for employee record management.
For instance, you have a list of first names and last names of your 500
employees; this sed command would help you in this regard to change the first
letter of their names to capital. The syntax of the command is written below:
Syntax

sed [options] 's/\b\(.\)/\u\1/g' [file name]
The command mentioned below shows the application of above stated syntax: For
instance, we have a list of three names; each name consists of two words and we
want to capitalize first letter of each word then:
The image below shows that firstly all the letters were in lower case, however,
once the command is executed the first letter of each name was capitalized:
$ sed 's/\b\(.\)/\u\1/g' names.txt

Conclusion

Linux Operating System is well known for its command line support and the
distros of Linux also have the same reason of popularity. One of the most
famous distro Ubuntu contains a large pool of command line utilities to
automate several tasks, such as sed command is used widely to perform several
actions on text files using terminal. The sed utility can be launched in
terminal and used to edit text files with one line operation that will be
applied on the whole file. Following the importance of this command, we have
compiled this guide to demonstrate the ways of using sed command to change the
case of letters in a text file and discussed the conversions of Upper to Lower
case and vice versa.


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
