





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to use sed character classes

1 year ago
by Adnan_Shabbir
Stream Editor (sed) is known as a powerful editor because of its wide range of
supported functionalities like substituting, editing, deleting and many more.
While Stream Editor has the long list of characters that provide assistance to
manage the files automatically: these characters are enclosed in a set of
similar characters known as Character Classes; these classes contain the
characters of alike families.
For instance, the digits while using sed are accessed through [[:digit:]] class
and the alphanumeric characters are stored in the class named as [[:alnum:]].
Similarly, all the characters belong to some specific character class; knowing
the importance of these classes, our today’s guide is focused to provide a deep
insight into character classes in sed.
So, let’s start this tutorial:

Character Classes in sed

This section contains the character classes that are used in sed to manage text
files:
Alphabetic Character Class : The alphabetic characters in sed are accessed
through “Alphabetic Character Class”; and one can manage text files by calling
the alphabet class: the keyword used to refer this class is written below:
[[:alpha:]]
For instance, we want to delete all the lines that contain alphabetical letters
from “test.txt”; so, for this you must use this class as shown in the command
below.
Note: use the keyword of the class carefully otherwise the command won’t work:
Additionally, you can perform other operations like substitution, printing as
we have performed deletion in the above command.
Alphanumeric Class : This class contains the alphanumeric characters like you
will have the access to all the letters and numeric numbers as well.
[[:alnum:]]
The example given below will help you to understand the basic usage of this
class in Ubuntu: from the file “test.txt”, we have displayed all the words that
contain alphanumeric characters by following the command written below:
$ sed -n ‘/[[:alnum:]]/p’ test.txt
Lower Case Character Class : This sed class is used to manage lower case
letters in a text file; you can substitute, delete, print the lower-case
letters by using this class; the keyword used for this class is shown below:
[[:lower:]]
For example, if you want to print lines that contain lower case letters then
the command written below will help you to do so:
$ sed -n ‘/[[:lower:]]/p’ test.txt
Upper Case Character Class: This class of sed contains the upper-case letters
in it; the keyword used to address upper case character class is written below:
[[:upper:]]
You can use this class to apply the directed changes to all the upper-case
letters; for example, the command given below will delete all the lines that
contain capital alphabetic letters.
$ sed ‘/[[:upper:]]/d’ test.txt
Blank Character Class : The blanks created by space bar or the tab key resides
in this class; and one can substitute, delete all the blanks in text file using
this character class, the keyword used to address this class is displayed
below:
[[:blank:]]
For instance, we want to substitute the letters “YYY” instead of the blank
spaces in the text file; so, the command mentioned below will help to replace
the blank space with “YYY”:
$ sed ‘s/[[:blank:]]/YYY/g’ new.txt
Space Character Class : This class has alike functionalities as Blank class,
but it covers few more features than it. The functionalities offered by space
character class are spaces, blanks, and support vertical tab, newline.
The keyword used to address this class is shown below:
[[:space:]]
The following command will delete all the lines that contain character of space
class from “test.txt”:
$ sed ‘/[[:space:]]/d’ test.txt
Digits Character Class : This character class is used to address and manage the
digits in sed command line utility; moreover, you can perform collective
changes related to digits throughout the whole text file. The keyword used to
address this class is mentioned below:
[[:digit:]]
For instance, the command written below will print all lines that contains
digits in “test.txt”:
$ sed -n ‘/[[:digit:]]/p’ test.txt
Hexadecimal Character Class: This class in sed contains the hexadecimal
characters (0-9, A-F); the keyword used to refer these characters is mentioned
below:
[[:xdigit:]]
The command mentioned below will print the lines containing hexadecimal
characters in “test.txt”:
$ sed -n ‘/[[:xdigit:]]/p’ test.txt
Print Character Class : This class contains the characters that can be printed
on the screen; it also includes the spaces: the keyword used for this class is:
[[:print:]]
For instance, the command written below will print all the lines that contain
even a single character:
$ sed -n ‘/[[:print:]]/p’ new.txt
Control Character Class : This class of character consist of non-printable
characters in a text file; the keyword used for this class is written below:
[[:cntrl:]]
The non-printable characters class include blank space, tabs, line break, page
breaks et.,
The command written below will delete the lines that contain control characters
in the text file named “new.txt”:
$ sed -n ‘/[[:cntrl:]]/d’ new.txt
Graph Character Class : This class of characters contains the characters that
are printable and works same as [[:print:]]; graph class keyword is written
here:
[[:graph:]]
Note: Graph characters include all those characters that can be edited,
printed, in a human readable manner. For instance, characters of classes of
alphabetical, numeric, hexadecimal et., can be referred as graph characters.
Now let’s get into the example, the command written below will delete all the
lines that have graph characters present in “newfile.txt”:
$ sed ‘/[[:graph:]]/d’ newfile.txt

Conclusion

One of the well-known editors in Ubuntu known as sed provides the ease of
managing text files and the core assistance in this regard provided by
characters. Moreover, there are classes of characters that contain alike
characters and are used extensively in sed. In this detailed guide, we have
targeted the character classes used in sed and briefly explained their usage in
a command line. These classes can be used to perform several operations in a
text file; like if you want to manage the digits in a file, you must use the
digit class and similarly, all other classes are called when their respective
functionality is required. Moreover, we have described the usage of character
classes in regard to fundamental operations of sed like substitution, deletion,
and printing.


About the author


Adnan Shabbir

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
