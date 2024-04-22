





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Find the Last Occurrence of a String in File Linux

1 year ago
by John_Otieno
In Linux, we constantly work with string and text files; whether working with
log files or documents, text manipulation is one process we cannot escape.
This guide will show you how to locate the last occurrence of a string in a
file in Linux. Linux has many tools that can help perform tasks. However, for
simplicity, we will stick to the readily available tools in all major Linux
distributions.

Method 1: Using Grep

Global Regular Expression Print, known as grep, is a popular and powerful text
manipulation tool.
It works by accepting input from standard input or a file and searches for a
specified pattern. Once grep finds the specified pattern, it prints the result
to the standard output. The specified pattern can be a single string or a
complex regex.
Suppose we have the file auth.log (/var/log/auth.log). To find the last
occurrence of a string (uid=0), we can use the command:
$ sudo grep “uid=0” auth.log | tail -1
The output will be as shown below:
The command is relatively simple. We start by finding the string we require
using grep. Next, Grep will list all the string occurrences, and finally, we
pipe the output to the tail and locate the last line of the output.
You can modify the command above to get the last five occurences of the string
as:
$ sudo grep “uid=0” auth.log | tail -5

Method 2: AWK

AWK is another popular string manipulation language. AWK is very powerful as it
offers incredible features compared to other text manipulation programs.
To find a similar string as above, we can use a command as:
$ sudo awk ‘{/uid=0/{flag = 1}; flag’ | tail -1
Similarly, this will show the last occurrence of the string as:

Conclusion

That is it for this one. In this quick tutorial, we discussed two main methods
to find the last occurrence of a string using grep and awk.


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
