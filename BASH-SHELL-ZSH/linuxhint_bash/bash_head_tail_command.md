






















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Head and Tail Command

1 year ago
by Fahmida_Yesmin
Many types of commands are available in bash to show the content of a file.
Most commonly used commands are ‘cat’, ‘more’, ‘less’, ‘head’ and ‘tail‘
commands. To read the entire file, ‘cat’, ‘more’, and ‘less‘ commands are used.
But when the specific part of the file is required to read then ‘head‘ and
‘tail‘ commands are used to do that task.
‘head‘ command is used to read the file from the beginning and the ‘tail‘
command is used to read the file from the ending. How you can use ‘head‘ and
‘tail‘ commands with different options to read the particular portion of a file
is shown in this tutorial.
You can use any existing file or create any new file to test the functions of
‘head‘ and ‘tail‘ commands. Create two text files named products.txt and
employee.txt with the following content to show the use of ‘head‘ and ‘tail‘
commands.
products.txt
ID  Type        Brand       Size        Price
01  HDD     Samsung     1TB         $70
02  Monitor         DELL            15”       $60
03  Mouse       A4      N/A     $05
04  Keyboard    Atech       Normal          $10
05  Scanner         HP      N/A     $50
06  Printer     Samsung         N/A     $100
07  Adapter         A4      N/A     $10
08  Monitor         Samsung         17”       $80
employee.txt
ID  Name            Department  Post
S001    John Paul       Sales       Marketing Officer
S002    Wellium Bob     Sales       Sales Executive
E003    Jason           HR      Manager
E004    Jullie          HR      Assistant Manager
E005    Janifer             HR      Programmer

Use of Head Command

By default, the ‘head’ command reads the first 10 lines of the file. If you
want to read more or less than 10 lines from the beginning of the file then you
have to use the ‘-n’ option with the ‘head’ command.

Head Command Syntax

head [option]  [filename]...[filename]
Using the option in the ‘head’ command is optional and the ‘head’ command can
be applied for one or more files.

Head Command Options

The purposes of different `head` command options have explained below.

Option         Purpose
-n or –lines It is used to print the first n number of lines.
-c or –bytes It is used to print the first n number of characters or bytes.
-q or –quiet It is used to print the content of one or more files without
               mentioning the filename in the output.
-v or –verbosIt is used to print the content of one or more files by
               mentioning the filename in the output.


Examples of Head Command

Different uses of the `head` command have shown in the following examples.

Example – 1: Head Command Without Any Option

The products.txt file has 9 lines with the heading. So, the following command
will display all lines of the products.txt file because no option is used with
the ‘head’ command.
$ head products.txt
Output:
The following output will appear after executing the above command.

Example – 2: Head Command with -n Option and Positive Value

The ‘-n’ option with 5 has been used in the following ‘head’ command to print
the first five lines of the products.txt file in the output.
$ head -n 5 products.txt
Output:
The following output will appear after executing the above command.

Example – 3: Head Command with -n Option and Negative Value

The ‘-n’ option with -7 has been used in the following ‘head’ command to print
the content of the products.txt file after omitting the last 7 lines.
$ head -n -7 products.txt
Output:
The following output will appear after executing the above command.

Example-4: Head Command with -c Option

The ‘-c’ option with 67 has been used in the following ‘head’ command to print
the first 67 characters of the products.txt file in the output.
$ head -c 67 state.txt
Output:
The following output will appear after executing the above command.

Example-5: Head Command with -q Option

The following `head` command with the –q option and two files will print the
all content of both files without mentioning the file name.
$ head -q  employee.txt products.txt
Output:
The following output will appear after executing the above command.

Example-6: Head Command with -v Option

The following `head` command with the –v option and two files will print the
all content of both files by mentioning the file names.
$ head -v employee.txt products.txt
Output:
The following output will appear after executing the above command.

Example – 7: Head Command with -n Option and Multiple Files

The particular number of lines from the beginning of one or more files can be
printed by using the -n option and number with the `head` command. The
following command will print the first 2 lines of products.txt and employee.txt
files.
$ head -n 2 products.txt employee.txt
Output:
The following output will appear after executing the above command.

Use of Tail Command

By default, the ‘tail’ command reads the last 10 lines of the file. If you want
to read more or less than 10 lines from the ending of the file then you have to
use the ‘-n’ option with the ‘tail‘ command.

Tail Command Syntax

tail [option]  [filename]...[filename]
Like ‘head’ command ‘tail’ command is also applicable for multiple files and
using the option is optional for the ‘tail’ command.

Tail Command Options

The purposes of different `tail` command options have explained below.

Option         Purpose
-n or –lines It is used to print the last n number of lines.
-c or –bytes It is used to print the last n number of characters or bytes.
-q or –quiet It works similar to the -q option of the `head` command.
-v or –verbosIt works similar to the -v option of the `head` command.
-f or –followIt is used to monitor the log entries written by running
               programs.


Example-1: Tail Command Without Any Option

The employee.txt file has only 6 lines which are less than 10. So, the
following command will display the full content of the employee.txt file.
$ tail employee.txt
Output:
The following output will appear after executing the above command.

Example – 2: Tail Command with -n Option and Positive Value

When you want to read particular lines from the ending of the file then you
have to use the ‘-n’ option with a positive value. The following command will
display the last 2 lines of the employee.txt file.
$ tail -n 2 employee.txt
Output:
The following output will appear after executing the above command.

Example – 3: Tail Command with -n and Negative Value

If you want to omit the specific lines from the beginning then you have to use
the ‘-n’ option with a negative value in the ‘tail’ command. The following
command will display the content of the employee.txt file by omitting 3 lines
from the beginning.
$ tail -n -3 employee.txt
Output:
The following output will appear after executing the above command.

Example – 4: Tail Command with -c Option

The ‘-c’ option with 65 has been used in the following ‘tail’ command to print
the last 65 characters of the employee.txt file in the output.
$ tail -c -65 employee.txt
Output:
The following output will appear after executing the above command.

Example – 5: Tail Command with -f Option

The ‘-f’ and ‘-n’ options with the path of history.log have been used in the
following ‘tail’ command to print the 3 lines of the history.log file in the
output.
$ tail -f -n 3 /var/log/apt/history.log
Output:
The following output will appear after executing the above command.

Example – 6: Tail Command with -n Option and Multiple Files

The following command will display the last 3 lines of products.txt and
employee.txt files.
$ tail -n 3 products.txt employee.txt
Output:
The following output will appear after executing the above command.

Example – 5: Using Head and Tail Commands Together

If you want to read the content from the middle of any file then only the
‘head‘ or ‘tail‘ command can’t solve this problem. You have to use both ‘head‘
and ‘tail‘ commands together to solve this problem. The following command will
read lines from 2 to 6 of the products.txt file. At first, the ‘head’ command
will retrieve the first 6 lines by omitting the last 5 lines for the negative
value and the ‘tail’ command will retrieve the last 5 lines from the output of
the ‘head‘ command.
$ head -n -5 products.txt | tail -n 5
Output:
The following output will appear after executing the above command.

Conclusion

I hope, after practicing the above examples, the bash users will be able to
apply ‘head‘ and ‘tail‘ commands properly.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
View_all_posts

1 Comment


*
  Admin says:
  September_8,_2021_at_10:53_am
  To omit NUM lines from the beginning of a file when using the tail command,
  the correct way is to use tail -n +NUM file.txt as described by the manual
  page. Your article implies that this is done by using tail -n -NUM file.txt
  (a negative number).
  This will not produce the desired behaviour, and the reason that it appears
  to work on the screenshot in the article is because it is actually just
  working as if the negative sign is not even there, i.e. as if you just
  specified NUM.
  That means it is outputting the last 3 lines of the file, but since the file
  only has 6 lines that is the same as omitting the first 3 lines so this
  mistake is not immediately apparent unless you use a different number than 3,
  if you used `-n -2` for example it would only print the 2 last lines instead
  of the 4 last lines which would be expected if you are trying to omit the
  first 2 lines in a 6 line file. To correct it the only thing you need to do
  is change the usage of negative with tail to usage of +.
  For the head command, using negative is correct. A negative number is only a
  mistake when used with the tail command, so references to using negative with
  head do not need to be changed.
  — Lenny


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
