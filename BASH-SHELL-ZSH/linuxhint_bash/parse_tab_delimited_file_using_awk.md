





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Parse the Tab-Delimited File Using `awk`

2 years ago
by Fahmida_Yesmin
`tab` is used as a separator In the tab-delimited file. This type of text file
is created to store various types of text data in a structured format.
 Different types of command exist in Linux to parse this type of file.  `awk`
command is one of the ways to parse the tab-delimited file in different ways.
The uses of the `awk` command to read the tab-delimited file has shown in this
tutorial.

Create a tab-delimited file:

Create a text file named users.txt with the following content to test the
commands of this tutorial. This file contains the user’s name, email, username,
and password.
users.txt
Name                Email                        Username              
Password

Md. Robin          
[email protected]               robin89                563425

Nila Hasan         [email protected]                nila78                
245667

Mirza Abbas        
[email protected]               mirza23                534788

Aornob Hasan       [email protected]              arnob45                778473

Nuhas Ahsan        
[email protected]               nuhas34                563452

Example-1: Print the second column of a tab-delimited file using the -F option

The following `sed` command will print the second column of a tab-delimited
text file. Here, the ‘-F’ option is used to define the field separator of the
file.
$ cat users.txt

$ awk -F '\t' '{print $2}' users.txt
The following output will appear after running the commands. The second column
of the file contains the user’s email addresses, which are displaying as
output.

Example-2: Print the first column of a tab-delimited file using the FS variable

The following `sed` command will print the first column of a tab-delimited text
file. Here, FS ( Field Separator) variable is used to define the field
separator of the file.
$ cat users.txt

$ awk '{ print $1 }' FS='\t' users.txt
The following output will appear after running the commands. The first column
of the file contains the user’s names, which are displaying as output.

Example-3: Print the third column of a tab-delimited file with formatting

The following `sed` command will print the third column of the tab-delimited
text file with formatting by using the FS variable and printf. Here,
the FS variable is used to define the field separator of the file.
$ cat users.txt

$ awk 'BEGIN{FS="\t"} {printf "%10s\n", $3}' users.txt
The following output will appear after running the commands. The third column
of the file contains the username that has been printed here.

Example-4: Print the third and fourth columns of the tab-delimited file by
using OFS

OFS (Output Field Separator) is used to add a field separator in the output.
The following `awk` command will divide the content of the file based on tab
(\t) separator and print the 3rd and 4th columns using the tab(\t) as a
separator.
$ cat users.txt

$ awk -F "\t" 'OFS="\t" {print $3, $4 > ("output.txt")}' users.txt

$ cat output.txt
The following output will appear after running the above commands. The 3rd and
4th columns contain the username and password, which have been printed here.

Example-5: Substitute the particular content of the tab-delimited file

sub() function is used in `awk to command for substitution. The following `awk`
command will search the number 45 and substitute with the number 90 if the
searching number exists in the file. After the substitution, the content of the
file will be stored in the output.txt file.
$ cat users.txt

$ awk  -F "\t"'{sub(/45/,90);print}' users.txt > output.txt

$ cat output.txt
The following output will appear after running the above commands. The
output.txt file shows the modified content after applying the substitution.
Here, the content of the 5th line has modified, and ‘arnob45’ is changed to
‘arnob90’.

Example-6: Add string at the beginning of each line of a tab-delimited file

In the following, the `awk` command, the ‘-F’ option is used to divide the
content of the file based on the tab(\t). OFS has used to add a comma(,) as a
field separator in the output. sub() function is used to add the string ‘—→’ at
the beginning of each line of the output.
$ cat users.txt

$ awk -F "\t" '{{OFS=","};sub(/^/, "---->");print $1,$2,$3}' users.txt
The following output will appear after running the above commands. Each field
value is separated by comma(,) and a string is added at the beginning of each
line.

Example-7: Substitute the value of a tab-delimited file by using the gsub()
function

gsub() function is used in the `awk` command for global substitution. All
string values of the file will replace where the searching pattern matches. The
main difference between the sub() and gsub() functions is that sub() function
stops the substitution task after finding the first match, and the gsub()
function searches the pattern at the end of the file for substitution. The
following `awk` command will search the word ‘nila’ and ‘Mira’ globally in the
file and substitute all occurrences by the text, ‘Invalid Name’, where the
searching word matches.
$ cat users.txt

$ awk  -F ‘\t’ '{gsub(/nila|Mira/, "Invalid Name"); print}' users.txt
The following output will appear after running the above commands. The word
‘nila’ exists two times in the 3rd line of the file that has been replaced by
the word ‘Invalid Name’ in the output.

Example-8: Print the formatted content from a tab-delimited file

The following `awk` command will print the first and the second columns of the
file with formatting by using printf. The output will show the user’s name by
enclosing the email address in brackets.
$ cat users.txt

$ awk -F '\t' '{printf "%s(%s)\n", $1,$2}' users.txt
The following output will appear after running the above commands.

Conclusion

Any tab-delimited file can be easily parsed and printed with another delimiter
by using the `awk` command. The ways of parsing tab-delimited files and
printing in different formats have shown in this tutorial by using multiple
examples. The uses of sub() and gsub() functions in the `awk` command for
substituting the content of the tab-delimited file are also explained in this
tutorial. I hope this tutorial will help the readers to parse the tab-delimited
file easily after practicing the examples of this tutorial properly.


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
