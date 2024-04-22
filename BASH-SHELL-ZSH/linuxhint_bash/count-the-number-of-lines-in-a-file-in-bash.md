





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How Do I Count the Number of Lines in a File in Bash?

1 year ago
by Aqsa_Yasin
In any code or a program, sometimes such a situation exists where we need to
know how big the data of the filefile’s data is. We can get this through the
number of lines of a file, instead of consulting the whole data. Counting the
lines manually can consume a lot of time. So these tools are used, that ease us
with our desired output. In this guide, wThis guide will cover some common and
uncommon ways to count the line number in a file.
For understanding this concept, we need to have a text file. So that we apply
the commands on that specific file. We have already created a file. Consider a
file named file1.txt.
$ cat  file1.txt
Otherwise, you first have to create a file. The file can be created through
many methods. We will do it through the echo with the angular brackets in the
command.
$ echo “text to be written in the file” > filename

Example 1

As we have displayed the content of a file through the cat command at the start
of the article. This example implies the use of “-n” with the cat command. The
output of the command will constitute the line number and the text content of a
file. So we will get the total lines in the respective file.
$ cat –n file1.txt   
The respective image shows that the file has 11 lines in it.
Similarly, there is another example in which we have used “nl” in the command.
N will show the numbers, and –l is used to enlistfor enlisting all the contents
with the line number. So here goes the command.
$ nl file1.txt

Example 2

This example deals with the usage of a “wc” command. This is used in finding
the number of words, bytes, lines, and characters. Here we will receive only
the line numbers without text. To get the resultant value, use “wc” with –l in
the command. This will provide the total number of lines with the file name as
a result. So we will apply this command.
$ wc –l file1.txt
In the result, both the line number and the data are seen. Now, if you want to
display only the number of total lines without displaying the file name. ThenIf
you want to display only the number of total lines without displaying the file
name, you can use a left angular bracket in the command. Here the command shell
has redirected the file1.txt file to the standard input for the wc –l command.
$ wc –l file1.txt
Another way of using the “wc” command is to use it with the cat command. This
command allows the use of “pipe” along with the cat and wc -l. The content will
act as input for the content part after the pipe in the command. The received
output is concurrent in both cases. But the way of use is different.
$ cat file1.txt | wc -l

Example 3

The use of a “sed” command is elaborated in this example. The stream editor
specifies that it is used to transform the text of the file. This is mostly
used in the command where we need to find the required text and then replace
it. “Sed” gets more than one argument to display the number of lines. In this
command, we will use “sed” to get the count for the respective file.
We will use two operators here to describe its usage with both.

“=”

The first one is the equality sign. We will use “sed”, an equal sign (=) and –n
option. This combination will bring the blank lines plus the numbering of
lines. The content will not be shown here. Only the line numbers are displayed
here.
$ sed –n ‘=’ file1.txt

“$=”

In the second option, we will use the dollar sign in addition to the equality
sign. This combination is used with the “sed” and –n option. Unlike the last
example, we will come to know the total number of lines only, not the context.
Sometimes we need to have the last line number instead of having the numbers of
all the lines of the filefile lines, ; for this, we use this approach.
$ sed –n ‘$=’ file1.txt

Example 4

An ‘awk’ is used in the command to collect the total numbers of the line. All
the lines are considered as the record. At the END section, we will see the
record number (NR). NR variable is a built-in of the ‘awk’. Only the last
number will be shown. So one can easily know the total lines in the file.
$ awk ‘END { print NR }’ file1.txt

Example 5

“Grep” stands for Global expression regular print. “Grep” is another way of
finding the filename or the text-related terms inside the file. “Grep” searches
for the specific patterns in the file through the special characters and also
finds the specific expressions that matched the ones present in the command
through the regular expressions.
Similarly, here ‘$’ is used. That is known to find and display the end of the
line. ‘-count’ is used to counting all the lines that match with the expression
present in the file. So by using this command, we will be able to reach the end
of the file and to count the line number of the content.
$ grep - -regexp = “$” - -count file1.txt             
Another way of using a grep command is to use it with “.*” and –c. “-c” is used
to count all the lines, whereas the ‘*’ sign implies all the text. It means to
count all the line numbers in the text.
$ grep –c “.*” file1.txt
In this type, we have used both –h and –c together. As we know, c is to count,
whereas –h will display all the matched lines. This means it will bring the
last line with the file name.
$ grep –Hc “.*” file1.txt

Example 6

We have used a “Perl” to count the lines in the whole file. “Perl” is expanded
as “Practical Extraction and Reporting Language”. It is a scripting language
like bash. It works like the “awk” command. It also prints the line number at
the end, as shown through the command. Here “$” sign means to
approachapproaching the end of the file. “-lne” is for the line.
$ perl –lne ‘END { print $. }’ file1.txt

Example 7

Here we will try a loop to count. As in the programming languages, we often use
loops for counting in any arithmetic operation. Similarly, here we will use a
while loop. The loop has shown a condition to go to the end, and the counting
process is done in the while whole body. The loop will work in such a wayso
that the input is read line by line, and every time the value of count is
incrementedthe value of count is incremented every time. We take print of the
count at the end.
$ count = 0

$ While read

Do

((count = $count+1))

Done < file1.txt

$ echo $count

Conclusion

Line numbers are counted in different ways. This is proved through this article
that, to count a line number of a file we can use many approaches we can use
many approaches to count a line number of a file. By using “grep”, “cat”, and
“awk” methodologies, through which we can obtain the desired output.


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
