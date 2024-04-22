





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How Do I Use Grep to Search a File on Linux?

2 years ago
by Aqsa_Yasin
Grep is a versatile command that allows sorting input by following complex
rules and regulations. It is a powerful command in a Linux environment. It is
not for searching files directly on your system. It shows the file names that
indicate the particular part of the string that matches your part present in
the search query. In the proceeding article, we will explain some examples to
let you understand searching with the help of Grep.

Syntax

Grep [pattern] [file]
The pattern should be a word or symbol that is to be searched in the file.

Prerequisites

For successful working of Grep in your system, you must have Linux operating
system installed. After configuration, you will give the user information to
have privileges to access the applications installed. Moving forward, go to the
terminal command line by using a shortcut key ctrl+alt+T.

Grep Installation

$ Sudo apt-get install grep
If you haven’t yet installed Grep, you can install repositories of Grep in
Ubuntu by using this command.

Grep Manual

To know about the Grep commands, we can go to the man page. Grep is very
versatile and allows users to use it in complicated ways.
$ Man grep
Some examples that help in understanding the functionality of Grep are as
follows:
-I distinctions on the case is ignored
-n print the line number with output
-r search all directories on Linux
–color Display the matched result in colors

Show all Files

If you already have Ubuntu files and want to list them to see all filenames and
extensions, you can use the following cited command.
$ ls
You will simply use the “ls” command to display all files created.

File Creation if not Already Exists

To understand the functionality of searching a file, we need to have a file or
files created in our system. If you don’t have any files, then you should
create files. File in Linux is made in more than one way. A simple method that
we are going to use is described as following.
$ echo “text” > filename
The echo word is used to display data in the Linux command. Using this command,
the user will be able to create a file and enter data in it by using the same
command. In the particular example, the name of the file is file20.txt. As the
file contains text, so we have used the file extension of ”.txt.”
Similarly, another example of file creation is that we have created more than
one file at a time.

Search File by Sorting a Word

A file in Linux can be searched through a word. The syntax is quite
comprehensible.
$ grep “technical” file*
This command shows not only the filename but also the data present in it. In
the current example, you will know that the word through which we have searched
is highlighted to show its existence in the file. Moreover, the filename is
written initially, “File*” means to search that particular word in all files.
That’s how a single word helps in obtaining the output of filenames.

Search File using “-l”

“-l” is a command used to display only the names of files in Linux.
$ grep –l my file*
As the command mentioned above, “my” is a word that we want to search in files.
As we have described above that “file*” means to search in all files created in
the system. We can observe that there are four filenames with”.txt” extensions
and one without any extension. It means that all files having particular words
are shown. We will further see how specifically we can search a file by
mentioning the extension.

Search File by File Extension

In the previous example, we have seen that by sorting all files were displayed.
But to show filenames of specific extensions below written command is used
“*.txt” represents the extension type of a file so that all files should be of
this extension.
This is basic discrimination between the last two examples which is held
through file extension.
$ grep –l “my” *.txt

Search File by Using “-e”

There might exist a situation wherein you want to search files with the help of
more than one word in different files. In these types of scenarios, we should
use the“-e” command-line option. For example, you want to search those files
having three specific words, then this command is recommended. Searching will
be applied to all files present in your current working directory. These files
must be of text extension as there is a limitation of text.
$ grep –e my –e aqsa –e technical *.txt
Grep, Aqsa, and Technical are three words based to search files. All these
words are highlighted wherever these words are found in particular files.
Filenames are mentioned in the starting. There is a possibility of the
existence of only a single word in a file.

Search Data of a Single File

In previous examples, we have seen that the filename is displayed with data
present in the file. If we don’t know the data present in the file or a single
word is rememberable, we can search within the file with the help of the word.
$ grep ‘Aqsa’ file20.txt
In this example, the command fetches whole data with the help of a word in the
file.

Search Data through more than a Single File

Like the preceding example, here searching is done by one word but in two
files. Both files are of text extension, and the word that is present in both
files are highlighted. Filenames are also displayed as we have searched with
the help of both filenames.
$ grep ‘Aqsa’ file20.txt file23.txt

Show Word Existence in File

To check file existence or presence of the words in a file. The“-q” flag is
used, and it works to search particular terms in all files that display “1” or
“0” as output. If “1” comes, it means there is no match, but if the match is
found, it shows ”0”.

Conclusion

We have explained each example in detail to pursue information for users. It
will apply to the Grep file searching effortlessly on files and within the
files in the Linux environment.


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
