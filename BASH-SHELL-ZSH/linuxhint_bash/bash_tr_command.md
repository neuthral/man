





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash tr Command

1 year ago
by Fahmida_Yesmin
`tr` is a very useful UNIX command. It is used to transform strings or delete
characters from the string. Various types of transformation can be done by
using this command, such as searching and replacing text, transforming string
from uppercase to lowercase or vice versa, removing repeated characters from
the string, etc. The command can be used for some complicated transformations
also. The different uses of the `tr` command have shown in this tutorial.

Syntax:

tr [option] stringValue1 [stringValue2]
The optionand stringValue2 are optional for the `tr` command. You can use –c, -
s and -d option with the `tr` command to do different types of tasks.

Example-1: Change Case

You can change the case of the string very easily by using tr command. To
define uppercase, you can use [:upper:] or [A-Z] and to define lowercase you
can define [:lower:] or [a-z].
The `tr` command can be used in the following way to convert any string from
uppercase to lowercase.
tr [:upper:] [:lower:]
You can use `tr` command in the following way also to convert any string from
lowercase to uppercase.
tr a-z A-Z
Run the following command to convert all small letters of the
string,’linuxhint’ into the capital letter.
$ echo linuxhint | tr [:lower:] [:upper:]
Output:
The following output will appear after executing the above command. The string,
‘linuxhint’ has converted into the string, ‘LINUXHINT’.
You can apply the `tr` command for converting the content of any text file from
upper to lower or lower to upper. Suppose, you have a text file named,
items.txt with the following contents.

  1. Monitor
  2. Keyboard
  3. Mouse
  4. Scanner
  5. HDD

Run the following commands from the terminal to display the content of the
items.txt file and the output of the `tr` command after converting the content
of that file from lower to upper case. The `tr` command will not modify the
original content of the file.
$ cat items.txt
$ tr a-z A-Z < items.txt
Output:
The following output will appear after executing the above commands. All small
letters of the items.txt file have been converted into capital letters.
You can run the following command to store the output of the `tr` command into
another file named ‘output.txt’.
$ tr [:upper:] [:lower:] < items.txt > output.txt
$ cat output.txt
Output:
The following output will appear after executing the above commands. The
output.txt file contains all small letters.

Example-2: Translate Character

`tr` command can be used to search and replace any particular character from
any text. The following command is used to convert each space of the text,
“Welcome to Linuxhint” by a newline (\n).
$ echo "Welcome To Linuxhint" | tr [:space:] '\n'
Output:
The following output will appear after executing the above command. Each word
of the text has printed each line.

Example-3: Using –c (–complement) Option

`tr` command can be used with -c option to replace those characters with the
second character that don’t match with the first character value. In the
following example, the `tr` command is used to search those characters in the
string ‘bash’ that don’t match with the character ‘b‘ and replace them with
‘a’. The output will be ‘baaaa’. Four characters are converted here. These are
,’a’,’s’,’h’ and ‘\n’.
$ echo "bash" | tr -c 'b' 'a'
Output:
The following output will appear after executing the above command.

Example-4: Using -s Option

The `tr` command uses –s (–squeeze-repeats) option for search and replace any
string from a text. In the following example, space (‘ ‘) is replaced by tab
(‘\t’).
$ echo "BASH Programming" | tr -s ' ' '\t'
Output:
The following output will appear after executing the above command. Here, the
space has been replaced by tab space.
You can use both -c and -s options together with the `tr` command. In the
following example, the range of small letters has been used as the first string
value. For –c option, the `tr` command will search and replace the characters
which are not small letters with a newline (‘\n’) of the file, items.txt, and
store the output of the command in the file, output.txt.
$ cat items.txt
$ tr -cs [a-z] "\n" < items.txt > output.txt
$ cat output.txt
Output:
The following output will appear after executing the above commands. The
output.txt file contains the small letter only.

Example-5: Using –d (–delete) Option

The -d option is used with the `tr` command to search and delete any character
or string from a text. In the following example, the `tr` command will search
‘P’, ‘y’, and ‘t’ in the string “Python is a Programming language” and delete
those characters.
$ echo "Python is a Programming language" | tr -d 'Pyt'
Output:
The following output will appear after executing the above command. The ‘P’,
‘y’, and ‘t’ characters have been removed in the output.
The -c option can be used with the –d option in the `tr` command to complement
the search like the previous -cs command. In the following example, the `tr`
command with –cd will search all non-digit characters from the string, “Phone
No: 985634854” by using numeric range and delete them.
$ echo "Phone No: 985634854" | tr -cd '0-9'
Output:
The following output will appear after executing the above command. The output
contains the numeric part of the string only.
Similarly, you can use the -cd option in the `tr` command like the following
command to remove the non-printable characters from a file. The ‘\n’ is a non-
printable character that will be removed from the items.txt file.
$ tr -cd "[:print:]" < items.txt
Output:
The following output will appear after executing the above command. The output
contains the content of the items.txt file after removing the newline(\n)
character.

Example-6: Remove all non-numeric characters

The `tr` command can also be used to remove all non-numeric characters from a
text by using [0-9] or [:digit:] with the command. Run the following command to
remove all non-numeric characters from the text using [:digit:] class.
$ echo "The product price 800 dollars" | tr -cd [:digit:]
Output:
The following output will appear after executing the above commands. The output
contains the digits only.

Example-7: Print the $LS_COLORS Value on a Separate Line Based on Delimiter

Any environment variable with a colon(:) delimited list values can be printed
into separate lines by using the `tr` command. The $LS_COLORS is an environment
variable that contains colon-separated key and color values. Run the following
command to print each key and color pair in each line.
$ echo $LS_COLORS | tr  ':' '\n'
Output:
The following output will appear after executing the above commands.

Example-8: Converting the Contents of a File Based on Delimiter

Create a text file named “students.txt” with the following content. The colon(:
) has been used as the separator in each line of this file.
students.txt
Md. Hossain:CSE:Batch-50:Semester-10
Nibir Rahman:CSE:Batch-51:Semester-9
Mehnaz Kazi:CSE:Batch-52:Semester-8
Run the following commands to print the original content of the text file,
create output.txt file by converting the colon(:) of the students.txt file by
‘\t’, and print the content of output.txt file.
$ cat students.txt
$ tr ':' '\t' < students.txt > output.txt
$ cat output.txt
Output:
The following output will appear after executing the above commands. The
output.txt file contains the converted content of the students.txt file.

Conclusion

The basic uses of the `tr` command have been explained in this tutorial by
using various examples. The ways to search, replace and delete the part of a
text or a file by using this command with different options and patterns have
described here. I hope, this tutorial will help the bash users to learn the
purposes of using this command properly.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
View_all_posts

RELATED LINUX HINT POSTS


* What_are_Double_Parentheses_in_Bash
* Floating_Point_Math_in_Bash
* Bash_Continue_Built-In_Statement
* 10_Most_Important_Things_to_Know_About_Bash_Scripting
* Mastering_Backticks_in_Linux_Bash_Scripts
* Making_a_Bash_Script_Return_with_Different_Return_Codes_on_Exit
* Greater_Than_Numerical_Comparison_in_a_Bash_Script

Linux Hint LLC, [email protected]om
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
