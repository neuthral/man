





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Sed Remove Whitespace

2 years ago
by Karim_Buzdar
Removing whitespaces in documents is an essential formatting step that is
required to improve the overall layout of a text and to ensure data is clean
and tidy. It helps to store only the required data and get rid of unnecessary
leading and trailing spaces. Following are some scenarios where you might need
to remove whitespaces:

* For reformatting the source code
* For cleaning up data
* For simplifying the command-line output

If we talk about leading whitespaces, they are relatively easy to spot as they
are at the start of the text. However, it is not easy to spot the trailing
whitespaces. The same is the case with double spaces which are also sometimes
difficult to spot. It all becomes more challenging when you need to remove all
those leading and trailing whitespaces from a document containing thousands of
lines.
To remove whitespaces from your document, you can use various tools such as
awk, sed, cut, and tr. In some other articles, we have discussed the use of awk
in removing the whitespaces. In this article, we will be discussing the use of
sed for removing whitespaces from the data.
You will learn how to use sed to:

* Remove all white spaces
* Remove leading whitespaces
* Remove trailing whitespaces
* Remove both leading and trailing whitespaces
* Replace multi spaces with single space

We will be running the commands on Ubuntu 20.04 Focal Fossa. You can also run
the same commands on other Linux distributions. We will use the default Ubuntu
Terminal application for running the commands. To open the Terminal, use the
Ctrl+Alt+T keyboard shortcut.

What is Sed

Sed (stands for stream editor) is a very powerful and handy utility in Linux
that allows us to perform basic text manipulations on the input streams. It is
not a text editor, but it helps to manipulate and filter text. It receives the
input streams and edits it according to the user’s instructions and then print
the transformed text to the screen.
With sed, you can:

* Select text
* Search text
* Insert text
* Replace text
* Delete text


Using Sed to Remove Whitespaces

We will use the following syntax for removing whitespaces from the text:
s/ REGEXP /replacement /flags
Where

* s/: is substitution expression
* REGEXP: is a regular expression to match
* replacement: is the replacement string
* flags: We will only use the “g” flag to enable substitution globally on each
  line


Regular expressions

Some of the regular expressions we will use here are:

* ^ matches start of the line
* $ matchesthe end of line
* +matches one or more occurrences of the preceding character
* * matches zero or more occurrences of the preceding character.

For demonstration purpose, we will use the following sample file named
“testfile”.
 Sample file
  Sample file


View All Whitespaces in a File

To find all the whitespaces in your file, pipe the output of cat command to the
tr command like this:
$ cat testfile | tr " " "*" | tr "\t" "&"
This command replaces all the whitespaces in your file by (*) symbol, which
makes it easier to spot all the whitespaces whether they are single, multiple,
leading, or trailing whitespaces.
In the following screenshot, you can see the whitespaces are replaced by *
symbol.
 Sample file with all spaces and tabs  Sample file with all spaces and tabs

Remove All Whitespaces (Including Spaces and Tabs)

In some cases, you need to remove all whitespaces from the data, i.e. leading,
trailing, and the whitespaces between the texts. The following command will
remove all the whitespaces from the “testfile”.
$ cat testfile | sed -r ‘s/\s+//g’
Note: Sed does not alter your files unless you save the output to the file.
Output:
After running the above command, the following output appeared, which shows
that all the whitespaces have been removed from the text.
You can also use the following command to verify that all whitespaces have been
removed.
$ cat testfile | sed -r 's/\s+//g' | tr " " "*" | tr "\t" "&"
From the output, you can see that is no (*) symbol which means all the
whitespaces have been removed.
To remove all whitespaces but only from a specific line (let’s say line number
2), you can use the following command:
$ cat testfile | sed -r '2s/\s+//g'

Remove All Leading Whitespaces (Including Spaces and Tabs)

To remove all the whitespaces from the beginning of each line (leading
whitespaces), use the following command:
$ cat testfile | sed 's/^[ \t]*//'
Output:
The following output appeared after running the above command, which shows all
the leading whitespaces have been removed from the text.
You can also use the following command to verify that all the leading
whitespaces have been removed:
$ cat testfile | sed 's/^[ \t]*//' | tr " " "*" | tr "\t" "&"
From the output, you can see there is no (*) symbol at the beginning of the
lines which verifies that all the leading whitespaces are removed.
To remove the leading whitespaces from only a specific line (let’s say line
number 2), you can use the following command:
$ cat testfile | sed '2s/^[ \t]*//'

Remove All Trailing Whitespaces (Including Spaces and Tabs)

To remove all the whitespaces from the end of each line (trailing whitespaces),
use the following command:
$ cat testfile | sed 's/[ \t]*$//'
Output:
The following output appeared after running the above command, which shows all
the trailing whitespaces have been removed from the text.
You can also use the following command to verify that all trailing whitespaces
have been removed.
$ cat testfile | sed 's/[ \t]*$//' | tr " " "*" | tr "\t" "&"
From the output, you can see there is no (*) symbol at the end of the lines
which verifies that all the trailing whitespaces are removed.
To remove the trailing whitespaces from only a specific line (let’s say line
number 2), you can use the following command:
$ cat testfile | sed '2s/[ \t]*$//'

Remove both Leading and Trailing Whitespaces

To remove all the whitespaces from both the start and end of each line (i.e.
both leading and trailing whitespaces), use the following command:
$ cat testfile | sed 's/^[ \t]*//;s/[ \t]*$//'
Output:
The following output appeared after running the above command, which shows that
both the leading and trailing whitespaces have been removed from the text.
You can also use the following command to verify that both the leading and
trailing whitespaces have been removed.
$ cat testfile | sed 's/^[ \t]*//;s/[ \t]*$//' | tr " " "*" | tr "\t" "&"
From the output, you can see there is no (*) symbol at the start or end of the
lines which verifies that all the leading and trailing whitespaces are removed.
To remove both the leading and trailing whitespaces from only a specific line
(let’s say line number 2), you can use the following command:
$ cat testfile | sed '2s/^[ \t]*//;2s/[ \t]*$//'

Replace Multiple Whitespaces with Single Whitespace

In some cases, there are multiple whitespaces at the same place in the file,
but you only need single whitespace. You can do so by replacing those multiple
spaces by a single space using sed.
The following command will replace all multiple whitespaces with single
whitespace from each line in the “testfile”.
$ cat testfile | sed 's/[ ]\+/ /g'
Output:
The following output appeared after running the above command, which shows the
multiple whitespaces have been replaced with the single whitespace.
You can also use the following command to verify if multiple whitespaces are
replaced with single whitespace:
$ cat testfile | sed 's/[ ]\+/ /g' | tr " " "*" | tr "\t" "&"
From the output, you can see the single (*) symbol at each place which verifies
that all the occurrences of the multiple whitespaces are replaced with a single
whitespace.
So, this was all about removing the whitespaces from your data using sed. In
this article, you have learned how to use sed to remove all whitespaces from
your data, remove only the leading, or trailing whitespace, and remove both
leading and trailing whitespace. You have also learned how to replace multi
spaces with a single space. It will now be easy for you to remove whitespaces
from a file containing hundreds or thousands of lines.


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
