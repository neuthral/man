





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Print the First Column or Last Column or Both Using `awk`

2 years ago
by Fahmida_Yesmin
Linux’s `awk` command is a powerful utility for different operations on text
files such as search, replace, and print. It is easy to use with tabular data
because it automatically divides each line into fields or columns based on the
field separator. When you work with a text file that contains tabular data and
want to print the data of a particular column, then the `awk` command is the
best option. In this tutorial, we will show you how to print the first column
and/or last column of a line or text file.
Print the first column and/or last column of a command output
Many Linux commands such as the ‘ls’ command generate tabular outputs. Here, we
will show you how to print the first column and/or last column from the output
of the  ‘ls -l’ command.

Example 1: Print the first column of a command output

The following `awk` command will print the first column from the output of the
‘ls -l’ command.
$ ls -l

$ ls -l | awk '{ print $1 }'
The following output will be produced after running the above commands.

Example 2: Print the last column of a command output

The following `awk` command will print the last column from the output of the
‘ls -l’ command.
$ ls -l

$ ls -l | awk '{ print $NF }'
The following output will be produced after running the above commands.

Example 3: Print the first and last columns of a command output

The following `awk` command will print the first and last columns from the
output of the ‘ls -l’ command.
$ ls -l

$ ls -l | awk '{ print $1,  $NF }'
The following output will be produced after running the above commands.

Print the first column and/or last column of a text file

Here, we will show you how to use the `awk` command to print the first column
and/or last column of a text file.

Create a text file

To follow along with this tutorial, create a text file named customers.txt with
the following content. The file contains three types of customer data: name
with id, email, and phone number. The tab character (\t) is used to separate
these values.
Name Email Phone

Jonathon Bing - 1001 [email protected] 01967456323

Micheal Jackson - 2006 [email protected] 01756235643

Janifer Lopez - 3029 [email protected] 01822347865

John Abraham - 4235 [email protected] 01590078452

Mir Sabbir - 2756 [email protected] 01189523978

Example 4: Print the first column of a file without using a field separator

If no field separator is used in the `awk` command, then a space is used as the
default field separator. The following `awk` command will print the first
column by using the default separator.
$ cat customers.txt

$ awk '{print $1}' customers.txt
The following output will be produced after running the above commands. Note
that the output shows only the customer’s first name because the space is
applied as the field separator. The solution to this problem is shown in the
next example.

Example 5: Print the first column of a file with a delimiter

Here, \t is used as a field separator to print the first column of the file.
The ‘-F’ option is used to set the field separator.
$ cat customers.txt

$ awk -F '\t' '{print $1}' customers.txt
The following output will be produced after running the above commands. The
content of the file is divided into three columns based on \t. Therefore, the
customer’s name and id are printed as the first column. If you want to print
the customer’s name without the id, then continue to the next example.

If you want to print the customer’s name without the id, then you have to use
‘-‘ as a field separator. The following `awk` command will print the customer’s
name only as the first column.
$ cat customers.txt

$ awk -F '-' '{print $1}' customers.txt
The following output will be produced after running the above commands. The
output includes the full names of the customers without their ids.

Example 6: Print the last column of a file

The following `awk` command will print the last column of customers.txt.
Because no field separator is used in the command, the space will be used as a
field separator.
$ cat customers.txt

$ awk '{print $NF}' customers.txt
The following output will be produced after running the above commands. The
last column contains phone numbers, as shown in the output.

Example 7: Print the first and last columns of a file

The following `awk` command will print the first and last columns of
customers.txt. Here, tab (\t) is used as the field separator to divide the
content into columns. Here, tab (\t) is used as a separator for the output.
$ cat customers.txt

$ awk -F "\t"  '{print $1 "\t"  $NF}' customers.txt
The following output will appear after running the above commands. The content
is divided into three columns by \t; the first column contains the customer’s
name and id and the second column contains the phone number. The first and last
columns are printed by using \t as a separator.

Conclusion

The `awk` command can be applied in different ways to get the first column and/
or last column from any command output or from tabular data. It is important to
note that a field separator is required in the command, and if one is not
provided, then the space is used.


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
