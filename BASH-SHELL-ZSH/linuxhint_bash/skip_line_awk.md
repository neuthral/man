





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Skip the First Line of a File Using `awk`

2 years ago
by Fahmida_Yesmin
There are various uses of the `awk` command in Linux. For example, it can be
used to print the content of a text file. The first line of many text files
contains the heading of the file, and sometimes, the first line must be skipped
when printing the content of the file. In this tutorial, we will show you how
to accomplish this task by using the `awk` command.

Create a text file

To follow along with this tutorial, create a tab-delimited text file
namedbooklist.txt with the following content. This file contains a list of
books with their corresponding authors. In this tutorial, we will show you how
to print different parts of this file after skipping the first line.
Cybersecurity with bash Paul Troncone, Carl Albing

Command Line Kung Fu Jason Cannon

Linux Command Line Travis Booth

Bash in easy steps Mike McGrath

Unix in easy steps Mike McGrath

Example 1: Skip the first line of a file using NR and the ‘>’ operator

The NR variable indicates the number of records in a file. The following `awk`
command uses the NR variable to skip the first line of a file. The value of NR
is 1 for the first line. The following command will print lines for which the
NR value is greater than 1.
$ cat booklist.txt

$ awk '(NR>1)' booklist.txt
The following output will be produced after running the above commands. The
output includes all lines other than the first line of the file.

Example 2: Skip the first line by using NR and the ‘!=’ operator

The following `awk` command is similar to that in the previous example.
However, the ‘!=’ comparison operator is used here instead of ‘>’.
$ cat booklist.txt

$ awk 'NR!=1' booklist.txt
The following output will be produced after running the above commands. The
output shows all lines other than the first line of the file.

Example 3: Skip the first line of a file by using a conditional statement

The following `awk` command will print the lines of the file if the if
statement is true. Here, the if statement will be true only when the NR value
does not equal 1.
$ cat booklist.txt

$ awk '{if (NR!=1) {print}}' booklist.txt
The following output will be produced after running the above commands. The
output includes all lines except the first line of the file.

Example 4: Print the book names from the file but skip the first line

Two `awk` commands are used in this example to print all book names except the
first. The `awk` command will read the first column from the file based on the
field separator (\t) and send the output to the second `awk` command. The
second `awk` command will print the desired output.
$ cat booklist.txt

$ awk -F "\t" '{print $1}' booklist.txt | awk 'NR!=1 {print}'
The following output will be produced after running the above commands. The
output shows all the book names except for that of the first book.

Example 5: Format the file content after skipping the first line

The ‘-F’ option, NR variable, and printf function are used in the following
`awk` command to generate formatted output after skipping the first line. The
command will divide the file content into columns based on \t, and printf will
print the first and second columns when the NR value is at least 2.
$ cat booklist.txt

$ awk -F '\t' 'NR>=2 {printf "%30s %20s\n", $1, $2}' booklist.txt
The following output will be produced after running the above commands. The
output shows the formatted content of the file, excluding the first line of the
file.

Example 6: Print the book names after skipping the first line using NR and NF

The following `awk` command uses the ‘-F’ option and NR and NF to print the
book names after skipping the first book. The ‘-F’ option is used to separate
the content of the file base on \t. NR is used to skip the first line, and NF
is used to print the first column only.
$ cat booklist.txt

$ awk -F '\t' 'NR>1 && NF=1' booklist.txt
The following output will be produced after running the above commands. The
output includes all the book names in the file except for that of the first
book.

Example 7: Print the formatted author names after skipping the first line

The following `awk` command uses the ‘-F’ option and a conditional statement to
print the author names after skipping the first line. Here, the NR value is
used in the if condition. Here, “Author Name:\n\n” will be printed as the first
line instead of the content from the first line. The author’s names from the
file will be printed for the other values of NR.
$ cat booklist.txt

$ awk -F '\t' ' {if (NR==1) printf "\nAuthor Name:\n\n"; else  printf "%s\n",
$2}' booklist.txt
The following output will be produced after running the above commands. The
output shows the text, “Author Name:” with a newline, and all author names are
printed except the first one.

Conclusion

The first line of a file can be skipped by using various Linux commands. As
shown in this tutorial, there are different ways to skip the first line of a
file by using the `awk` command. Noteably, the NR variable of the `awk` command
can be used to skip the first line of any file.


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
