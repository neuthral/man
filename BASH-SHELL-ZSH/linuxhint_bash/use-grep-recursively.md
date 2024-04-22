





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Grep Recursively?

2 years ago
by Aqsa_Yasin
Grep command is used to search text from files. It is a versatile pattern that
invokes grep with –r. –R option search files recursively from subdirectories,
starting from the current directory. The command is run from the top-level
directory. For instance /home/abc etc. Grep is a tool for obtaining
dependencies while moving from one host to another. If we do not mention a
directory in the command, grep will search the current working directory. To
perform grep recursively, there are three arguments that we have taken from the
man page of grep.
$ Man grep
–include is used for an exact match in the file which could be files that are
present in the directory, or by default. –r implies the directory name, as
described earlier, if no path is defined in the command, the current directory
is considered. It only follows a symbolic link. –R is quite different from –r
because it reads all files, not only the symbolically defined ones.

Syntax

Grep  –R  “pattern”  /path/
“Path” is a “directory path”. And the pattern is a word or a string you want to
search.

Prerequisite

To understand the grep recursive function, you need to have Linux operating
system. After installation, you will configure Linux by providing a username
and password. After doing so, you will get privileges to access all
applications in that operating system.

All Files in Linux

This command will help you search all the file names in the directories of your
system. As –l works in providing only the file names, –r will help to search
symbolically wherever the required word is present, will come as output.
Whereas “Aqsa” is the word we want to search for. This command is without any
path to the directory because here, we want all possible file names in the
system. If we have provided a path, then the searching process will have
limitations.
$ grep  –r  –l  “aqsa”

Simple Example

To understand the dilemma of recursiveness with the help of the path, we
introduced a simple example to guide the user. As shown in the below command,
“versatile” is a word we want to search. Following the word, there is a
directory in which we wish to sort. It shows both the filename with the
directory and the whole text inside the file. –r also shows the binary files.
$ grep –r versatile /home/aqsayasin

Recursively Search in All Directories and Subdirectories

As we are all familiar with the functionality of “*” in the searching system.
It implies sorting in all files. So, the command will display the respective
data from all the files. The “house” word is to be searched recursively using
the grep statement.
$ grep –r “house” *
It shows the filenames and the text inside by highlighting the searched word,
indicating that a match exists. Only a single text file contained that word,
which is shown in the resultant line.

Grep Recursively for a String

Unlike the above examples, grep works on a string in the specific directory. /
etc/ is the command directory that means that searching will be through this
directory, the IP address of a computer. Its information is saved in the
directory, having names of files present in directory /etc/ppp/. The option is
the name of a particular folder. This command will read all files under the
given directory.
$ grep –r “192.168.1.5” /etc/
The names of the file in the output can be suppressed with the help of the–h
option. The command is as follows.
$ grep -h -R "192.168.1.5" /etc/
Both separators can be written like -h -R in a command.

Search Recursively Without a Directory

Recursive search can also be done without using a directory by simply searching
a word with a single word.
$ grep  –r  wife
The “wife” word is searched in all directories automatically because when there
is no directory mentioned, the searching process will proceed in all files and
directories of the system. It will also include binary files along with the
text files. File address and file names are shown at first. Whereas text inside
the file is displayed. Not only the plain text but also the grep command
applied on the file text is shown, i.e., grep ‘I am a house wife’.

Grep Exact Multiple Patterns

Searching multiple methods is also a feature obtained through the grep command.
“-rw” is used to explore the particular match. “-e”  is used to add more than
one pattern in the command. The directory path is mentioned to make it
convenient for the system to search. Binary files are excluded because the
limit is introduced in adding a directory in the command. The output contains
the file directory name and file name. Also, text inside the file is displayed.
$ grep –rw ‘/home/aqsayasin/’
Searched words are highlighted in the file text. Both searched terms need to be
present in a single file. There is a probability of the existence of words in
different files, as shown in the output.

Grep Recursively Using – -Include

“—include” matches the given file pattern and works effectively as it also
speeds up the searching process, which works most of the files. Here, it does
not bring binary or compiled, or image files in it. The file extension is used
to add limitations to the command. The directory is mentioned to bring the
required output. The included keyword is quite advanced in grep as compared to
other functionalities.
$ grep –r - -include=”*txt” “sister” /home/aqsayasin

Conclusion

In this article, we have explained each example to demonstrate the usage of the
grep recursive function. A recursive function is used to search with
limitations and precisely in all directories in the system. If a directory is
not present, the current directory is considered by default.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
