





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Insert a Line after the Match using `sed`?

2 years ago
by Fahmida_Yesmin
One of the useful and powerful commands of Linux is the “sed” command. This
command is used to perform different types of tasks in Linux, such as insert,
update, and delete a particular text or line based on the match. You can insert
a text in a string or a file in different ways by using the “sed” command.
How to insert a line after finding a match in a string or a line is shown in
this tutorial.

Insert a line in the String

A new line can be inserted after any string value using the “sed” command if
the pattern defined in the command matches with any part of the string value.
The following example shows how a new line can be added after a string value if
a particular string exists anywhere in the string value.

Example-1: Insert a line in a string after finding a match

The following command will search “inng” in the string, “I like programming”,
and a line of text, “Do you like programming?” will be inserted after the
string if the searching string exists.
Here, the “&” character is used to insert the line after the string.
$ echo "I like programming." | sed 's/inng/& Do you like programming?/'
The following output shows that “inng” does not exist in the string and no line
is inserted after the string.

The following command will search “ing.” in the string, “I like programming”
and it exists in the string.
$ echo "I like programming." | sed 's/ing./& Do you like programming?/'
The following output shows that the new line is added after the string.

Insert a line in a File

There are two ways to insert a line after a match is found in a file that is
mentioned below. When the “sed” command is used without the “-i option”, then
the content of the file will remain unchanged, and the output will show the
file content with the inserted newline. You have to use the “-i” option with
the “sed” command to insert the new line permanently in the file if the
matching pattern exists in the file.
A. Using “a” in the “sed” command
The “a” can be used in the search pattern of the “sed” to append one or more
lines in a file after the line where the searching pattern matches or after a
particular line number.
B. Using “i” in the “sed” command
The “i” can be used in the search pattern of the “sed” command to insert one or
more lines in a file before the line where the searching pattern matches.
Insert line(s) in a file based on the pattern:
Create a tab-delimited text file named products.txt with the following content
to show the uses of the above flag in the “sed” command.
products.txt
ID        Name

01        Whip cream

02        Cocoa Powder

03        Sugar

04        Egg

05        Flour

Example-2: Insert a line after a particular line number using the “a”

The following commands show how a new line can be added, after a particular
line number of the products.txt file, based on the pattern used in the “sed”
command.
Here, the first command will show the existing content of the file. The “sed”
command will append the text, “b01 Baking powder”, after the first two lines of
the file. The last command is used to check that the file content is changed or
not.
$ cat products.txt

$ sed '2 a b01\tBaking powder' products.txt

$ cat products.txt
The following output will appear after running the above command.

Example-3: Insert a line after the last line using the “a”

The following command shows the way to append a new line after the last line of
the file. The first and last command shows the existing content of the file
before and after executing the “sed” command. The “$” symbol is used in the
pattern of the “sed” command to mention the last line of the file.
$ cat products.txt

$ sed '$ a b01\tBaking powder' products.txt

$ cat products.txt
The following output will appear after running the above command.

Example-4: Insert a line anywhere in the file after matching a pattern using
the “a”

The following “sed” command shows how a new line can be added anywhere in the
file based on the matching pattern. The pattern used in the “sed” command will
search any line starting with “s01”, and add the new string after it. The
fourth line of the file starts with “s01”, and the new line will be inserted
after that line.
$ cat products.txt

$ sed '/^s01.*/a b01\tBaking Powder' products.txt

$ cat products.txt
The following output will appear after running the command.

The following “sed” command will search any line that ends with “Powder” and
insert the new line after it. The third line of the file ends with “Powder”.
So, the new line will be inserted after that line.
$ cat products.txt

$ sed '/Powder$/a b01\tBaking Powder' products.txt

$ cat products.txt
The following output will appear after running the above commands.

Example-5: Insert multiple lines after the matching pattern using “a”

The following “sed” command shows the way to add multiple lines inside the
content of a file based on the matching pattern.
Here, two lines will be added after the third line, according to the pattern.
$ cat products.txt

$ sed '/^[a-c]/a b01\tBaking Powder\nb02\tBaking Soda' products.txt

$ cat products.txt
The following output will appear after running the above commands.

Example-6: Insert a line after matching a pattern using the “I”

$ cat products.txt

$ sed '/cream/i b01\tBaking Powder' products.txt

$ cat products.txt
The following output will appear after running the above commands.

Example-7: Insert a line permanently after the matching pattern using the “-i”
option

The following “sed” command shows how to change the content of the file
permanently. The “i” option is used with the “sed” command to insert a new line
in the file based on the pattern.
$ cat products.txt

$ sed -i '/e$/a g01\tGhee' products.txt

$ cat products.txt
The following output will appear after running the above commands.

Conclusion:

The ways of inserting two or more lines in a file by using the “sed” command
with pattern have been shown in this tutorial to help the reader apply this
command for inserting lines in the temporarily or permanently based on the
pattern.


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

Linux Hint LLC, [email protected]
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
