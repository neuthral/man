





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Linux egrep Command with Examples

3 years ago
by Karim_Buzdar
The egrep command belongs to the family of the grep command which is used for
pattern searching in Linux. If you have used the grep command, egrep works the
same as grep -E (grep Extended regex’) does. Egrep scans a specific file, line
to line, and prints the line(s) that contain the search string/regular
expression. In this article, we will explain 15 useful examples of the egrep
commands that will help newbies and even experts to perform meaningful searches
in LinuxWe have performed these examples on a Debian 10  Buster system but they
can be easily replicated on most Linux distros.

Example 1: Searching for a specific string in a file

This is the most common use of the egrep command. What you do is that you
specify a string that you want to search for, and the file name that you want
to look up that string in. The result then displays the entire line containing
the searched string.
Syntax:
$ egrep “search_string” filename
Example:
$ egrep debian samplefile.txt
In this example, I searched for the word “debian” in the specified text file.
You can see how the results display the entire line that contains the word
“debian”:

Example 2: Searching for a specific string in multiple files

With egrep command, you can search for a string among multiple files residing
in the same directory. You just have to be a little more specific in providing
a “pattern” for the searched files. This will become more clear with the
example we will present.
Syntax:
$ egrep "search_string" filename_pattern
Example:
Here, we will search for the word “debian” in all the .txt files by specifying
the filename pattern as follows:
$ egrep “debian” *.txt
The command has printed all the lines, along with the filenames that contain
the word “debian” from all the .txt files in the current directory.

Example 3: Recursively searching the string in the entire directory

When you want to search for a string in all the files from a directory and its
sub-directories, you can do so by using the -r flag with the egrep command.
Syntax:
$ egrep -r "search_string" *
Example:
In this example, I am searching for the word “sample” in the files of the
entire current(Downloads) directory.
$ egrep -r "sample" *
The results contain all the lines, along with the filenames, that contain the
word “sample” from all the files in the Downloads directory, and its sub
directories.

Example 4:  Performing a case-insensitive search

With the -i flag, you can use the egrep command to print the results based on a
search string without having to worry about its case.
Syntax:
$ egrep -i "search_string” filename
Example:
Here, I am searching for the word “debian” and I want the results to display
all lines from the file that contain the word “debian” or “Debian, irrespective
of its case.
$ egrep -i "search_string” filename
You can see how the -i flag helped me in fetching all the lines that contain
the search string through a case “insensitive” search.

Example 5: Searching for a string as a full word and not as a sub-string

When you normally search for a string through egrep, it prints all the words
that contain the string as a sub-string. For example, looking up for the string
“on” will print all the words containing the string “on” like “ on”, “only”,
“monitor”, “clone”, etc. If you want the results to display only the word “on”
as a full word and not as a sub-string, you can use the -w flag with egrep.
Syntax:
$ egrep -w “search_string” filename
Example:
Here I am searching for the string “on” in a sample file:
$ egrep -i “on” samplefile.txt
You can see in the above output, that it contains the word “only” too. However,
this is not what I want as I am exclusively looking for the word “on”. So, this
is the command I will use instead:
$ egrep -iw “on” samplefile.txt
Now my search results only include the lines that contain the word “on” as a
whole word.

Example 6: Printing only the filenames that contain the string

Sometimes we only want to fetch the file names that contain a specific string,
rather than printing the lines that contain it. This can be done using the -l
(lowercase L) flag with the egrep command.
Syntax:
$ egrep -l "search_string" filename_pattern
Example:
Here I am searching for the string “sample” in all the .txt files in the
current directory:
$ egrep -l sample *.txt
The search results only print the name of the files that contain the specified
string.

Example 7: Printing only the search string from a file

Instead of printing the entire line that contains the search string, you can
use the egrep command to print the string itself. The string will be printed
the number of times it appears in the specified file.
Syntax:
$ egrep -o "search_string" filename
Example:
In this example, I am looking up for the word “This” in my file.
$ egrep -o This samplefile_.txt
Note: This usage of the command comes handy when you are searching for a string
based on a regular expression pattern. We will explain regular expressions in
detail in one of the coming examples.

Example 8: Displaying n number of lines before,after, or around the search
string

Sometimes it is very important to know the context in a file where a specific
string is used. The egrep comes in handy in the sense that it can be used to
display the line containing the search string and also a specific number of
lines before, after and surrounding it.
This is the sample text file that I will be using to explain the coming
examples:
N number of lines After the search string:
Using the A flag in the following manner will display the line containing the
search string and N number of lines after it:
$ egrep -A <N> "search_string" filename
Example:
$ egrep -A 2 "sample” samplefile.txt
N number of lines Before the search string:
Using the B flag in the following manner will display the line containing the
search string and N number of lines before it:
$ egrep -B <N> "search_string" filename
Example:
$ egrep -B 2 "sample” samplefile.txt
N number of lines Before the search string:
Using the C flag in the following manner will display the line containing the
search string, and N number of lines before and after it:
$ egrep -C <N> "search_string" filename
Example:
$ egrep -C 2 "sample” samplefile.txt

Example 9:  Matching regular expression in files

The egrep command becomes more powerful as you search for regular expressions
instead of solid search strings in a file.
Syntax:
$ egrep "RegularExpressions" filename
Let us explain how you can use Regular Expressions in your egrep search:

Repetition operator Use
                    The preceding item before ? is optional and is matched
?                   maximum one time
                     
*                   The preceding item before * will be matched zero or more
                    times
+                   The preceding item before + will be matched one or more
                    times
{n}                 The preceding item is exactly matched n number of times.
{n,}                The preceding item is matched n or more times
{,m}                The preceding item is matched maximum m times
{n,m}               The preceding item is matched at least n times but not more
                    than m times

Example:
In the following example, the lines containing the following expression is
matched:
starting with “Gnome” and ending at “ programs”

Example 10: Highlighting the search string

When you set the GREP_OPTIONS environment variable as below, you get your
output with the search string/pattern highlighted in the results:
$ sudo export GREP_OPTIONS='--color=auto' GREP_COLOR='100;8'
You can then search for the string in any manner we have described in the
examples of this article.

Example 11: Performing Invert search in a file

By invert search, we mean that the egrep command prints everything in the file,
except the lines that contain the search string. We will use the following
sample file to explain invert search through egrep. We have printed the
contents of the file using the cat command:
Syntax:
$ egrep -v "search_string" filename
Example:
From the sample file we mentioned, we want to omit the line containing the word
“two” in the output, therefore we will use the following command:
$ egrep -v "two" samplefile_.txt
You can see how the output contains everything from the sample file except for
the second line that contained the search string “two”.

Example 12:  Performing invert search based on multiple criteria/search pattern

With the -v flag, you can also make the egrep command to perform an inverted
search based on more than one search string/pattern.
We will be using the same sample file that we mentioned in example 11 to
explain this scenario.
Syntax:
$ egrep -v -e "search_string"/”pattern” -e "search_string"/”pattern”
.... filename
Example:
From the sample file we mentioned, we want to omit the line(s) containing the
words “one” and “two” in the output, therefore we will use the following
command:
$ egrep -v -e “one” -e "two" samplefile_.txt
We have provided two words to omit using the -e flag, therefore the output will
appear as follows:

Example 13: Printing the number of lines that match the search string

Instead of printing the searched string from the file or the lines containing
it, you can use the egrep command to count and print the number of lines
matched against the string. This count can be fetched using the -c flag with
the egrep command.
Syntax:
$ egrep -c "search_string” filename
Example:
In this example, we will use the -c flag to count the number of  lines that
contain the word “This” in our sample file:
$ egrep -c "This” filename
You can also use the invert search feature here to count and print the number
of lines that do not contain the search string: 
$ grep -v -c "search_string” filename

Example 14: Displaying the line number where the string is matched

With the -n flag, you can make the egrep command to print the matched line
along with the line number that contains the search string.
Syntax:
$ grep -n "search_string” filename
Example:
$ grep -n "This” samplefile_.txt
You can see how the line numbers are displayed against the search results.

Example 15: Displaying the position in the file where the search string matches

If you want to know the position in the file where the search string exists,
you can use the -b flag with the egrep command.
$ grep -o -b "search_string” filename
Example:
$ grep -o -b "This” samplefile_.txt
The search results print the byte offset of the file where the search word
exists.This was a detailed usage of the egrep command. By using a combination
of the flags explained in this article, you can perform more meaningful and
complex searches on your files.


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
