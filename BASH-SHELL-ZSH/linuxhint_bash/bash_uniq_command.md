





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash uniq Command

4 years ago
by Fahmida_Yesmin
Linux users need to create or read the text file in regular basis for many
purposes. A text file can contain different types of numeric and character
data. Same data can be stored multiple times in a text file. Sometimes, you may
require reading any text file by omitting duplicate lines of data. Bash uniq
command is a useful command line utility tool that is used to read a text file
by filtering or removing adjacent duplicate lines from the text file. uniq
command is used to detect the adjacent lines from a file and write the content
of the file by filtering the duplicate values or write only the duplicate lines
into another file.


Syntax:

uniq [OPTION]  [ INPUT  [OUTPUT] ]
Here, OPTION, INPUT, and OUTPUT are optional. If you use only uniq command
without any option or input/output filename then this command will apply on the
standard input data. Many types of options can be used with this command to
filter duplicate data in various ways from any text file. If you use an input
file name with this command then the data will filter from that file. If you
execute the command with the option, input filename, and output filename then
the data will filter from input file based on the option and write the output
into the output file.

Options:

Some major options of uniq command are discussed below.

* -f N or –skip-fields=N

It is used to skip N fields before detecting the uniqueness of data. Fields are
the group of characters separated by whitespace or tab.

* -s N or –skip-chars=N

It is used to skip N characters before detecting the uniqueness of data.

* -w N or –check-chars=N

It is used to compare N characters only in a line.

* -c or –count

It is used to count how many times a line repeated in the searching data and
the values are shown as the prefix of that line.

* -z or –zero-terminated

It is used to terminate the line with 0 bytes instead of using newline.

* -d or –repeated

It is used to print all repeated lines only.

* -D or –all-repeated[=METHOD]

It is used to print all repeated lines based on the used method. The following
methods can be used with this option.
none: It is the default method and doesn’t delimit duplicate lines.
prepend: It adds a blank line before each set of duplicate lines.
separate: It adds a blank line between two duplicate lines.

* -u or –unique

It is used to print the unique lines only.

* -i or –ignore-case

It is used for case-insensitive comparison.

Examples of uniq command

Create a text file named uniq_test.txt with the following content:
Bash Programming
Bash Programming
Python Programming
I like PHP Programming
I like Java Programming

Example#1:  Using -f option

The following command will apply uniq command by skipping first two fields of
each line from uniq_test.txt file.
$ uniq -f 2 uniq_test.txt

Example#2: Using -s option

The following command will apply uniq command by skipping 4 characters from
each line of uniq_test.txt file.
$ uniq -s 4 uniq_test.txt

Example#3: Using –w option

The following command will apply uniq command by comparing the first two
characters of each line.
$ uniq -w 2 uniq_test.txt

Example#4: Using –c option

The following command will count the appearance of each line in the file and
displays the number at the front of each line of the output.
$ uniq -c uniq_test.txt

Example#5: Using –d option

The following command displays those lines from the file only that appeared
multiple times in the file. Only one line has appeared two times in
uniq_test.txt file which is displayed as output.
$ uniq -d uniq_test.txt

Example#6: Using –D option

The following command will print all duplicate lines from the file.
$ uniq -D uniq_test.txt

Example#7: Using –all-repeated option with prepend method

Three methods can be used with –all-repeated option which are mentioned earlier
of this tutorial. Here, the prepend method is used with this option that prints
duplicate lines by appending blank lines at the beginning of duplicate lines.
$ uniq --all-repeated=prepend uniq_test.txt

Example#8: Using –u option

The following command will find out all the unique lines from the file. There
are three unique lines in uniq_test.txt file which are printed as output.
$ uniq -u uniq_test.txt

Conclusion

The uses of uniq command are explained and shown by using various examples in
this tutorial. Hope, you will be able to use uniq command properly after
reading this tutorial.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
