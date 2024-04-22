





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Removing Characters from String in Bash

2 years ago
by Karim_Buzdar
At times, you may need to remove characters from a string. Whatever the reason
is, Linux provides you with various built-in, handy tools that allow you to
remove characters from a string in Bash. This article shows you how to use
those tools to remove characters from a string.
The article covers how to perform the following:

* Remove character from string using sed
* Remove character from string using awk
* Remove character from string using cut
* Remove character from string using tr

The commands shown in this article were performed in Ubuntu 20.04 Focal Fossa.
The same commands can also be performed on other Linux distributions that have
the above tools available. We will use the default Terminal application to run
the commands. You can access the Terminal application using the Ctrl+Alt+T
keyboard shortcut.

Remove Characters from String Using sed

Sed is a powerful and handy utility used for editing streams of text. It is a
non-interactive text editor that allows you to perform basic text manipulations
on input streams. You can also use sed to remove unwanted characters from
strings.
For demonstration purposes, we will use a sample string and then pipe it to the
sed command.

Remove Specific Character from String

Using sed, you can remove a specific character from a string. For example, to
remove “h” from the string “hello, how are you?” the command would be:
$ echo "hello, how are you?" | sed 's/h//'
This will only remove the first occurrence of ‘h’ in the string.
 Remove Specific Character from String1  Remove Specific Character from String1

To remove all occurrences of ‘h’ from the string, use the following command:
$ echo "hello, how are you?" | sed 's/h//g'
Where g stands for global. It will remove all occurrences of ‘h’ in the string.
 Remove Specific Character from String2  Remove Specific Character from String2

Remove First Character from String

To remove the first character from the string “hello, how are you?” the command
would be:
$ echo "hello, how are you?" | sed 's/^.//' file
Where (.) matches exactly a single character and (^) matches any character at
the beginning of the string.
 Remove First Character from String  Remove First Character from String

Remove Last Character from String

To remove the last character from the string “hello, how are you?” the command
would be:
$ echo "hello, how are you?" | sed 's/.$//'
Where (.) matches exactly a single character and ($) matches any character at
the end of the string.
 Remove Last Character from String  Remove Last Character from String

Remove First and Last Character from String

To remove the first and last character from the string “hello, how are you?”
the command would be:
$ echo "hello, how are you?" | sed 's/^.//;s/.$//'
 Remove First and Last Character from String  Remove First and Last Character
from String

Remove Characters from String Using awk

Awk is a powerful scripting language used for pattern matching, along with text
processing. Awk allows you to filter and transform text in various ways. You
can also use awk to remove characters from strings.
For demonstration purposes, we will use a sample string and then pipe it to the
awk command.

Remove First Character From a String

To remove the first character from the string “hello, how are you?”the command
would be:
$ echo "hello, how are you?" | awk '{ print substr( $0, 2 ) }'
Where ($0) is the whole target string and (2) is the character starting
position. The above command removes the first character, ‘h,’ character number
‘1,’ and returns the target string beginning with the second character, ‘e.’
 Remove First Character From a String  Remove First Character From a String

Remove First Two Characters from String

You can also remove a specific number of characters from the beginning of a
string. For example, to remove the first two characters from the string “hello,
how are you?”the command would be:
$ echo "hello, how are you?" | awk '{ print substr ($0, 3 ) }’
The above command will remove the first two characters, ‘he,’ or character
numbers ‘1 and 2,’ and returns the target string beginning with character
number ‘3,’ or ‘l.’
 Remove First Two Characters from String  Remove First Two Characters from
String

Remove Last Character from String

To remove the last character from “hello, how are you?” the command would be:
$ echo "hello, how are you?" | awk '{ print substr( $0, 1, length($0)-1 ) }'
Where length($0)-1 means deducting ‘1’ from the total character length.
The above command will print the string beginning with character number ‘1’ up
to length($0)-1 to strip off the last character.
There are ‘19’ characters (including spaces) in the above string. The command
will work by printing all characters, starting with character ‘1’ and up to
character ‘18,’ while removing the last character ‘19.’
 rmv last char frm string  rmv last char frm string

Remove Last Two Characters from String

To remove the last two characters from “hello, how are you?” the command would
be:
$ echo "hello, how are you?" | awk '{ print substr( $0, 1, length($0)-2 ) }'
Where length($0)-2 means deducting ‘2’ from the total character length.
The above command will print the string, beginning with character number ‘1’
and up to character number ‘length($0)-2,’ to remove the last two characters in
the string.
 Remove Last Two Characters from String  Remove Last Two Characters from String

Remove Both First and Last Characters from String

To remove both the first and the last characters from the string “hello, how
are you?” the command would be:
$ echo "hello, how are you?" | awk '{print substr($0, 2, length($0) - 2)}'
Where length($0)-2 means deducting ‘2’ from the total character length.
The above command will print the string, beginning with character number ‘2’ up
to character number ‘length($0)-2,’ to remove the first and last character.
 Remove Both First and Last Characters from String  Remove Both First and Last
Characters from String

Remove Character from String Using cut

Cut is a command-line tool commonly used to extract a portion of text from a
string or file and print the result to a standard output. You can also use this
command for removing characters from a string.
For demonstration purposes, we will use a sample string and then pipe it to the
cut command.

Remove First Character from String

To remove out the first character from the string, “hello, how are you?” the
command would be:
$ echo "hello, how are you?" | cut -c 2-
This command will print the string, beginning with the second character, while
removing the first character.
 rmv cut -c  rmv cut -c

Remove First Four Characters from String

To remove the first four characters from the string “hello, how are you?” the
command would be:
$ echo "hello, how are you?" | cut -c 5-
This command will print the string, beginning from the fifth character, while
removing the first four characters.
 Remove First Four Characters from String  Remove First Four Characters from
String

Print String Between 2nd and 5th Characters

To print the string “hello, how are you?”between the second and fifth
characters, the command would be:
$ echo "hello, how are you?" | cut -c 2-5
This command will print the string, beginning from the second character and up
to the fifth character, while removing the remaining beginning and ending
characters.
 rmv 2nd and 5th c2  rmv 2nd and 5th c2

Remove Last Character from String

To remove the last character from the string “hello, how are you?” use the cut
command with rev, as follows:
$ echo "hello, how are you?" | rev | cut -c2- | rev
This command works by first reversing the string, then cutting the first
character, and finally reversing it again to give you the desired output.
 02Remove Last Character from String  02Remove Last Character from String

Remove Last Four Characters from String

To remove the last four characters from the line “hello, how are you?” the
command would be:
$ echo "hello, how are you?" | rev | cut -c5- | rev
This command works by first reversing the string, then cutting the first four
characters, and then reversing it again to give you the desired output.
 rmv last four chars  rmv last four chars

Remove First and Last Characters from String

To remove the first and last characters from the string “hello, how are you?”
use the cut command with rev, as follows:
$ echo "hello world!" | cut -c2- | rev | cut -c2- |rev
This command works by cutting the first character, then reversing the string
and cutting its first character, and then reversing it again to give you the
desired output.
 rmv first and last  rmv first and last

Remove Character from String Using tr

The tr command (short for translate) is used to translate, squeeze, and delete
characters from a string. You can also use tr to remove characters from a
string.
For demonstration purposes, we will use a sample string and then pipe it to the
tr command.

Remove All Occurrences of Character

Using the tr command, you can remove all occurrences of lowercase or uppercase
characters from your string. For instance, to remove all occurrences of the
lowercase character ‘h’ from the string, the command would be:
$ echo "Hello, how are you?" | tr -d h
 remove all occurences 01  remove all occurences 01
Similarly, to remove all occurrences of the uppercase character ‘H’ from the
string, the command would be:
$ echo "Hello, how are you?" | tr -d H
You can also use interpreted sequences to remove lowercase or uppercase
letters:
$ echo "Hello, how are you?"| tr -d [:upper:]
 occurences lower  occurences lower
$ echo "HELLO, How are you?"| tr -d [:lower:]
 occurences upper  occurences upper

Remove All Occurrences of Lowercase and Uppercase Characters

You can also remove all occurrences of both lowercase and uppercase characters
from a string. For instance, the following command will remove all occurrences
of the character ‘h,’ both lowercase and uppercase.
$ echo "Hello, how are you?" | tr -d ‘hH’
 occurences upper and lower  occurences upper and lower

Remove All Occurrences of Characters in a Specific Range

To remove all occurrences of characters from a string in the specific range ‘d-
h,’ the command would be:
$ echo "hello, how are you?" | tr -d 'd-h'
This command will remove all characters in the range ‘d-h’ (d,e,f,g,h) in the
string.
 occurences specific range  occurences specific range

Conclusion

In Linux, there will always be more than one way to accomplish a simple job.
The same is true with removing characters from a string. This article showed
you four different ways to do so, along with a few examples for removing
unwanted characters from a string. Deciding which tool to use all depends on
your preferences and, more importantly, on what you want to achieve.


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
