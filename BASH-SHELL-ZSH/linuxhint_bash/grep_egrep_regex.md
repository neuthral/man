





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Using grep (and egrep) with Regular Expressions

3 years ago
by Ken_Marr
This tutorial describes how to use both grep (and egrep) to find text in files,
in their simple form and when combined with regular expressions. It contains
several examples and exercises, plus solutions, for the viewer to complete.
The name grep comes from the ed (and vim) command “g/re/p”, which means
globally search for a given regular expression and print (display) the output.

RegularExpressions

The utilities allow the user to search text files for lines that match a
regular expression (regexp). A regular expression is a search string made up of
text and one or more of 11 special characters. A simple example is matching the
start of a line.

Sample File

The basic form of grep may be used to find simple text within a particular file
or files. In order to try the examples, first create the sample file.
Use an editor such as nano or vim to copy the text below into a file called
myfile.
xyz
xyzde
exyzd
dexyz
d?gxyz
xxz
xzz
x\z
x*z
xz
x z
XYZ
XYYZ
xYz
xyyz
xyyyz
xyyyyz
Although you may copy and paste the examples in the text (note that double
quotes may not copy properly), commands need to be typed in order to learn them
properly.
Before trying the examples, view the sample file:
$ cat myfile

Simple Search

To find the text ‘xyz’ within the file run the following:
$ grep xyz myfile

Using Colours

To display colours, use –color (a double hyphen) or simply create an alias. For
example:
$ grep --color xyz myfile
or
$ alias grep=’grep --color’
$ grep xyz myfile

Options

Common options used with the grep command include:

* -i find all lines irrespective of case
* -c count how many lines contain the text
* -n display line numbers of matching lines
* -l display only file names that match
* -r recursive search of sub-directories
* -v find all lines NOT containing the text

For example:
$ grep -i xyz myfile      # find text irrespective of case

$ grep -ic xyz myfile     # count lines with text

$ grep -in xyz myfile     # show line numbers

Create Multiple Files

Before trying to search multiple files, first create several new files:
$ echo xyz>myfile1
$ echo -e “xyz\nxzz\nXYZ”>myfile2
$ echo -e “xxx\nyyy”>myfile3
$ cat myfile1
$ cat myfile2
$ cat myfile3

Search Multiple Files

To search multiple files using filenames or a wildcard enter:
$ grep -ic xyz myfile myfile1 myfile2 myfile3
$ grep -in xyz my* 
# match filenames beginning with ‘my’

Exercise I


  1. First count how many lines there are in the file /etc/passwd.

Hint: use wc -l /etc/passwd

  1. Now find all occurrences of the text var in the file /etc/passwd.
  2. Find how many lines in the file contain the text
  3. Find how many lines do NOT contain the text var.
  4. Find the entry for your login in the /etc/passwd

Exercise solutions can be found at the end of this article.

Using Regular Expressions

The command grepmay also be used with regular expressions by using one or more
of eleven special characters or symbols to refine the search. A regular
expression is a character string that includes special characters to allow
pattern matching within utilities such as grep, vim and sed. Note that the
strings may need to be enclosed in quotes.
The special characters available include:

^ Start of a line
$ End of a line
. Any character (except \n newline)
* 0 or more of previous expression
\ Preceding a symbol makes it a literal character

Note that the *, which may be used at the command line to match any number of
characters including none, is not used in the same way here.
Also note the use of quotes in the following examples.

Examples

To find all lines starting with text using the ^ character:
$ grep ‘^xyz’ myfile
To find all lines ending with text using the $ character:
$ grep ‘xyz$’ myfile
To find lines containing a string using both ^ and $ characters:
$ grep ‘^xyz$’ myfile
To find lines using the .to match any character:
$ grep ‘^x.z’ myfile
To find lines using the * to match 0 or more of the previous expression:
$ grep ‘^xy*z’ myfile
To find lines using .* to match 0 or more of any character:
$ grep ‘^x.*z’ myfile
To find lines using the \to escape the * character:
$ grep ‘^x\*z’ myfile
To find the \ character use:
$ grep ‘\\’ myfile

Expression grep – egrep

The grep command supports only a subset of the regular expressions available.
However, the command egrep:

* allows the full use of all regular expressions
* may simultaneously search for more than one expression

Note that the expressions must be enclosed within a pair of quotes.
To use colours, use –color or again create an alias:
$ alias egrep='egrep --color'
In order to search for more than one regex the egrep command may be written
over multiple lines. However, this can also be done using these special
characters:

|   Alternation, either one or the other
(…Logical grouping of part of an expression

$ egrep '(^root|^uucp|^mail)' /etc/passwd
This extracts the lines which begin with root, uucp or mail from the file, the
| symbol meaning either of the options.
The following command will not work, although no message is displayed, since
the basic grep command does not support all regular expressions:
$ grep '(^root|^uucp|^mail)' /etc/passwd
However, on most Linux systems the command grep -Eis the same as using egrep:
$ grep -E '(^root|^uucp|^mail)' /etc/passwd

Using Filters

Pipingis the process of sending the output of one command as input into another
command and is one of the most powerful Linux tools available.
Commands that appear in a pipeline are often referred to as filters since in
many cases they sift through or modify the input passed to them before sending
the modified stream to standard output.
In the following example, standard output from ls -l is passed as standard
input to the grepcommand. Output from the grep command is then passed as input
to the more command.
This will display only directories in /etc:
$ ls -l /etc|grep ‘^d’|more
The following commands are examples of using filters:
$ ps -ef|grep cron
$ who|grep kdm

Sample File

In order to try the review exercise, first create the following sample file.
Use an editor such as nano or vim to copy the text below into a file called
people:
Personal       J.Smith       25000
Personal       E.Smith       25400
Training       A.Brown       27500
Training       C.Browen      23400
(Admin)        R.Bron        30500
Goodsout       T.Smyth       30000
Personal       F.Jones       25000
training*      C.Evans       25500
Goodsout       W.Pope        30400
Groundfloor    T.Smythe      30500
Personal       J.Maler       33000

Exercise II


  1. Display the file people and examine its contents.
  2. Find all lines containing the string Smith in the file people.Hint: use
     the command grep but remember that by default, it is case sensitive.
  3. Create a new file, npeople, containing all lines beginning with the string
     Personal in the people file.Hint: use the command grep with >.
  4. Confirm the contents of the file npeople by listing the file.
  5. Now append all lines where the text ends with the string 500 in the file
     people to the file npeople.Hint: use the command grep with >>.
  6. Again, confirm the contents of the file npeople by listing the file.
  7. Find the IP Address of the server which is stored in the file /etc/
     hosts.Hint: use the command grep with $(hostname)
  8. Use egrep to extract from the /etc/passwd file account lines containing lp
     or your own user id.

Exercise solutions can be found at the end of this article.

More Regular Expressions

A regular expression can be thought of as wildcards on steroids.
There are eleven characters with special meanings: the opening and closing
square brackets [ ], the backslash \, the caret ^, the dollar sign $, the
period or dot ., the vertical bar or pipe symbol |, the question mark ?, the
asterisk or star *, the plus sign + and the opening and closing round bracket
{ }. These special characters are also often called metacharacters.
Here is the full set of special characters:

^   Start of a line
$   End of a line
.   Any character (except \n newline)
*   0 or more of previous expression
|   Alternation, either one or the other
[…Explicit set of characters to match
+   1 or more of previous expression
?   0 or 1 of previous expression
\   Preceding a symbol makes it a literal character
{…Explicit quantifier notation
(…Logical grouping of part of an expression

The default version of grep has only limited regular expression support. In
order for all of the following examples to work, use egrep instead or grep -E.
To find lines using the |to match either expression:
$ egrep ‘xxz|xzz’ myfile
To find lines using | to match either expression within a string also use ( ):
$ egrep ‘^x(Yz|yz)’ myfile
To find lines using [ ] to match any character:
$ egrep ‘^x[Yy]z’ myfile
To find lines using [ ] to NOT match any character:
$ egrep ‘^x[^Yy]z’ myfile
To find lines using the * to match 0 or more of the previous expression:
$ egrep ‘^xy*z’ myfile
To find lines using the + to match 1 or more of the previous expression:
$ egrep ‘^xy+z’ myfile
To find lines using the ? to match 0 or 1 of the previous expression:
$ egrep ‘^xy?z’ myfile

Exercise III


  1. Find all lines containing the names EvansorMaler in the file people.
  2. Find all lines containing the names Smith, SmythorSmythe in the file
     people.
  3. Find all lines containing the namesBrown, BrowenorBron in the file
     people.If you have time:
  4. Find the line containing the string (admin),including the brackets, in the
     file people.
  5. Find the line containing the character * in the file people.
  6. Combine 5 and 6 above to find both expressions.


More Examples

To find lines using . and * to match any set of characters:
$ egrep ‘^xy.*z’ myfile
To find lines using { } to match N number of characters:
$ egrep ‘^xy{3}z’ myfile
$ egrep ‘^xy{4}z’ myfile
To find lines using { } to match N or more times:
$ egrep ‘^xy{3,}z’ myfile
To find lines using { } to match N times but not more than M times:
$ egrep ‘^xy{2,3}z’ myfile

Conclusion

In this tutorial we first looked at using grep in it’s simple form to find text
in a file or in multiple files. We then combined the text to be searched for
with simple regular expressions and then more complex ones using egrep.

Next Steps

I hope you will put the knowledge gained here to good use. Try out grep
commands on your own data and remember, regular expressions as described here
can be used in the same form in vi, sed and awk!

Exercise Solutions


Exercise I

First count how many lines there are in the file /etc/passwd.
$ wc -l /etc/passwd
Now find all occurrences of the text var in the file /etc/passwd.
$ grep var /etc/passwd
Find how many lines in the file contain the text var
grep -c var /etc/passwd
Find how many lines do NOT contain the text var.
grep -cv var /etc/passwd
Find the entry for your login in the /etc/passwd file
grep kdm /etc/passwd
 

Exercise II

Display the file people and examine its contents.
$ cat people
Find all lines containing the string Smith in the file people.
$ grep 'Smith' people
Create a new file, npeople, containing all lines beginning with the string
Personal in the people file
$ grep '^Personal' people> npeople
Confirm the contents of the file npeople by listing the file.
$ cat npeople
Now append all lines where the text ends with the string 500 in the file people
to the file npeople.
$ grep '500$' people>>npeople
Again, confirm the contents of the file npeople by listing the file.
$ cat npeople
Find the IP Address of the server which is stored in the file /etc/hosts.
$ grep $(hostname) /etc/hosts
Use egrep to extract from the /etc/passwd file account lines containing lp or
your own user id.
$ egrep '(lp|kdm:)' /etc/passwd
 

Exercise III

Find all lines containing the names EvansorMaler in the file people.
$ egrep 'Evans|Maler' people
Find all lines containing the names Smith, Smyth or Smythe in the file people.
$ egrep 'Sm(i|y)the?' people
Find all lines containing the namesBrown, Browen orBron in the file people.
$ egrep 'Brow?e?n' people
Find the line containing the string (admin),including the brackets, in the file
people.
$ egrep '\(Admin\)' people
Find the line containing the character * in the file people.
$ egrep '\*' people
Combine 5 and 6 above to find both expressions.
$ egrep '\(Admin\)|\*' people
 


About the author


Ken Marr

Ken has been a Linux (and Unix) trainer in the UK for over 20 years and has
both knowledge of, and a passion for, Linux and open source. He keeps abreast
of developments in Linux using both Mint with Cinnamon and MX with Xfce as his
prefered desktop environments. He still delivers courses, in fundamentals,
shell scripting and administration, using Virtual Box VMs running CentOS,
Ubuntu and Kali.
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
