





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Cut Command with Examples

1 year ago
by Aqsa_Yasin
The cut command is used to extract the specific portion of text in a file. Many
options can be added to the command to exclude unwanted items. It is mandatory
to specify an option in the command otherwise it shows an error. In this
article, we will throw light on each option of the cut command.

Syntax

Cut [option] … [filename]..
To get the version of cut in Linux, we can use the below mention methods.
$ cut –version.

Extracts Bytes from the Text

To extract bytes from the file or a single string, we will use the ‘-b’ option
in the command with a number or list of numbers that are separated by commas in
the command. The string is introduced before the pipe and this pipe will make
that string as an input for the cut function described after the pipe. Consider
a string of alphabets. And we want to fetch a single letter that is present on
a specific byte that is 12.
$ echo ‘abcdefghijklmnop’ | cut –b 12
From the output, you can see that character ‘l’ is present on the 12th byte of
a string. Now, we will provide more than one byte on the same string. This list
will be defined with separation of commas. Let’s have a look.
$ echo ‘abcdefghijklmnop’ | cut –b 1,8,12

Extracts Bytes from the File

List without ranges
To extract a portion of text from a particular file, we will apply the same
method of using –b in the command. A list will be added just like the above
example. Consider a file named tool.txt.
$ Cat tool.txt
Now, we will apply a command to fetch characters on the first three bytes from
the text in the file. This extraction will be done on each line of the file.
$ cut –b 1,2,3 tool.txt
The output reveals that the first three characters will be shown in the output.
Whereas, others are deducted.
List with ranges
The range of bytes is introduced by using a hyphen (-) between two bytes. It is
necessary to provide numbers in the command either in the form of range or
without because if the number is missing, then the system will show an error.
Consider the same file. Here, we have applied two ranges separated by commas.
$ cut –b 1-2, 5-8 tool.txt
From the output, we can see that the words from range 1-2 and 5-8 are present.
If we want to get output from the first byte till the end, then 1- is used. By
default, the first to last byte of a line is shown as output.
$ cut –b 1- tool.txt
If we use 4- instead of 1-, then it will show the output starting from the 4th
byte to the last byte of a line in a file.
$ cut –b 4- tool.txt
It is visible now that in some strings, at the 4th bit, there is a space
between characters. This space is also extracted. For instance, Mac OS has
space at the 4th byte, so it is also counted.

Extract Text by Using Columns

To extract the characters from the text, we use –c in the command. It also
contains either a range of numbers or a list that is separated by commas like
in the bytes procedure. Spaces between the words are treated as characters.
Consider the same above file to elaborate on the example.
$ cut –c1 tool.txt
Moving forward, here a list of numbers is used with three numbers. So, these
three numbers will be extracted from all the lines in a file.
$ cut –c 3,5,7 tool.txt
We will also consider another example for this purpose having a single number.
Let’s have a file  named cutfile2.txt.
$ cat cutfile2.txt
In this file, we will apply the command to cut and extract the words starting
from the start till the number that is 5th.
$ cut –c 5- cutfile2.txt
From the output, you can view that the first 5 characters are selected. In the
4th line, you will notice that the space between the two words is also counted.

Extract Text by Using Field

Cut command provides the output in a limit. It is useful for the fixed length
of a line in a file. Whereas, some lines in the files don’t contain fixed
lines. To make it precisely relevant, we will use fields instead of columns.
While using –f, ranges are not defined. As a default, a tab is used by cut as a
field delimiter. But to add other delimiters we use -d in the command.

Syntax

$ Cut -d "delimiter" -f (number) filename.txt
By using –d and then delimiter then we add –f and the number in the command.
Now, consider the given example. If –d is used then space will be considered as
a delimiter. The words before space will be printed. You can see the output by
using these lines of command. In the below example, there is a string and we
want to cut the word ‘cut’ here. As it is after space, we will define the space
delimiter and the field number that is 2. Here we go with the command.
$ echo “Linux cut command is useful” | cut –d ‘ ‘ –f 2
Now, we will apply this field-delimiter concept on a file.
$ Cut –d “ “ –f 1 cutfile2.txt
Now, consider another example in which we will use ‘:’ as a delimiter in the
command. The input is introduced with a directory.
$ cat /etc/passwd
Apply the delimiter command with –f and the number.
$ cut –d ‘:’ –f1 /etc/passwd
From the output, you will see that the text before the colon is displayed as a
resultant.

An – -output-delimiter 

In the cut command, the input delimiter is the exactly same as the output
delimiter. But to customize it, we will use a keyword of – – output-delimiter
with adding field number. Consider a file cutfile1.txt.
$ cat cutfile1.txt
Here, we want to add the ‘$$’ sign between each word of the first sentence. So,
we will add fields from 1 to 7. As 7 words are present in the first line.
$ cut –d “ “ –f 1,2,3,4,5,6,7 cutfile1.txt - - output-delimiter= ’ $$ ‘
From the output, it is clear that where the space was present it is now
replaced with the double dollar sign we have written in the command. If we
apply the same command on the same file, only the fields are changed we enter
only starting and ending words. You will see that the delimiter”@” will be only
present between these two words instead of appearing in between each word of a
line in the file.
$ cut –d “ “ –f 1,18 cutfile1.txt - -output-delimiter= ’@’

Use of –Complement in Cut Command

–complement can be used with other options as well like –c and –f. As the name
indicates, the output is a complement of the input. Consider an example in
which we have used 5 numbers to cut the column.
$ cut - -complement –c 5 cutfile2.txt

Conclusion

The specific part of the text can be extracted by using bytes, columns, and
fields in the cut command. Each option has different beneficiary things that
differentiate it from others. In this article, we have tried to explained the
uses of the cut command with examples.


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
