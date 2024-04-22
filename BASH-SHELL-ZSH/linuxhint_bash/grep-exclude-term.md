





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Grep Exclude Term

2 years ago
by Aqsa_Yasin
Global regular expression print is a versatile terminal-based utility. As the
name shows that it helps in searching the text within the file with the help of
regular expressions. Grep is firstly originated as a Unix utility to run on
that operating platform. After Linux configuration, it can access many
applications on this operating system. Most Grep functions are included in the
matching of the text of the file present in the command. Exclude function is
also as useful as matching any pattern and displaying it because it helps
remove the particular match from the file. It helps to exclude the word or
words from the lines in a file. We can get help from the man page in the system
by applying the below-appended command.
$ man grep
We have found two important keywords used in excluding terms in any file. –v is
used to invert the match; it then outputs the nonmatching lines in the text.

Prerequisite

To perform the functionality, we need to have Linux installed in our system
configured on the virtual machine. By adding a username and password,  you will
have access to applications in the operating system. You need a terminal to
open and run commands on it.
Exclude term (word)

Example 1

To apply this function to a word, we need to have a file existing in our
system. If you don’t have any files, then create them first. We have a file
named fileb.txt. We will use the cat command to display text.
$ cat fileb.txt
This image shows the output of the file.
If we want to exclude some words from the text, we will use the following
command to exclude the words in the fileb.txt
$ grep –I –v –E ‘ubuntu’ fileb.txt
In the command above, we have used –v that will invert the text in the query.
Ubuntu is the word we want to exclude from the given text. –I is for case
sensitivity and an optional thing that is if the desired output is to obtained
without using –i. “|” is used to exclude or match the accurate words. The
output of this command is to be appended below.
In this output, you have seen that “ubuntu” is removed from the file. To draw
another word, say Linux, from the file, we can amend the given command.
$ grep –I –v –E ‘Ubuntu|Linux’ fileb.txt
In this way, at a time together, more than one word will be excluded.

Example 2

In this example, the whole string is removed from the file. The target word is
mentioned in the command, and the command works in such a way that word is
matched with the text in a string, and in this way, the whole string is removed
from the file. Syntax of command is the same as described above in this guide.
Let us have a file named file22.txt. Firstly, we will display all of the
contents so that the respective result will show the difference.
$ Cat file22.txt
Now we will apply the command to exclude the whole string from the file.
$ grep –v ‘technical’ file22.txt
The command will be applied in such a way that it will match the target word
and will display all the strings except the one that contains the match. Now
you can see that the first string is not present in the text file.

Exclude Term of Multiple Words

Unlike the examples above, here we will mention more than one command to
exclude them from the text file. Cat and Grep both act in the same way. Now
with the help of the given command, we will understand this concept.
$ cat file20.txt | grep –v –e “good” –e “years”

$ grep –v –e “good” –e “years” file20.txt
In this command, –e is used for more than one term as an input in the command.
It will eliminate both words from the text. The first command implies the file
to be displayed and then remove the words we want to exclude. Simultaneously,
the second command will use –v first to remove the words written further in the
command.
Here is another way of exclusion. Firstly, we exclude one word by providing a
file address, and after “|” we will introduce the second word.
$ grep –v “years” file20.txt  | grep “good”

Exclude File

Like words, we can also exclude the file from the system. We will use the
following command.
$ grep – exclude “file21.txt” grep *.txt
This command will remove the file. This command will use the “—exclude” keyword
to remove the file. “*.txt” implies that the file is a “txt” extension. Command
will work on all the text files to search the relevant file that is present in
the system.

Exclude Directory with Word

The directory can also be excluded by defining a word. This command will help
to match the word present in any text file of a directory and then remove the
respective directory or directories having that word in it. Here,  we don’t
mention the file name in the command.
$ grep - -exclude-dir “good” –R “grep”
“dir” represents the directory in the system. –R shows the recursive function.
To do any alteration in directories, we always use –R.
We will quote another example that shows that directories that contain the word
“Aqsa” are removed from the system.
$ grep - -exclude-dir “directory” –R “aqsa”
It will show all directories, including the word Aqsa.

Exclude word with Help of Directory

As we have excluded the directory by using the word, we can also exclude the
word using the directory or provide the whole path of the file.
$ grep –R “years” /home/aqsayasin/file20.txt/ | grep –v “exclude this”
In this command, we want to exclude the word year. To introduce the directory,
we will write –R. Consider file20.txt as below.
Now apply the following command by using the directory as input.
The output obtained from this command will exclude the word year from the
output.
Moving towards another example. Here, we will exclude the word “grep” from the
directory using the following appended command.
$ grep –RI “grep”

Conclusion

Excluding term is an alternative to the matching process of Grep. It helps in
removing unwanted words or strings from the files present in the system. This
article will assist you in getting rid of unwanted words.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
