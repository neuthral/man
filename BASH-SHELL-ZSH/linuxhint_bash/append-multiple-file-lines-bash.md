





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How To Append Multiple Lines To A File With Bash

1 year ago
by John_Otieno
In Linux, we constantly work with files. As a result, we may encounter
instances where we need to append multiple lines to a file.
This quick guide will discuss various approaches you can use to append multiple
lines in a file.

Method # 1 – Using echo & Printf

The simplest way to append multiple lines to a file is to use the echo and
printf command.
Let us start with echo.
Echo is a command used to output a string or multiple strings as arguments.
Echo is available in all Linux distributions, making it a good tool for
redirecting output to a file.
Let us start by verifying the file is not empty.
cat multiple.txt
As shown in the output above, the file is not empty; it contains lines of text.
To add multiple lines to a file with echo, use the -e option and separate each
line with \n.
When you use the -e option, it tells echo to evaluate backslash characters such
as \n for new line.
echo -e "Hello, world\nBash scripting is awesome\nThis is a new line" >>
multiple.txt
If you cat the file, you will realize that each entry is added on a new line
immediately after the existing content.
cat multiple.txt

The printf

Let us now look at printf. Using the printf command is very similar to the echo
command. To append multiple lines with printf command:
printf "Learn Bash scripting basics here\nhttps://linuxhint.com/
bash_scripting_tutorial_beginners/" >> multiple.txt
Similarly, cating the command provides a similar output as:
cat multiple.txt

Method # 2 – Using Bash Heredoc

Another method we can use to append multiple lines to a file in bash is to use
the heredoc.
A heredoc is a redirection feature that allows you to pass multiple lines to a
command or a file.
Using a heredoc involves specifying a delimiter at the beginning of your
command. Once the shell encounters the delimiter, it terminates the input and
redirects it to a file or a specific command.
Learn_the_basics_of_using_a_heredoc.
We can use the tee or cat command to redirect multiple lines to a file using a
heredoc. Let’s discuss both

The Tee command

To append a line using the tee command, we use the -a option. We can then pass
the input from a heredoc as:
tee -a multiple.txt <<EOF
Copy standard input toeach FILE, and also to standard output.
       -a, --append
appendtothe given FILEs, donot overwrite
       -i, --ignore-interrupts
              ignore interrupt signals
       -p     diagnose errors writing tonon pipes
--output-error[=MODE]
set behavior onwriteerror.  SeeMODEbelow
--help display this help and exit
--version
              output version information and exit
EOF
Once you execute the command, a tee will display the contents and append them
to the specified file.
You can verify the content is appended to the file using cat.
cat multiple.txt

The cat command

Using the cat command to append to a file is similar to using the tee command.
However, we use the append redirection symbols to redirect the output.
The following command appends the following lines to the file.
cat <> multiple.txt
------------------------------------------------------------
CAT APPENDS FILES ARE LOCATED HERE
------------------------------------------------------------
EOF
Verify the contents exists in the file using the cat command:
cat mupltiple.txt

To Conclude

This guide discussed various methods you can use to append multiple lines to a
file in bash.


About the author


John Otieno

My name is John and am a fellow geek like you. I am passionate about all things
computers from Hardware, Operating systems to Programming. My dream is to share
my knowledge with the world and help out fellow geeks. Follow my content by
subscribing to LinuxHint mailing list
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
