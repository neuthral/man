





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


10 Awesome Awk Command Examples

2 years ago
by Sam_U
Awk command is a powerful tool to process data. It gets input data, manipulates
it, and gives results in standard output. Various operations can be performed
on rows and columns of a file.
Knowing the essentials of the “awk” command is very important when it comes to
processing data efficiently, and this post covers the key features of the “awk”
command. Let’s check the syntax first:
$ awk [options] [file]
Some of the commonly used options are given in the table below:

Option Description
-F     To specify a file separator
-f     Specify the file that contains the “awk” script
-v     To assign variable

Let’s take a look at some examples about the usage of the “awk” command, and
for demonstration, I have made a text file by the name of testFile.txt:

1. How to print a column of a file with the awk command?

The “awk” command can be used to get a specific column of the text file. To
print the content of file use:
$cat testFile.txt
Now, to print the second column of the file, use:
$awk ‘{print $2}’ testFile.txt
To print more than one fields, use the command:
$awk ‘{print $1,$2,$3}’ testFile.txt
 
If you don’t use the comma “,” then the output will be without spaces:
$awk ‘{print $1$2$3}’ testFile.txt

2. How to use regular expression with awk command:

To match the strings or any expression, we use slashes “//,” for instance, if
you want to print the names of people who are studying “History,” then use:
$awk ‘/History/ {print $2}’ testFile.txt
The output is clearly showing that only “Sam” and “Tommy” are studying the
“History” course.

3. How to use the relational expression with the “awk” command:

To match the content of a specific field, relational expression can be used. To
match any string or expression against a field, indicate the field and use the
comparison “~” operator with the pattern as presented in the following command:
$awk ‘$3 ~/is/ {print $2}’ testFile.txt
The above output displaying every field in column 2 against every field that
contains “is” in column 3.
And to get the opposite output of the above command, use the “! ~” operator:
$awk ‘$3! ~/is/ {print $2}’ testFile.txt
For comparison, we can also use operators like greater than “>” and less than
“<” and equal “=” as well:
$awk ‘$4>70 {print $2}’ testFile.txt
The output has printed the names of people who got marks of more than 70.

4. How to use range pattern with awk command:

A range can also be used for search; simply use the comma “,” to separate the
range as presented in the below-mentioned command:
$awk ‘/Joel/, /Marlene/ {print $3}’ testFile.txt
The output shows the subjects of the range from “Joel” to “Marlene” from column
2. We can use the double equal sign “==” to define a range; see the example
below:
$awk ‘$4 == 80, $4 == 90 {print $0}’ testFile.txt
The output displays the names of the people from column 2 for the range of
marks “70 to 80” from column 4.

5. How to combine pattern using logical operator:

The use of logical operators such as OR “||,” AND “&&” allow you to combine
patterns for search. Use the following command
$awk ‘$4>80 && $6>0.4 {print $2}’ testFile.txt
The above command prints people’s names against the fourth field more
significant than 80 and the sixth field greater than 0.4. And only two records
are fulfilling the condition.

6. The awk command special expressions:

There two special expressions, “BEGIN” and “END”:
BEGIN: To perform an action before data is processed
END: To perform an action after the data is processed
$awk ‘BEGIN {print “Processing has begun”}; {print $2}; END {print “Processing
has ended”}’ testFile.txt

7. The useful built-in variable of awk command:

The awk command has various variables that help in data processing:

Variable   Description
NF         It gives the number of fields in the data
NR         It gives the number of the current record
FILENAME   Displays the name of the file that is currently being processed
FS and OFS Field separator and Output Field separator
RS and ORS Separates the record and Output Record Separator

For example:
$awk ‘END{print “The file name is ” FILENAME “has” NF “fields and” NR
“records”}’ testFile.txt
We use “END,” but if you use “BEGIN,” the output would give 0 fields and 0
records.

8. How to change the record separator:

The default separator in the record is usually space; if there is a comma “,”
or dot “.” as your field separator, then use the “FS” option along with the
separator.
Let’s have another file where data fields are separated by a comma colons “:”:
$cat testFile2.txt

$awk ‘BEGIN {FS= “:”} {print $2}’ testFile2.txt
Since the file’s separator is a colon, but the “awk” command even beneficial
for the files like this, simply use the “FS” option.
The “-F” can also be used:
$awk -F “:” ‘{print $2}’ testFile2.txt
The default record separator is “newline,” and to set the record separator to
“:”, use:
$awk ‘BEGIN {RS = “:”}{print $1}’ testFile2.txt

9. Awk Actions:

Awk actions are tiny programs that are surrounded by “{}” brackets and have
more than one statement separated by semi-colons“;”.
The most used statement with the “awk” command is the “print” statement. For
example, to print a text with each record, use text string in quotes:
$awk ‘{“The is a field,” $2}’ testfile.txt
Let’s perform a simple sum operation using awk:
$awk ‘{sum += $4} END {printf “%d\n”, sum}’ testFile.txt

10. Creating an awk program:

Let’s begin with the “awk” programming, the programming given below is simply
doing multiplication:
BEGIN {
i=2
while(j<4)
{
print “The multiplication of 2 with”  j “ is ” i*j;
j++
}
}
Save the program by the name of “myCode.awk” and to run it, open terminal and
type:
$awk -f myCode.awk

Conclusion:

The “awk” command is a handy command to process, scan data of text files, such
as separating any particular field of a file; we use the “awk” command. It
makes it easier to search anything in any form or pattern from the text files.
In this guide, we understand the basics of the “awk” command and its usage. The
“awk” command validates data, generates reports, and even parses files. Using
simple commands “awk” also enables users to write tiny programs to process data
more efficiently.


About the author


Sam U

I am a professional graphics designer with over 6 years of experience.
Currently doing research in virtual reality, augmented reality and mixed
reality.
I hardly watch movies but love to read tech related books and articles.
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
