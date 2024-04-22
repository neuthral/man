





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


sed examples of capture groups

1 year ago
by Adnan_Shabbir
The text file handling operations play a vital role in the daily life of a
computer user as to deal with text is a common among the users of all
professions. Linux and its distros provide a variety of tools and command line
utilities to access and manage text files like the default editor, vim, nano.
These tools assist to edit, delete, substitute, the text inside text files;
however, the users have to open the file using any of these editors and
manually perform the changes that are to be made.
There is another well-known editor known as “Stream Editor (sed)”; sed command
line utility of Ubuntu provides an extensive support to manage text files; this
tool is ranked in topmost editors because of the advanced features that it
offers while dealing with text files. The reason behind its popularity is one
line command operation: which means that it can manage text files using
terminal and the users do not have to open and manually edit any text file.
Capturing group refers to another advanced feature of this tool; the group
capturing functionality of sed allows the user to get the specific part of a
text file or a line. In this detailed guide, we have briefly described the
concept of capture grouping, its working and usage with sed.
Firstly, we will get some deep insight into the capture groups and then we’ll
proceed to its usage with sed:
So, Let’s start today’s guide:

How capture groups work

As discussed above, capture groups are the specific part of any line, or text
file. There may be one of the following purposes behind the capture groups:

* To capture the information
* Manipulate the text for specific match

It can be used to get the pinpoint information by searching the specific part
inside a text file as well as the manipulation operations can also be performed
on that specific match.

How to make capture groups using sed command in Ubuntu

The capture groups in sed are formed by applying parenthesis to regular
expressions or the operation that the user wants to perform. For instance, to
make capture groups you have to put parenthesis like “\(” at start and “\)” at
the end of a specific regular expression:
In short, capture group are used to take the specific part of line, text file
and then perform an operation on that group:
The upcoming examples demonstrate the use of capture groups using sed command;
examples vary from basic to advanced level.

Capturing Single group using sed command

The command written below will capture the word “Hello” and then replace the
word occurring after it (“sed!”) with “Linuxhint”: You may have noticed that
capture group is enclosed in parenthesis expression “\(” and “\)”.
$ echo Hello sed! | sed 's/\(Hello\) sed!/\1 Linuxhint/'

Capturing multiple groups using sed command

The sed command allows you to capture multiple groups and then perform the
operation on that group. For instance, the command mentioned below will capture
and print only selected groups. It is observed that capture groups can be
called by assigning them an order name:
In the echo part of this command three distributions and a parent Linux is
placed, i.e., total four entries: however, in the sed command we have only
called 1,2 and 3 groups in reverse order. The output shows that only three
groups are printed in reverse order while “Fedora” keeps its original position:
$ echo Ubuntu Debian Linux Fedora | sed 's/\(Ubuntu\) \(Debian\) \(Linux\)/\3
\2 \1/'

Capturing groups of complex expressions

Let’s say we have an expression that contains alphanumeric keywords; we have to
make groups and then print them in any (reverse/normal) order. The command
given below show that the expression contains alphanumeric keywords; we have
made groups of all three alphanumeric words and then displayed those words in a
reverse order:
Note: The same command can be used by replacing “\w\w*” with “[[:alnum:]_]\
{1,\}”:
$ echo Linuxhint 123 capture_groups | sed 's/\(\w\w*\) \(\w\w*\) \(\w\w*\)/\3
\2 \1/'
The command above contains capture groups “\(\w\w*\)”; these work for
alphanumeric keywords. You can execute the above command by using the
alphanumeric character class as a capture group. For instance, the command
mentioned below will give the same output when alphanumeric character class is
used as a capture group:
$ echo Linuxhint 123 capture_groups | sed 's/\([[:alnum:]_]\{1,\}\) \([[:alnum:
]_]\{1,\}\) \([[:alnum:]_]\{1,\}\)/\3 \2 \1/'

Conclusion

Sed command line utility provides detailed guidance to deal with text files
using command line terminal; this editor may be difficult to operate but as you
dig into the details, you will find it easy to understand and apply. Moreover,
its advanced functionalities ease the process of manipulating and managing the
text files; like regular expressions and group capturing. In this article, we
have pinned down the concept of capture groups in sed; and provided the
thorough usage by referring to a few examples. The capture groups are quite
useful especially when you have very large text files and want to identify
specific content from those files.


About the author


Adnan Shabbir

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
