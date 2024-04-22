





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Finding strings in text files using grep with regular expression

3 years ago
by Matt_Zand
grep is one of most popular tools for searching and finding strings in a text
file. The name ‘grep’ derives from a command in the now-obsolete Unix ed line
editor tool—the ed command for searching globallythrough a file for a regular
expressionand then printingthose lines was g/re/p, where re was the regular
expression you would use. Eventually, the grep command was written to do this
search on a file when not using ed.
In this article, we show you to run advance string searching using Grep with
regular expression by giving you 10 hands-on examples on its implementations.
Many examples discussed in this article have practical implications meaning you
can use them in your daily Linux programming. The following samples describe
some regexp examples for commonly searched-for patterns.

Ex 1: Find a Single Charterer in a Text File

To output lines in the file ‘book’ that contain a ‘$’ character, type:
$ grep ’\$’ book

Ex 2: Find a Single string in a Text File

To output lines in the file ‘book’ that contains the string ‘$14.99’, type:
$ grep ’\$14\.99’ book

Ex 3: Find a Single Special Charterer in a Text File

To output lines in the file ‘book’ that contain a ‘\’ character, type:
$ grep ’\\’ book

Ex 4: Matching Lines Beginning with Certain Text

Use ‘ˆ’ in a regexp to denote the beginning of a line.
To output all lines in ‘/usr/dict/words’ beginning with ‘pro’, type:
$ grep ’ˆpro’ /usr/dict/words
To output all lines in the file ‘book’ that begin with the text ‘in the
beginning’, regardless of case, type:
$ grep -i ’ˆin the beginning’ book
NOTE:These regexps were quoted with’ characters; this is because some shells
otherwise treat the ‘ˆ’ character as a special “metacharacter”
In addition to word and phrase searches, you can use grep to search for complex
text patterns called regular expressions. A regular expression—or “regexp”—is a
text string of special characters that specifies a setof patterns to match.
Technically speaking, the word or phrase patterns are regular expressions—just
very simple ones. In a regular expression, most characters—including letters
and numbers—represent themselves. For example, the regexp pattern 1matches the
string ‘1’, and the pattern boymatches the string ‘boy’.
There are a number of reserved characters called metacharacters that do not
represent themselves in a regular expression, but they have a special meaning
that is used to build complex patterns. These metacharacters are as follows: .,
*, [, ], ˆ, $, and \. It is good to note that such metacharacters are common
among almost all of common and special Linux distributions. Here is a good
article that covers special meanings of the metacharacters and gives examples
of their usage.

Ex 5: Matching Lines Ending with Certain Text

Use ‘$’ as the last character of quoted text to match that text only at the end
of a line. To output lines in the file ‘going’ ending with an exclamation
point, type:
$ grep ’!$’ going

Ex 6: Matching Lines of a Certain Length

To match lines of a particular length, use that number of ‘.’ characters
between ‘ˆ’ and ‘$’—for ex- ample, to match all lines that are two characters
(or columns) wide, use ‘ˆ..$’ as the regexp to search for.
To output all lines in ‘/usr/dict/words’ that are exactly three characters
wide, type:
$ grep ’ˆ...$’ /usr/dict/words
For longer lines, it is more useful to use a different construct: ‘ˆ.\
{number\}$’, where number is the number of lines to match. Use ‘,’ to specify a
range of numbers.
To output all lines in ‘/usr/dict/words’ that are exactly twelve characters
wide, type:
$ grep ’ˆ.\{12\}$’ /usr/dict/words
To output all lines in ‘/usr/dict/words’ that are twenty-two or more characters
wide, type:
$ grep ’ˆ.\{22,\}$’ /usr/dict/words

Ex 7: Matching Lines That Contain Any of Some Regexps

To match lines that contain any of a number of regexps, specify each of the
regexps to search for between alternation operators (‘\|’) as the regexp to
search for. Lines containing any of the given regexps will be output.
To output all lines in ‘playboy’ that contains either the patterns ‘the book’
or ‘cake’, type:
$ grep ’the book\|cake’ playboy

Ex 8: Matching Lines That Contain All of Some Regexps

To output lines that match allof a number of regexps, use grep to output lines
containing the first regexp you want to match, and pipe the output to a grep
with the second regexp as an argument. Continue adding pipes to grep searches
for all the regexps you want to search for.
To output all lines in ‘playlist’ that contains both patterns ‘the shore’ and
‘sky’, regardless of case, type:
$ grep -i ’the shore’ playlist | grep -i sky

Ex 9: Matching Lines That Only Contain Certain Characters

To match lines that only contain certain characters, use the regexp ‘ˆ
[characters]*$’, where characters are the ones to match.  To output lines in ‘/
usr/dict/words’ that only contain vowels, type:
$ grep -i ’ˆ[aeiou]*$’ /usr/dict/words
The ‘-i’ option matches characters regardless of case; so, in this example, all
vowel characters are matched regardless of case.

Ex 10: Finding Phrases Regardless of Spacing

One way to search for a phrase that might occur with extra spaces between
words, or across a line or page break, is to remove all linefeeds and extra
spaces from the input, and then grep that. To do this, pipe the input to tr
with ‘’\r\n:\>\|-’’ as an argument to the ‘-d’ option (removing all line breaks
from the input); pipe that to the fmt filter with the ‘-u’ option (outputting
the text with uniform spacing); and pipe that to grep with the pattern to
search for.
To search across line breaks for the string ‘at the same time as’ in the file
‘docs’, type:
$ cat docs | tr -d ’\r\n:\>\|
-’ | fmt -u | grep ’at the same time as’

Summary

In this article, we reviewed 10 practical examples of using Grep Linux command
for searching and finding strings in a text file. Along the way, we learned how
to use regular expressions in conjunction with Grep to conduct complex searches
on text files. By now you have a better idea on how powerful Linux search
functions are.
Here are additional resources for those interested in learning more about Linux
programming:

Resources for System Administrators


* Linux_System_Admin_Guide-_What_is_Linux_Operating_System_and_how_it_works
* Linux_System_Admin_Guide-_Overview_of_Linux_Virtual_Memory_and_Disk_Buffer
  Cache
* Linux_System_Admin_Guide-_Best_Practices_for_Monitoring_Linux_Systems
* Linux_System_Admin_Guide-_Best_Practices_for_Performing_Linux_Boots_and
  Shutdowns
* Linux_System_Admin_Guide-_Best_Practices_for_Making_and_Managing_Backup
  Operations


Resources for Linux Kernel Programmers


* How_Linux_Operating_System_Memory_Management_works
* Comprehensive_Review_of_Linux_Kernel_Operating_System_Processes
* What_are_mechanisms_behind_Linux_Kernel_task_management


Linux File System Dictionary

Comprehensive_Review_of_How_Linux_File_and_Directory_System_Works


About the author


Matt Zand

Matt Zand is the founder of High_School_Technology_Services, DC_Web_Makers and
Coding_Bootcamps. He has written extensively on advance topics on web design,
mobile App development and blockchain. He is a senior editor at Touchstone
Words where he writes and reviews coding and technology articles. He is also
senior instructor and developer living in Washington DC. You can follow him on
Linkedin.
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
