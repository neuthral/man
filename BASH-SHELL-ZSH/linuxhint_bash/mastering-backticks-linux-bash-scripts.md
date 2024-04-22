





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Mastering Backticks in Linux Bash Scripts

2 weeks ago
by Prateek_Jangid
Bash scripts are best when it comes to simplifying the daily tasks. These
scripts contain commands and tricks that you can use as a sysadmin. The
backtick (`) operator is one of those features of Bash script that can ease up
your work.
However, many beginners misunderstand the backticks as quotation mark
characters used in the strings. That’s why learning about back quote characters
or backticks is essential. In this guide, we will list down the approach on how
to master the backticks in Linux Bash scripts.

Mastering Backticks in Linux Bash Scripts

Before moving to the illustrations of backticks in Bash scripts, let’s
understand what they are and why we should learn them.

What Are Backticks in Linux Bash Scripts?

Backticks or the back quote (`) character which allows a user to assign the
shell command’s output to the variable. It runs the commands in the system and
returns the output to continue the logic in the particular script. In simple
words, the backticks in Bash scripts work as a bridge between two commands,
which means that the second command’s action depends upon the first one. This
tiny piece of code is a significant building block in script programming. You
can easily use the backticks since combining them with other script commands is
simple.

How to Use Backticks in Bash

Now, we will use a simple example to use the backticks in the Bash script. For
example, you have four text files: MyFile_1.txt, MyFile_2.txt, MyFile_3.txt,
and MyFile_4.txt. One of these files contains a “Linuxhint.dev” text, and you
want to find that particular file to edit. That’s why you must execute the grep
command and then use the gedit command. We can use the backtick character here.
Here is the following method:
The text files are present in the Documents directory, so use the following
command to create a Bash script:
touch MyFile.sh
After that, execute the following commands:
chmod +x MyFile.sh

nano MyFile.sh
The first gives executable permission to the script, and the second opens it in
the nano editor. Now, enter the following details in the script to make it
work:
#!/bin/bash

gedit `grep -l "Linuxhint.dev" *.txt`
In the previous codes, the system executes the grep command and then executes
the gedit command according to the output of the first one.
Finally, run the Bash script in the terminal. It opens the MyFile_2.txt since
it has the “Linuxhint.dev” text.
./MyFile.sh
You can also use the backticks to add a command execution in the string. For
example, we add the current time when we opened the script. It only requires
the following codes in the script:
#!/bin/bash

DATE= `date`

echo "You have accessed the script on: $DATE"
We can get the following result by executing the “File.sh” Bash script in the
terminal:
./File.sh

Conclusion

This is the brief information on the best approach to mastering backticks in
Linux Bash scripts. Backticks play an essential role as it helps to run the
multiple commands from the Bash script. With backticks, you can execute the
different commands based on their output. In this guide, we explained two
examples by which you can understand everything about the backticks in the Bash
scripts.


About the author


Prateek Jangid

A passionate Linux user for personal and professional reasons, always exploring
what is new in the world of Linux and sharing with my readers.
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
