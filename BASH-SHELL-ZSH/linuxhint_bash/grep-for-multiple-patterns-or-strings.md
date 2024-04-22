





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Grep for Multiple Patterns or Strings

2 years ago
by Aqsa_Yasin
Global Regular Expression Print or Grep is a powerful utility used in Linux
operating system. Through grep, you can search from files with different
patterns or strings by applying limitations. Grep function takes one or more
input files to search in directories or sub-directories. To search for numerous
patterns, we use OR operator. This operator is used to separate the patterns
written in the command. The alteration operator “|” is used with the backslash.
The syntax for searching different regular expression is as follow:

Syntax

$ grep ‘pattern1\|pattern2’ filename
A regular expression is always written in a single quotation. Two names are
separated with backslash and alteration operator. The command is ended with the
filename. While doing grep recursive, directory or whole path is used instead
of a single file name.

Prerequisite

In this article, we will learn the functionality of grep in searching multiple
patterns and strings. For this purpose, you need to have Linux operating system
running on your virtual box. You need to install it on your system. After
configuration, you will have access to use all applications. After logging in
to the user by providing a password, go to the terminal shell command-line to
proceed.

Search by Multiple Patterns in a File Using Grep

If we want to search multiple patterns or strings in a particular file, use the
grep functionality to sort within a file with the help of more than one input
word in the command. We use ‘\|’ operators for the separation of two patterns
in a command.
$ grep ‘technical\|job’ filea.txt
The command represents how grep works. Both files mentioned will be searched in
filea.txt. Searched words are highlighted in the whole text of the output.
To search for more than two words, we will continue to add them in the same
method.
$ grep ‘graphic\|photoshop\|posters’ fileb.txt

Search Multiple Strings by Ignoring Case

To understand the concept of case sensitivity in grep function in Linux,
consider the following example. Two commands work on grep. One is with ‘-i’ and
the other is without. This example demonstrates the differences between the
commands. The first one shows that two words will be searched in a given file.
However, as indicated in the command “Aqsa”, it starts with capital A. Thus, it
will not be highlighted because, in a particular file, this text is in
lowercase.
$ grep ‘Aqsa\|sister’ file20.txt
It will only consider the word sister, which will be seen in the output.
In the second example, we have ignored case sensitivity by using the “–I” flag.
This function will search both words, and output will be highlighted. Whether
the word ‘Aqsa’ is written in capital letters or not, grep will search for the
same match in text inside a file. So, both commands are helpful in their ways.
$ grep –I ‘Aqsa\|sister’ file20.txt

Counting Multiple Matches in a File

Count function helps in counting the occurrence of a word or words in a
particular file. For instance, if you want to know about the errors occurring
in the system. The detail is recorded in the logs file. To maintain this
information in a specific folder, you will write the path of folders. This
example shows that 71 errors occurred in log files.

Search Exact Matches in a File

If you want to find an exact match in the files of your system, you need to use
the “–w” flag to sort it accurately. We have quoted a simple and comprehensive
example. In the below example, consider searching without “–w”, this command
will bring both words as matched with the given input. But with the use of the
“–w” flag, searching will be limited as input words only match the first
string. The second word is not highlighted because “–w” allows accurate
matching with the pattern.
$ -iw ‘hamna\|house’ file21.txt
Here –I is also used to remove case sensitivity in searching of text.
As seen in the photo, the results are not the same. The first command brings
all related data with whole strings, while the second command shows how exact
data matches through grep in searching for multiple strings.

Grep for More Than One Pattern in a Specific File Extension Type

Searching is done within all files. It is up to you if you search by providing
file name It will only search in specific files. But by providing a file
extension, data will be searched through all the files of the same extension.
There are two different examples to depict the related result. Considering the
first example, error files will be counted in all files of the .log extension.
“–c” is used for counting.
$ grep –c ‘warning\|error’ /var/log/*.log
This command implies that the files will be searched in all files of the .log
extension. The count of matches will be shown in the output to better
demonstrate grep with the specific file extension.
In the second example, we have used two words in our files in Linux with the
extension of the text. All data will be shown in the form of numbers. 0
indicates no matching data, whereas other than 0 shows that a match exists.
$ grep –c ‘aqsa\|my’ /home/aqsayasin/*.txt

Searching Multiple Patterns Recursively in a File

By default, the current directory is used if there is no directory mentioned in
the command. If you want to search in the directory of your own choice, then
you have to mention it. “–r” operator is used for grep recursively./home/
aqsayasin/ shows the path of files, whereas *.txt shows the extension. Text
files will be the target for grep to search recursively.
$ grep –R ‘technical\|free’ /home/aqsayasin/*.txt
The desired output is highlighted in the result showing the existence of these
words.

Conclusion

In the article mentioned above, we have quoted different examples to make it
easier for a user to understand the working of commands to search multiple
patterns on Linux. This guide will help you in escalating your existing
knowledge.


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

Linux Hint LLC, edit[email protected]
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
