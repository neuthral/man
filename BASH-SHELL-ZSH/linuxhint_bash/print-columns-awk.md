





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to print a range of columns using the `awk` command

2 years ago
by Fahmida_Yesmin
The `awk` command is one of many commands that can be used to print a range of
columns from tabular data in Linux. The `awk` command is can be used directly
from the terminal by executing the `awk` script file. In this tutorial, we will
show you how to print a range of columns from tabular data.

Example 1: Print a range of columns from a command output

The following command will print the second, third, and fourth columns from the
command output, ‘ls -l‘. Here, the column numbers are stated explicitly, but a
more efficient command for printing the same range of columns is shown in the
next example.
$ ls -l | awk '{ print $2, $3, $4 }'
The following output is produced by the command above.

Example 2: Print the range of columns from a file by using afor loop

To follow along with this example and the other examples in this tutorial,
create a text file named marks.txt with the following content:
ID CSE203 CSE102 CSE202
1109 78 87 79
1167 67 81 70
1190 56 61 69
1156 89 55 78
199 54 66 58
The following `awk` command will print the first three columns of marks.txt.
The for loop is used to print the column values, and the loop includes three
steps. The NF variable indicates the total numbers of fields or columns of the
file.
$ cat marks.txt
$ awk '{for(i=1;i<=NF-1;i++) printf $i" "; print ""}' marks.txt
The following output will be produced by running the command. The output shows
the student IDsand the marks for CSE203 and CSE102.

Example 3: Print the range of columns by defining starting and ending variables

The following `awk` command will print the first three columns from the command
output ‘ls -l’ by initializing the starting and ending variables. Here, the
value of the starting variable is 1, and the value of the ending variable is 3.
These variables are iterated over in a for loop to print the column values.
$ ls -l | awk ' BEGIN { first = 1; last = 3 }
{ for (i = first; i < last; i++) { printf("%s ", $i) } print $last }'
The following output will appear after running the command. The output shows
the first three column values of the output, ‘ls -l’.

Example 4: Print a range of columns from a file with formatting

The following `awk` command will print the first three columns of marks.txt
usingprintf and output field separator (OFS). Here, the for loop includes three
steps, and three columns will be printed in sequence from the file. OFS is used
here to add space between columns. When the counter value of the loop (i)
equals theending variable, then a newline(\n) is generated.
$ cat marks.txt
$ awk -v start=1 -v end=3 '{ for (i=start; i<=end;i++) printf("%s%s",
 $i,(i==end) ? "\n" : OFS) }' marks.txt
The following output will be generated after running the above commands.

Example 5: Print the range of columns from a file using a conditional statement

The following `awk` command will print the first and last columns from a file
by using a for loop and an if statement. Here, the for loop includes four
steps. The starting and ending variables are used in the script to omit the
second and third columns from the file by using the if condition. The OFS
variable is used to add space between the columns, and the ORS variable is used
to add a newline(\n) after printing the last column.
$ cat marks.txt
$ awk -v start=2 -v end=3 '{ for (i=1; i<=NF;i++)
if( i>=start && i<=end) continue;
else printf("%s%s", $i,(i!=NF) ? OFS : ORS) }' marks.txt
The following output will appear after running the above commands. The output
shows the first and last columns of marks.txt.

Example 6: Print the range of columns from a file using the NF variable

The following `awk` command will print the first and last columns from the file
by using an NF variable. No loops or conditional statements are used to print
the column values. NF indicates the number of fields. There are four columns in
marks.txt. $(NF-3) defines the first column, and $NF indicates the last column.
$ cat marks.txt
$ awk '{print $(NF-3)" "$NF}' marks.txt
The following output is produced by running the above commands. The output
shows the first and last columns of marks.txt.

Example 7: Print the range of columns from a file using substr() and index()

The index() function returns a position if the second argument value exists in
the first argument value. The substr() function can take three arguments. The
first argument is a string value, the second argument is the starting position,
and the third argument is the length. The third argument of substr() is omitted
in the following command. Because the column starts from $1 in the `awk`
command, the index() function will return $3, and the command will print from
$3 to $4.
$ cat marks.txt
$ awk '{print substr($0,index($0,$3))}' marks.txt
The following output will be produced by running the above commands.

Example 8: Sequentially print a range of columns from a file using printf

The following `awk` command will print the first, second, and third columns of
marks.txt by setting enough space for 10 characters.
$ cat marks.txt
$ awk '//{printf "%10s %10s %10s\n",$1,$3,$2 }' marks.txt
The following output will be produced by running the above commands.

Conclusion

There are various ways to print the range of columns from the command output or
a file. This tutorial shows how `awk` command can help Linux users to print
content from tabular data.


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
