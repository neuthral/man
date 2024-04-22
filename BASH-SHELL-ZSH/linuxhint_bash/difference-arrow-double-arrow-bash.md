





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


The Difference Between “>” and “>>” in Linux

1 year ago
by Sam_U
Learning Linux terminal is easy, but mastering it is a bit hard. In many
situations, you come across commands that mystify you because they contain
different operators. Operators are characters or set of characters which offer
different functionalities.
For example, one of the most used sets of operators in Linux is direction
operators. Direction operators redirect the input or output of a command to a
file or any other command.
There are two approaches for redirection; input redirection, and output
redirection. For input redirection, we use less-than “<” sign and for output
redirection greater-than “>” sign which are also termed as angled brackets.
Understanding operators is a bit troublesome. Adding one character to an
operator can change its functionality altogether. Many Linux users face a
similar situation while using “>” and “>>” operators in terminal. Both are
output direction operators. So, what is the difference? Well, this write-up is
all about discussing how these two operators differ. Let’s begin.

Difference Between “>” and “>>” in Linux

As discussed in the introductory part, both operators are output direction
operators. The main difference is mentioned below:
“>“: Overwrites the existing file, or creates a file if the file of the
mentioned name is not present in the directory.
“>>“: Appends the existing file, or creates a file if the file of the mentioned
name is not present in the directory.
While making modifications in a file and you want to overwrite the existing
data, then use the “>” operator. If you want to append something to that file,
use the “>>” operator.  Let’s understand it with an example. I am executing the
following command in terminal:
$ echo “Welcome to LinuxHint” > my_file_1.txt
You will notice that a text file will be created in the directory with the text
“Welcome to LinuxHint”.To check, type“ls”:

To read the file type:
$ cat my_file_1.txt
Let’s run the same command but with different text:
$ echo “Learn latest tips and tricks about Linux” > my_file_1.txt
Now, open read the file using:
$ cat my_file_1.txt
The new text has overwritten the previous text.
Let’s use “>>” operator:
$ echo “Welcome to LinuxHint” >> my_file_2.txt

It will also create a file by the name of “my_file_2.txt” in the current
directory. Type “ls” to verify it:
To read this file, use:
$ cat my_file_2.txt
Now, let’s change the text:
$ echo “Learn latest tips and tricks about Linux” > my_file_2.txt
Since we are using a file that has already been created; to check what changes
“>>” operator made, execute:
$ cat my_file_2.txt
As it can been seen that instead of overwriting the existing text, the “>>”
operator appended the text.

Conclusion

Some commands in Linux can cause confusion, especially to new users, because
they contain operators. Operators are a bit tricky to understand because each
operator can have different functionality. In this guide, we learned the
difference between “>” and “>>” operators.
The “>” is an output operator that overwrites the existing file, while “>>” is
also an output operator but appends the data in an already existing file. Both
operators are often used to modify the files in Linux.


About the author


Sam U

I am a professional graphics designer with over 6 years of experience.
Currently doing research in virtual reality, augmented reality and mixed
reality.
I hardly watch movies but love to read tech related books and articles.
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
