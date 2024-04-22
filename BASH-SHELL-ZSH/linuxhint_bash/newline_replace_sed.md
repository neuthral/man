





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Replace Newline with Comma Using the `sed` Command

2 years ago
by Fahmida_Yesmin
Any character or string can be replaced by using the `sed` command. Sometimes,
we need to replace the newline character (\n) in a file with a comma. In this
article, we use the `sed` command to replace \n with a comma.

Using `sed` to replace \n with a comma

Many issues can occur when replacing \n with a comma. By default, every line
ends with \n when creating a file. The `sed` command can easily split on \n and
replace the newline with any character. Another delimiter can be used in place
of \n, but only when GNU sed is used. When the \n is missing in the last line
of the file, GNU sed can avoid printing \n. Furthermore, \n is usually added to
each consecutive output of `sed`.

Create a File

In this article, we will show you how to use  the `sed` command to replace \n
with a comma. To follow along with this tutorial, create a text file
namedClients.txtwith the following tabular client information.

ID  Name         Email             Phone
c01 Md. Rakib    [email protected]01856233238
c02 Meher Afroze [email protected]01733536342
c03 Fakrul Ahsan [email protected]01934737248
c04 Helal Uddin  [email protected]01534895898
c05 Nusrat Jahan [email protected]01866345254


Example 1: Replace \n with a comma using -z

The -z option is used to convert \n to the null character (\0). The content of
the file is treated as a single line if it does not contain any null
characters. The `sed` command will convert the newline into the null character
and replace each \n with a comma by using the first search and replace pattern.
Here, ‘g’ is used to globally search for \n. With the second search and replace
pattern, the last comma will be replaced with \n.
$ cat Clients.txt

$ sed -z 's/\n/,/g;s/,$/\n/' Clients.txt
The following output will be produced after running the commands.

Example 2: Replace \n with a comma using a, b, $! and N

The `sed` command can be used to replace \n with a comma by using a, b, N, and
$!. Here, a is used to append tasks, b is used to branch the content, N is used
to go to the next line, and $! is used to prevent the replacement task from
being applied to the last line. The command will replace each \n with a comma
except the last line.
$ cat Clients.txt

$ sed ':a;N;$!ba;s/\n/,/g' Clients.txt
The following output will be produced after running the commands.

Example 3:  Replace \n with a comma using H, h, d, x and y

If you want to replace \n) with a comma in a small file, then the following
`sed` command can be used. Here, H is used to append the last line to the
holding text, 1h is used to copy every line of the file to the holding text
from the first line, $!d is used to delete all lines except the last line, x is
used to exchange the holding text and pattern space, and y is used to replace
each \n in the holding text with a comma.
$ cat Clients.txt

$ sed 'H;1h;$!d;x;y/\n/,/' Clients.txt
The following output will be produced after running the commands.

Example 4: Replace \n with a comma using -n ,H, h, g and p

The `sed` command can be used to replace \n with a comma with-n option, which
prevents automatic printing. Like in the previous example, H is used here to
append the last line to the holding text, 1h is used to copy every line of the
file to the holding text, $ refers to the last line of the file, g is used to
copy from the holding text, and p is used to print.
$ cat Clients.txt

$ sed -n  "H;1h;\${g;s/\n/,/g;p}" Clients.txt
The following output will be produced after running the above commands.

Example 5: Replace \n with a comma using H, x, p

H, x, and p have been explained in previous examples. The first search and
replace expression will replace each \n with a comma, and the second search and
replace expression will replace a comma at the beginning of a line with a
space.
$ cat Clients.txt

$ sed -n  'H;${x;s/\n/,/g;s/^,//;p;}' Clients.txt
The following output will be produced after running the above commands.

Example 6: Replace \n with a comma using N and `cat`

The `cat` command is used here to send the content of the file to the `sed`
command, and N is used to move to the next line.
$ cat Clients.txt

$ cat Clients.txt | sed 'N;s/\n/,/'
The following output will be produced after running the above commands.

Conclusion

It may be necessary to replace \n with a comma to transfer data from one file
format to another. This type of replacement can also be done by using other
Linux commands. Many command options, such as H, N, h, and x, can be used with
the `sed` command to complete this task. This tutorial goes over several ways
to use the `sed` command to replace \n with a comma.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
