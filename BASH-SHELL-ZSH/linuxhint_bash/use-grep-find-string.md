





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Grep to Find a String

1 year ago
by Kalsoom_Bibi
Grep is a short form for global regular expression print. It is a helpful tool
that Linux system engineers use when looking for a text or pattern in ordinary
files and the system. Grep is a fundamental command in Linux and Unix. It is
used to look for text and strings within a file. In other words, the grep
command looks for lines in a given file that match the provided strings or
words. It is among the most useful commands for programmers and sysadmins on
Linux and Unix-like systems. The grep utility, which we will be getting our
hands on today, is a Linux tool related to the egrep and fgrep tools. All these
are Linux tools for searching through your files, including text in a
repetitive manner. The grep command can be utilized to search for files and
their contents to retrieve important information. It is frequently used to
filter out irrelevant details while reporting only the information needed from
large log files.
This tutorial will show you how to use Grep with regular expressions to perform
advanced string searches with real-world examples. Many of the examples in this
article have real-world applications so that you may use them in your day-to-
day Linux programming. The following example illustrates how to use grep to
find patterns that are frequently searched for.

Syntax of Grep

In its simplest form, the grep command is made up of three parts. The grep
command comes first, followed by the pattern you are checking. Following the
string is the file name that grep looks for.
The most basic grep command syntax is as follows:
grep [OPTIONS] PATTERN [FILE...]

Installation of Grep

While most Linux systems include wit the grep utility installed by design, if
you don’t have it, follow these steps:
Using the Dashboard application area or the Ctrl+Alt+T shortcut, launch the
Ubuntu Terminal. Then, as the root user, run the following command to download
grep using apt-get command:
$ sudo apt-get install grep

Example 1

As discussed, the grep command is used to search “strings” in the text file. So
initially, we have to create a file in our Ubuntu 20.04 Linux system with the
help of the touch command.
$ touch test1.txt
We have named our file “test1.txt”. You can name it according to your need.
After executing the command as mentioned above, you will view the created file
in the home directory of your Ubuntu 20.04 Linux system as we have shown in the
below-attached screenshot.
Initially, the file will be empty; you can add the needed text to it. We have
added information related to the Ubuntu system. After adding the content to the
file, you can save it by clicking on the “Save” button or using the shortcut
key “Ctrl+S.” After that, you can close the file
Now the time comes to search for the string in the above file. We have to
search for a string “Ubuntu” from the file created in the above steps. You can
select your desired string from the content that you have added to your file.
Execute the following command to search string in Ubuntu 20.04 Linux system
using grep command.
$ grep “Ubuntu” test1.txt
You can check that the string is mentioned in inverted commas that we want to
search following the name of the relevant file. The output highlighted the
required string in red color.

Example 2

If you want to search any other string from the same file named “internet
access,” you have to execute the following command to search string in Ubuntu
20.04 Linux system using grep command.
$ grep “internet access” test1.txt
Again, inverted commas indicate a string that we intend to search for
before the name of a related file. The required string is highlighted in red in
the result.

Example 3

In this illustration, we will search the string in files. For this, we have to
create another file in our Ubuntu 20.04 Linux system with the help of the touch
command.
$ touch test2.txt
“test2.txt” is the name of our file. You can give it any name as you like.
Following the execution of the command as mentioned above, you will see the
created file in your Ubuntu 20.04 Linux system’s home directory, as seen in the
screenshot below.
The file will begin out empty; you can write it in with whatever text you need.
We have added information about the Ubuntu 20.04 operating system. After you
have finished adding content to the file, you can save it by hitting the “Save”
button or using the shortcut key “Ctrl+S.” After that, you can keep the file
and close it.
Now it is time to look for the string in both of the files we created before.
We need to look for the string “Ubuntu” in both of the files. You can choose
your preferred string from the content you have included in your document. To
search for a string in many files on an Ubuntu 20.04 Linux system, run the
following command.
$ grep “Ubuntu” test1.txt test2.txt
You can write the names of more than two files as well.

Conclusion

In this tutorial, we looked at using the Grep Linux command to search and find
strings in a text document. Then you can utilize it to find filtered results,
which may include files or file contents. This saves you a lot of effort that
you would have spent scanning through all of the search results before learning
to use the grep command. It would be best if you now understood how powerful
the Linux search function is.


About the author


Kalsoom Bibi

Hello, I am a freelance writer and usually write for Linux and other technology
related content
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
