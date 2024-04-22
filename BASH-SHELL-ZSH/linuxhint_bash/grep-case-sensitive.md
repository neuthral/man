





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How Do You Grep Case Sensitive?

2 years ago
by Aqsa_Yasin
Global regular expression print is a versatile and powerful feature of Linux.
It helps in finding words and phrases in the file such that the grep keyword is
used to obtain the desired functionality. Grep is used to obtain data not only
from direct searching in the text but also from directories as well, by
applying the commands on it. It searches the respective data and modifies them
by removing the extra space between the text, obtaining line numbers, and
excluding terms from the data. The simplest feature of grep is to handle case
sensitivity. Grep is case-sensitive by default hence it shows the
perceptibility of both upper and lower cases in the file. This feature helps in
getting the required output by removing the discrimination of the case which
can all be done on the main page of grep.
$ man grep
From that command, we will find two features described above. –I mean to ignore
the case, wherever this keyword is used, the case affection is removed.

Prerequisite

To fulfill the accomplishment of that feature’s functionality in the Linux
operating system, we need to have a Linux OS installed. After configuration,
you will provide the required user information, with the help of that the user
will be logged in. Furthermore, when the username and password are provided,
the user will be able to access all built-in features of the operating system.
Finally, once the desktop is accessed, you are required to access the terminal,
as commands have to be run on it.

Example 1:

In this example, we will see how grep helps in making use of avoiding case
sensitivity. Consider a file named files11.txt. The file contains the following
data in it; as you can see the word mango is written in different ways, some
words are in uppercase and some are in lowercase. By using the cat command we
will display the data of the file.
$ cat files11.txt
Once the command is used to display the data, it can be observed that the only
word that matches the case of the letter present in the command is displayed.
All letters are in lowercase.
$ grep mango files11.txt
Now to understand the concept of case insensitivity, we will use “-I” in the
command to handle case-sensitivity by providing all the data present in the
file, the matches with the string present inside the command.
$ grep –I mango files11.txt
From the output, you will come to know that all data that matches the word
“mango” is displayed either with some words written in uppercase and some are
in lowercase.

Example 2

This example resembles the first one, the difference is that only a single word
is obtained. This command helps in obtaining the whole string by matching it
with the word provided in the command. Let us have a file filea.txt. as an
example, we want to fetch a record according to the given match.
$ cat filea.txt
Now apply the same command to ignore the case and depict the output. The
technical word is displayed by excluding the case to make it case-sensitive.

Example 3

Another method of using grep to ignore case is to introduce a filename first
and later apply the –I command with grep following “|” operator. Cat is used in
conjunction with “|”. Let us have a file named file24.txt. as an example.
$ Cat file24.txt | grep –I “Aqsa”
This command will fetch the word “Aqsa” in both upper and lower cases.

Example 4

Moving towards another example. Here we will display the data of the file
containing the word “my”. Here searching is done by introducing a directory
thus command will sort the word in all files having the extension .txt in the
system.
$ grep –I my /home/aqsayasin/*.txt
The above image shows the output obtained from the command. “my” word is
highlighted, that is in both cases. Some files contain it in small letters
while others have it in capital ones. The address of the files and file names
are also displayed.

Example 5

This example can be applied to the directory having all files present in it.
Limitations will be applied to display the specific result that matched with
the word we have defined in the command. “is” word is used for searching in all
files present in the system.
$ grep –I is /home/aqsayasin/file*
The output shows whole strings containing the matched word in it. As “is” is
written separately or combined within another word i.e. sister.

Example 6

The next command shows how –iw works together in the command. Besides here, the
search is through two words in a single file. The backslash and “|” are used to
describe two words in a file while –w is used for the exact match of the
respective word in the file.
$ grep –iw ‘hamna\|house’ file21.txt

$ grep ‘hamn\|house’ file21.txt
-I will ignore the case sensitivity. In the above example, we can see that the
presence of –w with –I, allows a house in the first command not to be
considered because –w allows the exact match. In the second command, we have
removed both –iw, hence both words are displayed after matching in string.

Example 7

More than one word is searched by applying a different method. Both words are
searched from the same file these words are “job” and “earn”. Earn is fetched
from the word learning as well take note that each word is separated from the
keyword –e.
$ grep –I –e job –e earn filea.txt
The above image shows the whole strings in a paragraph regarding the words
present in the command. Like the above examples, -I have ignored all case
discrimination of the words job and earn.

Example 8

In this example, searching two words present in all files of the .txt
extension. These two words are separated with –e, as –e is the right way for
the separation of two words. The output obtained will have both words shown in
all files of text extension. The whole address of the file is obtained and is
displayed. –I will ignore the case sensitivity and will display both words
present in all files.
$ grep –I –e job –e earn /home/aqsayasin/*.txt

Conclusion

In this guide, we have used the simplest example to elaborate on the concept of
case sensitivity. We have tried our best to go through each aspect to enhance
the knowledge regarding grep.
grep


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
