





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to replace the last occurrence using `sed`

2 years ago
by Fahmida_Yesmin
`sed` command is used in Linux for various types of text operations, such as
insert, delete, replace, etc. Different types of replacement tasks can be done
by using the `sed` command easily. Any replacement task can be done based on
the searching text or pattern. The searching text or pattern may occur multiple
times in the string or a file where the searching will be done. How you can
replace the last occurrence of the searching text or pattern has been shown in
this tutorial.

Replace the last occurrence of the text in a string:

This section shows how the last occurrence of the searching pattern in a string
can be replaced by using the `sed` command.

Example-1: Replace the last occurrence of a word based on pattern

The following `sed` command will search the word ‘PHP’ in the string and
replace the searching word with the word ‘AngularJS’if the word exists in the
string.
$ echo "Java PHP Bash Python JavaScript PERL PHP Laravel" |
sed 's/\(.*\)PHP/\1AngularJS/'
The following output will appear after running the command. Here, the word
‘PHP’ exists two times in the string, and the last occurrence has been replaced
by the word’AngularJS‘.

Example-2: Replace the last occurrence of digit based pattern

The following `sed` command will search any digit in the string and replace the
last digit with the number 9.
$ echo "The first counter value 2. The second counter value 4" |
 sed 's/\(.*\)[0-9])*/\19/'
The following output will appear after running the command. Here, the digit
appears two times in the string, and the last digit,4,has been replaced by the
number 9.

Example-3: Replace the last digit of a number based on pattern

The following `sed` command will replace the last digit that exists in the
string value by the value by double zero (0 0).
$ echo "The product price is $ 500." | sed 's/\(.*\)[0-9]/\100/'
The following output will appear after running the command. Here, 500 exists in
the string value. So, according to the replacement command, the last zero of
500 has been replaced by two double zero, and the replaced value is 5000.

Example-4: Replace the last occurrence of a word with another word

The following `sed` command will search the word‘Jun’ in the string and replace
the last occurrence of the word with the value, ‘May’.
$ printf "%s\n" Jan Feb Jun Apr Jun Dec | tr '\n' ' ' |
 sed 's/\(.*\)Jun/\1May/' | tr ' ' '\n'
The following output will appear after running the command. Here, the word‘Jun’
exists two times in the string, and the last occurrence has been replaced by
the word ‘May’.

Replace the last occurrence of a text in a file:

Create a text file named Sales.txt with the following content to test the `sed`
command used in this part of the tutorial for replacing the last occurrence of
a text-based on the pattern.
Sales.txt
Month       Year    Amount
January     2018    $ 200000
March           2019    $ 300000
April           2019    $ 150000
March           2020    $ 350000
May         2019    $ 210000
January     2020    $ 240000

Example-5: Replace the last occurrence of a word with another word

The following `sed` command will search the word ‘January‘ in the file and
replace the last occurrence of this word with the word, ‘July‘.
$ cat Sales.txt
$ sed '$ s/January/July/' Sales.txt
The following output will appear after running the commands. The word ‘January’
appears two times in the file. The last occurrence that exists in the 7th line
of the file has been replaced by the word ‘July‘ in the output.

Example-6: Replace the last occurrence of a number with another number

`tac` command is used to reverse the content of the file. `tac` command is used
with the `sed` command in the following command to replace the last occurrence
of ‘2019‘ with the word, ‘2017’.
$ cat Sales.txt
$ tac Sales.txt | sed '0,/2019/{s/2019/2017/}' | tac
The following output will appear after running the commands. Here, the year
value, ‘2019‘ appears three times in the file. The first, ‘tac’ command has
reversed the content of the file and sent the output into the `sed` command to
replace the first occurrence of ‘2019’ which is the last occurrence in the file
by the year value, ‘2017’. After the replacement, the output has been sent to
the `tac` command to reverse the output again. In this way, the last occurrence
of ‘2019‘ has been replaced by the value, ‘2017‘.

Example-7: Replace everything of a line based on the last occurrence of a word

The following `sed` command will replace the line with a tab (\t) delimited
text where the line starts with the string‘Mar’ for the last time in the file.
$ cat Sales.txt
$ tac Sales.txt | sed '0,/^Mar.*/{s/^Mar.*/July\t\t2018\t$ 400000/}' | tac
The following output will appear after running the commands. Two lines in the
file start with the string, ‘Mar’, and the last occurrence of this string
appears in the 5th line. The first `tac` command has been used to reverse the
content of the file and sent the output to the `sed` command. `sed` command has
replaced the line with a text, ‘Jully 2018 $ 400000‘ where the searching string
found for the first time. The output of the `sed` command has been sent to the
`tac` command again to reverse the output that is the main content of the file.

Conclusion:

`sed` command can be used to replace any part of a string or a line of the file
in different ways by using regular expression patterns. This tutorial showed
the ways to replace the last occurrence of the searching text in a string or a
file by using multiple `sed` commands. How the `tac` command can be used with
the `sed` command to replace the last occurrence of the searching text has also
been shown in this tutorial. But all the commands used here will generate the
output temporarily. You have to use the ‘-i’ option with the `sed` command to
change the content of the file permanently based on the pattern.


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
