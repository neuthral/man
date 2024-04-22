





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Using the “awk” Command to Print the Last Column from a File

2 years ago
by Aqsa_Yasin
“awk” is a very powerful Linux command that can be used with other commands as
well as with other variables. This command is essentially used to read the
content of a file. The process of file reading has never been this much easier
as it is with this efficient command. File reading and writing are very
repeatedly used especially if you are a programmer. The read file can then be
used to process its content, to modify it, or even to simply print it.
However, there are situations in which you do not intend to read the entire
content of that file rather you are only concerned with a specific portion of
that file. In such a situation, it is highly not recommended to read the entire
file since it will occupy extra space and will also take a longer time for
processing rather you should directly hit that particular portion of that file.
In this article, we aim to walk you through the different methods of using the
“awk” command to print the last column from a file.

Different Ways of using the “awk” Command to Print the Last Column from a File:

There are two different methods in which we can use the “awk” command to print
the last column from a file. Although, these two methods can be used
interchangeably because after all, they render the very same output, however,
the first method is more suitable for the situation where you know the exact
number of columns of a file and the second method is helpful when the total
number of columns is unknown. Let us take a look at both these methods one by
one.
Note: We have used Linux Mint 20 for demonstrating both of these methods,
however, you are free to select any flavor of Linux of your choice.

Method # 1: When you know the Total Number of Columns of a File:

This method can be used when you know the exact number of columns in a file
e.g. 3, 5, 10, etc. For demonstrating this method, the following steps should
be performed in the specified order:
Create a text file with any name of your choice in your Home folder. In this
scenario, we have named it as awk.txt. Now double click on this file to open it
and type the data shown in the image below in your text file. There are a total
of three different columns and the columns are separated from each other by tab
space. You can also type any random data of your choice.
After creating this file, you have to save it and close it. Now launch the
terminal in Linux Mint 20 by clicking on its icon located on the taskbar. The
Linux Mint 20 terminal is also shown in the following image:
Now type the below-mentioned command in your terminal and then press the Enter
key to execute it:
$ awk ‘{print $ColNum}’ file.txt
Here, you need to replace ColNum with the column number of the last column. For
example, the text file that we have created has a total of three columns which
means that the column number of the last column will be 3. Since our goal is to
only print the last column of this file, so we have replaced ColNum with 3.
Whenever a column number is proceeded by the “$” symbol, then this means that
we want to access the values of that column. Moreover, you also have to replace
“file” with the exact name of your text file. In our case, the file name was
awk.txt.
As soon as you will hit the Enter key, all the values of the last column of the
file awk.txt will appear on your terminal as shown in the following image. The
awk command will read this column whereas the print command will be responsible
for displaying its values on the terminal.

Method # 2: When the Total Number of Columns of a File is Unknown:

This method is generally used when you do not know about the total number of
columns in a file. For printing the last column of a file through this method,
you will have to proceed as follows:
We are using the same text file that we have created for the method above. All
we have to do is to launch the terminal and then type the following command in
it:
$ awk ‘{print $(NF)}’ file.txt
Here, NF is a variable whose job is to explicitly print the last column from a
file. For example, if there are 10 or 20 or even more columns in a file but you
do not know their exact number and you still want to access the last column,
then this variable can prove to be very helpful for you. Again, you need to
replace “file” with the name of your text file. In our case, since we have used
the same file as that of Method # 1, therefore, we have replaced file.txt with
awk.txt.
After typing this command in your terminal, you need to run it by pressing the
Enter key. You will notice that the output of this command is identical to the
output of the command used in the method above i.e. the last column of the text
file which contained the year data has been successfully printed on the
terminal.

Conclusion:

In this article, we gave you the guidance about printing only the last column
from a file while making use of the “awk” command. There are a lot more aspects
of this command which can be explored in detail i.e. this command can also be
used in conjunction with other different commands to render a different kind of
output. However, for the scope of today’s discussion, our concern was only to
demonstrate its usage for printing the last column from a file. We presented to
you the two different ways of doing the same thing. Now it entirely depends on
your situation that which of these methods you choose to follow.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
