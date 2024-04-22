





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Grep with the Line Number in Output

2 years ago
by Aqsa_Yasin
Global regular expression print is a versatile utility that searches plain text
in the system with different regular expressions. We can perform many
operations with the help of Grep; we can explore in files, display line number
as output, and how to ignore blank spaces, and use Grep recursively. Grep with
the line number displays the line number of relevant text present in the file.
This function is accomplished with the help of –n. From the page of Grep, we
can easily describe different commands.
$ man grep

Prerequisite

To achieve this current goal of obtaining a specific line number of the text,
we must have a system to run commands on it which is the Linux operating
system. Linux is installed and configured on the virtual machine. After
providing a username and password, you will be able to access the applications.

The Line Number for Matching a Word

Generically when we use the Grep command, after the Grep keyword, the word that
has to be explored is written and followed by the filename. But, by getting the
line number, we will add -n in our command.
$ grep –n is file22.txt
Here “is” is the word that is to be explored. The starting line number shows
that the related file contains the word in different lines; each line has a
highlighted word that shows the matching line to the relevant search.

The Line Number of the Whole Text in the File

The line number of every line in the file has shown by using a particular
command. It not only shows the text but also covers the blank spaces and
mentions their line numbers too. The numbers are shown on the left side of the
output.
$ nl fileb.txt
Fileb.txt is a filename. Whereas n is for the line numbers, and l shows the
filename only. In case we have searched a specific word in any file, it will
only show the filenames.
Concurrent to the previous example, here are (except for free space), which are
special characters that are mentioned. They are also shown and read by the
command to display the line number. Unlike the first example of the article,
this simple command shows the line’s number exactly how it is present in the
file. As there is no limitation of search declares in command.

Show Only Line Number

To get only the line numbers of data in the respective file, we can easily
follow the below command.
$ grep –n command fileg.txt | cut –d: -f1
The first half command before the operator is understandable because we have
discussed earlier in this article. Cut –d is used to cut the command, which
means to suppress the display of text in the files.

Provide Output in a Single Line

Following the command above, the output is display on a single line. It removes
the extra space between the two lines and only shows the line number mentioned
in the previous commands.
$ grep –n command fileg.txt | cut –d:-f1 | tr “\n” “ “
The right portion of the command shows that how the output is displayed. The
cut is used to cut the command. Whereas second “|” is applied for bringing to
the same line.

Show Line Number of the String within the Subdirectory

In order to demonstrate the example on subdirectories, this command is used. It
will search for the word “1000” present in files in this given directory. The
file number is shown at the starting of the line on the left side of the
output, showing the occurrence of 1000 in the prcd folder at 370 ties and in
Webmin is 393 times.
$ grep –n 1000 /etc/services
This example is good in finding an error occurring chances in your system by
checking and sorting particular words from the directory or subdirectory. The /
etc/ describes the path of the directory having a folder of services.

Show according to a word in the file

As already described in the examples above, the word helps search the text
inside the files or folder. Searched words will be written in inverted commas.
On the very left side of the output, a line number is mentioned, showing the
occurrence of the name on which line in a file. “6” shows that the word Aqsa is
present on line 6 after line 3. Highlighting the specific word makes it easier
for the user to understand this concept.
$ grep –n ‘Aqsa’ file23.txt
The output shows the whole string in the file, not only the single word present
in the string, and it only highlights the given word.

Bashrc

This is a useful example of getting the line number in the output. This will
search in all directories, and we don’t have to provide the directory path. By
default, it is implemented on all directories. It shows all the output data on
the files present in subdirectories, as we don’t have to mention a specific
word to be searched through the command.
$ Cat –n .bashrc
It is an extension of all folders that are present. By specifying the extension
name, we can show the relevant data, i.e., login detailed files.

Search in all Files

This command is used in searching the file in all files having that data. File*
shows that it will search from all files. The filename is displayed with the
line number after the name at starting of the line. The relevant word is
highlighted to show the existence of the word in the text in the file.
$ grep –n my file*

Search in Files Extensions

In this example, the word is searched in all files of a specific extension,
that is.txt. The Directory that is given in the command is the path of all
files provided. The output also shows the way according to the extension. The
line number is given after the filenames.
$ grep –n my file*

Conclusion

In this article, we have learned how to obtain the line number in the output by
applying different commands. We hope this effort will help in gaining enough
information regarding the relevant topic.


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
