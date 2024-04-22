





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Multiple Delimiters in AWK

2 years ago
by John_Otieno
AWK is a powerful, pattern-matching programming language that works in the
command line to find various patterns in command outputs and files.
We can consider AWK an improvement over Sed since it offers more features,
including arrays, variables, loops, and good old, regular expressions.
In this tutorial, we will quickly discuss how you can use multiple delimiters
in an AWK command. Before we proceed, please note that this tutorial is not a
beginner’s guide to AWK, nor did I intend it as such.
Please refer to the following resource if you need a beginner’s guide to AWK.
https://linuxhint.com/use_awk_linux/

What are Delimiters?

I am sure that, since you are taking the time to read this article, you are
familiar with the concept of delimiters. But it doesn’t hurt to recap, so let’s
do that now:
In a nutshell, delimiters are a sequence of characters used to separate string
text values. There are various common types of delimiters that include:

Name            Symbol
Comma           ,
Colon           :
Semi-Colon      ;
Period          .
Pipe            |
Backslash       \
Slash           /
Parenthesis     ( )
Curly Braces    { }
Square Brackets [ ]
Space


AWK RegEx Field Separator

The AWK Field Separator (FS) is used to specify and control how AWK splits a
record into various fields. Also, it can accept a single character of a regular
expression. Once you specify a regular expression as the value for the FS, AWK
scans the input values for the sequence of characters set in the regular
expression.
We are going to implement the functionality of AWK to accept Regular Expression
values in the field separator to connect multiple delimiters.

Use Multiple Delimiters

To illustrate how to separate using multiple delimiters in AWK, I will use a
simple example to show you how to use this functionality.
Suppose you have a file with data as follows:
/org/gnone/desktop/interface:established:Apr17
16.59.09|org.gnome.Terminal.desktop[1099]
From the above file, we wish to get the output similar to the one shown below:
org/gnome/desktop/interface established Apr 17 16:59.09
org.gnome.Terminal.desktop[1099]
To separate the file using the various delimiters—in this case, a colon, space,
and a pipe—we can use a command as shown below:
awk -F'[: |]' '{print $1, $2, $3, $4, $5, $6}' user.log
The above command outputs the information as shown below:
As you can see, you can combine more than one delimiter in the AWK field
separator to get specific information.

Conclusion

In this quick guide, we discussed using AWK to separate multiple delimiters in
an input file.
To get more information on how to expand the functionality of AWK FS, consider
the following resources:
https://www.gnu.org/software/gawk/manual/html_node/Regexp-Field-Splitting.html
https://www.gnu.org/software/gawk/manual/html_node/Field-Separators.html


About the author


John Otieno

My name is John and am a fellow geek like you. I am passionate about all things
computers from Hardware, Operating systems to Programming. My dream is to share
my knowledge with the world and help out fellow geeks. Follow my content by
subscribing to LinuxHint mailing list
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
