





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to delete empty lines using sed

1 year ago
by Adnan_Shabbir
There are two possible methods to delete empty lines from a text file using
sed; the methods are listed below and are discussed in detail in the upcoming
part of this guide.

* Method 1: How to delete all empty lines in a text file using sed
* Method 2: How to delete specific lines from text file using sed


Method 1: How to delete all empty lines in a text file using sed

Before digging into the depth of this method, let’s understand the syntax to
delete empty lines using sed:
Syntax
sed [options] ‘/^$/d’ [file name]
The ‘/^$/d’ is the core part of this command; where “^” symbol shows that the
deletion must be executed from the beginning means from first line; “$”
represents that it must go till the last line of the text file and “d” shows
that deletion is in progress.
This section will guide you to delete all the lines in a text file with the
help of stream editor (sed):
We have created a text file “delete.txt; firstly, get the content of this file
using “cat” command as given below and we have used “-n” option with it, so
that we can get the line numbers too:
It is observed that there are multiple empty lines, and they are affecting the
aesthetics of this text file and readers may not pay attention to such content.
$ cat -n delete.txt
 Text Description automatically generated  Text Description automatically
generated
So, to avoid the above stated situation; you must remove the empty lines to
streamline the reading process; the command mentioned below will remove all
these lines from the “delete.txt” file.
Now you can notice that the empty lines are washed out and only those lines are
printed that contains some text, but the result is only displayed on terminal
while the original file remains the same:
$ sed ‘/^$/d’ delete.txt
 Text Description automatically generated  Text Description automatically
generated
If you want to remove the empty lines and update the original file too then you
must use in-place option “-i” and the below-mentioned command will help you to
do so:
$ sed -i ‘/^$/d’ delete.txt
 Text Description automatically generated  Text Description automatically
generated

Method 2: How to delete selected empty lines in a text file using sed

The syntax to delete specific lines in a text file is written below:
Syntax
sed [options] ‘(line-number)d’ [filename]
The main part of syntax on which the command relies is “(line-number)d’”; you
have to put the exact line number of empty line in “(line-number)” and the
letter “d” shows the inserted line number will be deleted:
You can delete some specific lines inside a text file using sed command; we
have created a new text file “new.txt” for this section. For instance, the
output of below command shows that line number “2” is empty:
$ cat -n newfile.txt
 Text Description automatically generated  Text Description automatically
generated
And if you want to run the command to delete this line only then you have to
specify the line number like we did in the command mentioned below:
$ sed ‘2d’ newfile.txt
 Text Description automatically generated  Text Description automatically
generated
You can also delete consecutive lines by using this method; for example, the
“new.txt” file has 3 empty lines “4,5,6” as can be seen in the image below:
$ cat -n new.txt
 Text Description automatically generated  Text Description automatically
generated
To remove these three consecutive lines; you must insert “,” between the
starting and ending line numbers as can be seen in the command below:
$ sed ‘4,6d’ new.txt
 Text Description automatically generated  Text Description automatically
generated
Lastly, you can also use in place option “-i” to save the changes permanently
to the file as without this option the sed command prints the result on the
terminal as we have modified the above command to use it with “-i” option:
$ sed -i ‘4,6d’ new.txt
 Text Description automatically generated  Text Description automatically
generated

Conclusion

Ubuntu supports multiple ways to manipulate the data in a text file; for
instance, you can use the default text editor of Ubuntu, the nano editor etc.
However, the sed command line utility of Ubuntu is leading all these editors
because of its functionalities like accessing the file from the terminal and
making changes without opening it. In this article, we have used sed command to
remove the empty lines from the text file and described two methods for this
operation. “Method 1” is suitable specifically when you have hundreds of lines
in a text file and you want to delete all empty lines at once: On the other
hand, “Method 2” is suitable for deleting the empty lines in a small document
where you can delete lines one by one. However, you have to look for empty
lines yourself, if you want to follow “Method 2”: So, if the comparison is
drawn between both methods, “Method 1” outperforms “Method 2” about deletion of
empty lines.


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
