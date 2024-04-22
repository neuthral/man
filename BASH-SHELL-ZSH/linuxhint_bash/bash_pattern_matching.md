





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Pattern Matching

2 months ago
by Denis_Kariuki
Bash pattern matching is an indispensable concept that comes in handy when
selecting different filenames from a directory and checking if a string matches
a given format. Whether you are starting out with bash pattern matching or
looking to brush up on your skills, this guide covers the various ways and tips
for pattern matching.

Pattern Matching

Bash mainly offers two types of pattern matching: globsand extended globs.The
two offer simple ways for users to select the filenames and check the different
strings against specific rules. However, Bash also supports using
regex,especially when working with scripts to validate various user input and
parsing data.

1. Bash Pattern Matching with Globs

Glob pattern matching mainly involves checking for specific filenames in a
given directory. They are referred to as wildcards.There are three types of
bash glob patterns:

2. Asterisk (*)

It is used when you want to match zero or more filenames.
Let’s have some examples.

Checking Filenames Starting or Ending with a Given Character

For instance, if we needed to search for a file starting with lor li,we could
use the following commands:
ls l*

ls li*
Note how it matches all the filenames that start with li or l in the current
directory, including the directories.
To only match with directories, add the / after the wildcard, as shown in the
following:
Similarly, if we needed to match the filenames that end with a given
characteror characters, we could use the wildcard as shown in the following
illustration. In this example, we match the filenames that end with e.
ls *e
Suppose that you are unsure of the filename that you want to search for but you
know the given characters. As in the following example, you can still match the
filenames by adding the wildcard before and after the characters.
We matched the filenames that include the nuxkeyword in their name.

Checking Files with a Given Extension

With Bash pattern matching, you can locate the files with a given extension.
For instance, if you want to find all the pdfs or text files. In that case, you
add the wildcard before the file extension. Let’s see the following example to
match all the text files:
ls *.txt
All the text files are matched as shown in the following:

3.Question Mark (?)

The question mark wildcard matches the filenames that match a single character.
However, you must know the number of characters that a given filename has, such
that each “?” represents each character.
For instance, to match a filename with four characters, but we know the last
character, we could have the following example:
ls ???e
Similarly, to find a given extension where you know the number of characters of
the filename, we could use the following command:
ls ?????.txt

4. Square Brackets []

When you want a more specific search such as matching the filenames that
contain the given characters, the characters to match can be added in the
square brackets.
For instance, to match the filenames that contain any characters or numbers
specified regardless of the extension, we can have the following command:
ls [e-m]*.*
Here, we match the filenames that contain any character from e to m and has any
extension.
If you wanted to match the filenames that start with specific characters, let’s
say starting with [f-l] and having a given extension, we could use the
following pattern:
ls [f-l]*.txt*

5. Bash Pattern Matching with Extended Globs

Extended globs have a huge resemblance to regular expressions. However, they
are turned off by default. When you must use them, you have to turn them on
using the following command:
$ shopt -s extglob
The extended globs include:

6. ?(patterns)

It is used when matching with zero or oneoccurrence of the specified pattern.
For instance, if you want to match all the filenames with a given extension or
those that contain specific characters in their naming, we could have the
following command:
$ ls ?(*nux* | *.sh)

7. *(patterns)

It is used when matching with zero or moreoccurrences of the specified pattern.
For instance, we could use the following command to match the filenames that
start with zero or more “f” and are text files:
$ ls *(f).txt

8. +(patterns)

It is used when matching with one or moreoccurrences of the specified pattern.
If we run the previous command, note that it only matches the filenames that
must contain at least one “f” which means that the .txtfile won’t be a match.
$ ls +(f).txt

9. @(patterns)

It is used when matching with one occurrence of the specified pattern.
If we only need to match the filenames that contain only one “f” using the same
pattern that is used in the previous example, we could use the @ as shown in
the following:
$ ls @(f).txt

10. !(patterns)

It is used when you want to match everything else that doesn’t match the
specified pattern.
Let’s have an example where we want to match all the filenames that don’t have
the specified pattern. In this example, we match all the filenames that are not
text files or Bash scripts. The command is as follows:
$ ls !(*.txt|*.sh)

Conclusion

This guide presented the Bash pattern matching and the various examples to
ensure that you understand how to work with the various pattern matching
options. Using this foundation, you can advance your Bash pattern matching and
use the same logic when you want to match the various patterns on the terminal
or when creating the Bash scripts.


About the author


Denis Kariuki

Denis is a Computer Scientist with a passion for Networking and Cyber Security.
I love the terminal, and using Linux is a hobby. I am passionate about sharing
tips and ideas about Linux and computing.
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
