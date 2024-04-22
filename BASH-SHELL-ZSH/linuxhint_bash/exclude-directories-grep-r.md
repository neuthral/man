





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How can I exclude directories from grep -R?

2 years ago
by Aqsa_Yasin
Grep is indeed a Linux / Unix terminal shell utility that searches a document
for a sequence of characters. A regular expression seems to be the term for the
textual pattern to be searched. It outputs the row with the outcome when it
detects the same match. While browsing across huge log files, the grep query
comes in hand. So, grep –R has been used to exclude directories while using
some keywords. Let’s discuss grep –R in this tutorial step by step.

Prerequisites:

Make it clear to have any distribution of Linux installed and configured. We
are using the Ubuntu 20.04 Linux system to implement this topic. On the other
hand, you must have root user rights as well. Open your command terminal to
start working.

Example 01:

When you open the command terminal, you are currently at the Ubuntu 20.04 Linux
system’s Home directory. Let’s navigate to a Documents directory. For this, you
have to use the below-stated “cd” command in the command shell to do so, along
with a directory path.
$ cd ~/Documents
Now you are in the Documents directory of your Linux system. Let’s create three
new files in the Documents directory. To create new text-type files, try the
below touch command in the shell, followed by a new file’s name. You can see we
have created three files named “one.txt,” “new.txt,” and “test.txt.”
$ touch one.txt
$ touch new.txt
$ touch test.txt
You have to add some text data or information in each file separately, as you
can see in the images below. Now save all the files and close.
Now come back to the terminal and list all the files and folders listed in the
Documents directory. Execute the simple “ls” command to do this as below. You
will have an output of all the files and folders lied in the Documents
directory. You can see that newly created and updated text files are also
there.
$ ls
Now it’s our turn to try some grep –R command on the Documents directory and
its files or folders. We will be using the grep –R command to exclude the
directories while using one keyword or unique word. We will have a command that
will search that particular word from all the files residing in the Documents
folder except one directory, which has been given to exclude in the command.
So, we are going to exclude the “Wao” directory currently present in the
Documents directory. So, try the below grep command to exclude the “Wao”
directory along with the –R flag, which has been used for recursive function,
and “Aqsa” has been used as a keyword to be searched in the files. The output
in the snapshot below is showing the text from two files, “test.txt” and
“new.txt,” having the text “Aqsa” in their data and the directory “Wao” has not
been checked due to exclusion in the command. However, the directory “Wao” also
has some text files that are avoided to be checked.
$ grep –exclude-dir “Wao” –R “Aqsa”
Let’s look at both the files. Try the cat command to see the file “new.txt”
contains the keyword “Aqsa.”
$ cat new.txt
The other file, “test.txt,” containing the keyword “Aqsa,” has been displayed
using the cat command below.
$ cat test.txt
Now let’s exclude the same directory “Wao” from the Documents folder using
another keyword, “brave,” if it lies in any files. So, try the below grep
command to exclude the directory as below. The output image shows the two
matched outputs for the keyword “brave” in two files, “test.txt” and “one.txt.”
$ grep –exclude-dir “Documents/Wao” –R “brave.”
You can see the file “one.txt” contains the keyword “brave” using the cat
command.
$ cat one.txt
The output below shows the file “test.txt,” which contains the keyword “brave”
with cat instruction usage.
$ cat test.txt

Example 02:

Let’s jump to the sub-directory “Wao” of the Documents folder using the “cd”
command in the shell.
$ cd ~/Documents/Wao
Let’s create three new files, “bin.txt,” “had.txt,” and “sec.txt” in the
directory “Wao” while using the touch command listed below. Add some text data
in all the files, save and then close them.
$ touch bin.txt
$ touch had.txt
$ touch sec.txt
Let’s list all the directories using the “ls” command as below. You will find
all the three newly created files in it.
$ ls -a
Let’s try the same grep instruction in your command terminal to exclude the
directory “Wao” while using another keyword “I” as a match as below.
$ grep –exclude-dir “Documents/Wao/” –R “I”
Now the output for this command shows the keyword “I” in the files held in the
folder Documents while the directory “Wao” has been ignored using the “exclude-
dir” keyword.
Now let’s exclude the same directory “Wao” using another keyword, “rimsha,”
from the grep command shown below in the terminal. The output snap shows no
output because the keyword “Rimsha” has not been found in any of the files
located in the Documents folder.
$ grep –exclude-dir “Documents/Wao” –R “rimsha”

Example 03:

Let’s navigate to the Documents folder first using the “cd” command as beneath.
$ cd ~/Documents
Let’s list all the directory Documents’ files and folders using the below ‘ls’
command. The output shows some text and other files along with one sub-
directory, “Wao.”
$ ls
Let us use the same grep command to exclude the directory “Wao” from this
folder using the keyword “Aqsa” in a flag. The output shows the four text files
having the word “Aqsa” in their text while the directory “Wao” has been avoided
and not checked.
$ grep –exclude-dir “Wao” –R “Aqsa”

Conclusion:

Using Ubuntu 20.04, we already understand how and when to use the grep –R
command. The grep command is extremely versatile and helps to locate text
embedded in hundreds of documents.


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
