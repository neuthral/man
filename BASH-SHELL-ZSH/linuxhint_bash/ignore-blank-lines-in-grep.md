





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How Do I Ignore Blank Lines in Grep?

2 years ago
by Aqsa_Yasin
grep stands for Global Regular Expression Print.It has many functionalities,
i.e., searching in a file, searching only names of a file, grep recursively,
etc. grep is considered a powerful command in the linux command portfolio when
it comes to searching. In many cases, we face situations where we don’t need
spaces, or there is a need to remove unwanted gaps in our data. One of the most
challenging ways of using grep is to ignore or remove blank lines from the text
file. This procedure is accomplished through different examples so please read
on below to see how its done.

Syntax

grep [pattern] [filename]
After using grep, there comes a pattern. The pattern implies the way we want to
use it in removing extra space in the data. Following the pattern, the filename
is described through which the pattern is performed.

Prerequisite

To understand the usefulness of grep easily, we need to have Ubuntu installed
on our system. Provide user details by providing username and password to have
privileges in accessing the applications of Linux. After logging in, open the
application and search for a terminal or apply the shortcut key of ctrl+alt+T.

By Using [: blank:] Keyword

You can create a file either on text editor or with a command line in the
terminal. To create a file on the terminal, including the following commands.
$ echo “text to be entered in a file” > filename.txt
There is no need to create a file if it is already present. Just display it
using the appended command:
$ cat filename.txt
Suppose we have a file named bfile having a text extension. Text written in
these files contains spaces between them, as seen in the figure below.
$ echo "my name is guria.
      i am a good student.
         i read in class 5.

          i have one brother and one sister

          my mother is a house wife
          i want to go to school
" > bfile.txt
Display the file contents as shown below:
$ cat bfile.txt
These blank lines can be removed using a blank command to ignore empty spaces
between the words or strings.
$ egrep '^[[:blank:]]*[^[:blank:]#]' bfile.txt
After applying the query, the blank spaces between the lines will be removed,
and the output will no longer contain extra space. The first word is
highlighted as spaces between the last word of the line and between the first
words of the next line are removed. We can also apply conditions on the same
grep command by adding this blank function to remove useless space in the
output.

By Using [: space:]

Another example of ignoring space is explained here. First lets create our text
file on the terminal:
$ echo "my name is hamna

I am a house wife
I want to learn programing

I have one daughter

" > file20
Without mentioning file extension, we will first display the existing file
using the command.
$ cat file20
Let’s look at how extra space is removed using the grep command besides the [:
space:] keyword. grep’s –v option will help print lines that lack blank lines
and extra spacing that is also included in a paragraph form.
$ grep -v '^[[:space:]]*$' file20
You will see that extra lines are removed and output is in sequenced form line-
wise. That’s how grep –v methodology is so helpful in obtaining the required
goal.
Let’s do another example with the following data file:
$ echo "grep is a versatile command that help new user.

 It is used to search file names with the help of commands.


 we can go to mannual by using grep man

" > fileg.txt
Output is as follow:
By applying the command, our output file has been obtained. Here, we can see
data without spacing between the lines that are consecutively written.
$  grep -v '^[[:space:]]*$' fileg.txt
Besides long commands, we can also go with the short written commands in Linux
and Unix to implement grep supports shorthand characters in it.
$ grep '\s' fileg.txt
We have seen how the output is obtained by applying commands from the input.
Here, we will learn how input is maintained back from the output.
$ grep '\S' fileg.txt > tmp.txt && mv tmp.txt fileg.txt
Here we will use a temporary text file with extension of text named as tmp to
transfer the filtered content back to the original file.

By Using ^#

Let’s create a new data file in order to test this syntax version:
$ echo "graphic designing is a good platform of designing

 and making logos business cards

 and posters etc. Photoshop

 and illustrator are used for that"> fileb.txt
$ cat fileb.txt
The text file includes 4 lines in it, having space between them. These space
lines are easily removed using a particular command.
$ grep -Ev "^#|^$" fileb.txt
Regular extended operations are enabled by –E, which allows all regular
expressions, especially pipe. A pipe is used as an optional “or” condition in
any pattern.”^#”. This shows the matching of text lines in the file that begins
with the sign #. “^$” will match with all free spaces in the text or blank
lines.
The output shows the complete removal of extra space between the lines present
in the data file. In this example, we have seen that in the command that ”^#”
comes first, which means the text is matched first. “^$” comes after |
operator, so free space is matched afterward.

By Using ^$

Just like the example mentioned above, we will come with the same results
because the command is almost the same. However, the pattern is written
oppositely. File22.txt is a file, which we are going to use in removing spaces.
$ echo "technical writing is a good feild of studying

it is an analytical field

we can learn many things in it
business writing is its category of writting

Thanku fot learning"> file22.txt
$ grep –v '^$' file22.txt
The same methodology is applied except the working with priority. According to
this command, first, free spaces will be matched, then the text files are
matched. The output will provide a sequence of lines by removing extra gaps in
them.
Other Simple Commands
grep '^..' file22.txt
grep '.' file22.txt
These both are so simple and helps in removing gaps in text lines.

Conclusion

Removing useless gaps in files with the help of regular expressions is quite an
easy approach to achieve a smooth sequence of data and maintain consistency.
Examples are explained in a detailed manner to enhance your information
regarding the topic.


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
