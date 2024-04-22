





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash brace expansion

3 years ago
by Fahmida_Yesmin
Bash uses brace expansion to generate a sequence of strings from the terminal
or by using any bash script. A sequence of expressions or comma-separated list
of data with curly brackets is used to define brace expansion. Two optional
parts of brace expansion are preamble and postscript. The preamble is used to
add text at the front of each generated string and postscript is used to append
text at the end of the generated string by using brace expansion. How the user
can create different types of random strings using bash brace expansion is
explained in this tutorial by using various examples.
Syntax:

  1. String List

{String1, String2,... ,StringN }

  1. Range List

{<start> . . <end>}

  1. Preamble and postscript

<preamble>{ string or range }
{ string or range }<postscript>
<preamble{ string or range }<postscript>
The above syntax shows that you can use brace expansion without preamble and
postscript or with preamble or with postscript or with both. Different uses of
brace expansions are shown in the next part of this tutorial by using various
examples.

Example-1: Using comma-separated lists

The following command shows the use of brace expansion with comma-separated
list only. You have to remember one thing while defining the list. That is,
list items must be separated by comma only and don’t add any space between the
items, otherwise brace expansion will not work. Here, the first command will
display the list items with space. Two lists are used in the second command and
the output will generate by combining each items of each list.
$ echo {PHP,Javascript,JQuery}
$ echo {"I like ","Learn "}{"PHP","Programming"}
Output:
The following output will appear after running the script. In the second
command, there are two items in each list and there are two lists. So, the
second command will print (2X2=4), four text as output.

Example-2: Using Ranges

Different types of ranges can be used in brace expansion to generate the list
of data. The uses of four types of ranges are shown in this example. The first
range will create a list of numeric data, starting from 50 to 60. The second
range will generate a list of alphabetic characters, starting from A to F. The
third range will generate a list of number, starting from 1 to 5 with leading
zero. The forth range will generate a list of alpha-numeric data by combining A
to C and 1 to 3.
$ echo {50..60}
$ echo {A..E}
$ echo {01..05}
$ echo {A..C}{1..3}
Output:
The following output will appear after running the above commands. In the last
command, the first brace expansion contains three items and the second brace
expansion contains three items. So, the total items in the output will be, 3X3
= 9.

Example-3: Using preamble

This example shows the use of preamble in brace expansion. The first command
will add the string, “Hi “ with each item of the list and generate the output.
The second command will add ‘b’ with each item of the list. This type of task
is beneficial if you want to add a common text or character at the front of
each list item.
$ echo "Hi "{John, Mohammed, Lisa}
$ echo b{all, ell, oat, eef}
Output:
The following output will appear after running the commands.

Example-4: Using postscript

This example shows the use of postscript in brace expansion. The text, “ is a
programmer” will add at the end of each list item in the first command. The
word, “ball” will add with each item of the list in the second command. If the
last part of each item of the list are same then it is better to create the
list by brace expansion with postscript.
$ echo {John,Mohammed,Lisa}" is a programmer."
$ echo {basket,foot,volley}ball
Output:
The following output will appear after running the commands.

Example-5: Using both preamble and postscript

When the first part and last part of each item of the list are same then it
better to create the list by using brace expansion with preamble and
postscript. Here, the first command will add “Hi “, at the beginning of each
list item and “ welcome to LinuxHint.“, at the end of the each list item. The
second command will generate an alpha-numeric list by adding “*****” at the
front and “.*****” at the end of the list item. According to the range, the
first item is Q01 and the last item is Q05.
$ echo "Hi, "{John,Mohammed,Lisa}" welcome to LinuxHint."
$ echo "*****Q"{01..05}".*****"
Output:
The following output will appear after running the commands.

Example-6:  Creating sequence of directory and file

`echo` command is used in all previous examples of this tutorial. But you can
use brace expansion with other commands also. How you can create multiple files
or folders in a single command by using brace expansion is shown in this
tutorial. The following command will create three folders, Design, Programming
and Framework, by using `mkdir` command and brace expansion.
$ mkdir {Design,Programming,Framework}
$ ls
Output:
The following output will appear after running the commands.
You can also create sequential multiple files by using touch and brace
expansion with preamble and postscript. In this example, `touch` command is
used to create multiple files. “ps” is used as preamble, “.py” is used as
postscript and 1..3 range is used to create the sequential file names. The
second command, ‘ls’ will show the files are created or not.
$ touch “ps”{1..3}”.py”
$ ls
Output:
The following output will appear after running the commands. Here, three files
will be created. These are ps1.py, ps2.py and ps3.py.
 

Conclusion

Brace expansion is very useful for generating a list of sequential data or
running any command on sequence of data. Some common uses of brace expansion
are shown in this tutorial. Hope, the reader will be able to use brace
expansion properly after practicing the examples of this tutorial.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
