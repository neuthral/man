





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Split a File of Strings with Awk

3 years ago
by Karim_Buzdar
The Linux awk command(abbreviated from the names of the developers; Aho,
Weinberger, and Kernighan) is a great way to process and analyze a file of
strings. In order for the files to be more informative, they have to be
organized in the form of rows and columns. Then, you can use awk on these files
to:

* Scan the files, line by line.
* Split each line into fields/columns.
* Specify patterns and compare the lines of the file to those patterns
* Perform various actions on the lines that match a given pattern

In this article, we will explain the basic usage of the awk command and how it
can be used to split a file of strings. We have performed the examples from
this article on a Debian 10  Buster system but they can be easily replicated on
most Linux distros.

The sample file we will be using

The sample file of strings that we will be using in order to demonstrate the
usage of the awk command is as follows:
This is what each column of the sample file indicates:

* The first column contains the name of employees/teachers in a school
* The second column contains the subject that the employee teaches
* The third column indicates whether the employee is a professor or assistant
  professor
* The fourth column contains the pay of the employee


Example 1: Use Awk to print all lines of a file

Printing each and every line of a specified file is the default behavior of the
awk command. In the following syntax of the awk command, we are not specifying
any pattern that awk should print, thus the command is supposed to apply the
“print” action to all the lines of the file.
Syntax:
$ awk '{print}’ filename.txt
Example:
In this example, I am telling the awk command to print the contents of my
sample file, line by line.
$ awk '{print}' sample_file.txt

Example 2:  Use awk to print only the lines that match a given pattern

With awk, you can specify a pattern and the command will print only the lines
matching that pattern.
Syntax:
$ awk '/pattern_to_be_matched/ {print}' filename.txt
Example:
From the sample file, if I want to print only the line(s) that contain the
variable ‘B’, I can use the following command:
$ awk '/B/ {print}' sample_file.txt
To make the example more meaningful, let me print only the information about
employees that are ‘professor’s.
$ awk '/professor/ {print}' sample_file.txt
The command only prints the lines/entries that contain the string “professor”
thus we have more valuable information derived from the data.

Example 3. Use awk to split the file so that only specific fields/columns are
printed

Instead of printing the whole file, you can make awk to print only specific
columns of the file. Awk treats all words, separated by white space, in a line
as a column record by default. It stores the record in a $N variable. Where $1
represents the first word, $2 stores the second word, $3 the fourth, and so on.
$0 stores the whole line so the who line is printed, as explained in example 1.
Syntax:
$ awk '{print $N,….}' filename.txt
Example:
The following command will print only the first column(name) and the second
column(subject) of my sample file:
$ awk '{print $1, $2}' sample_file.txt

Example 4: Use Awk to count and print the number of lines in which a pattern is
matched

You can tell awk to count the number of lines in which a specified pattern is
matched and then output that ‘count’.
Syntax:
$ awk '/pattern_to_be_matched/{++cnt} END {print "Count = ", cnt}'
filename.txt
Example:
In this example, I want to count the number of persons teaching the subject
“english”. Therefore I will tell the awk command to match the pattern “english”
and print the number of lines in which this pattern is matched.
$ awk '/english/{++cnt} END {print "Count = ", cnt}' sample_file.txt
The count here suggests that 2 people are teaching english from the sample file
records.

Example 5: Use awk to print only lines with more than a specific number of
characters

For this task, we will be using the built-in awk function called “length”. This
function returns the length of the input string. Thus, if we want awk to print
only lines with more than, or even less than, the number of characters, we can
use the length function in the following manner:
For printing lines with characters greater than a number:
$ awk 'length($0) > n' filename.txt
For printing lines with characters less than a number:
$ awk 'length($0) < n' filename.txt
Where n is the number of characters you want to specify for a line.
Example:
The following command will print only the lines from my sample file who have
characters more than 30:
$ awk 'length($0) > 30' sample_file.txt

Example 6: Use awk to save the command output to another file

By using the redirection operator ‘>’, you can use the awk command to print its
output to another file. This is the way you can use it:
$ awk 'criteria_to_print’' filename.txt > outputfile.txt
Example:
In this example, I will be using the redirection operator with my awk command
to print only the names of the employees(column 1) to a new file:
$ awk '{print $1}' sample_file.txt > employee_names.txt
I verified through the cat commands that the new file only contains the names
of the employees.

Example 7: Use awk to print only non-empty lines from a file

Awk has some built-in commands that you can use to filter the output. For
example, the NF command is used to keep a count of the fields within the
current input record. Here, we will use the NF command to print only the non-
empty lines of the file:
$ awk 'NF > 0' sample_file.txt
Obviously, you can use the following command to print the empty lines:
$ awk 'NF < 0' sample_file.txt

Example 8: Use awk to count the total lines in a file

Another built-in function called NR keeps a count of the number of input
records(usually lines) of a given file. You can use this function in awk as
following to count the number of lines in a file:
$ awk 'END { print NR }' sample_file.txt
This was the basic information you need to start with splitting files with the
awk command. You can use the combination of these examples to fetch more
meaningful information from your file of strings through awk.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
