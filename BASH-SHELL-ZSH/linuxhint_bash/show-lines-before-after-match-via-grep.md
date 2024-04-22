





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Show Lines Before and After Match via Grep

2 years ago
by Aqsa_Yasin
Grep has been used widely in Linux systems when working on some files,
searching for some specific pattern, and many more. This time, we are using the
grep command to display the lines before and after the matched keyword used in
some specific file. For this purpose, we will be using the “-A”, “-B” and, “-C”
flag throughout our tutorial guide. So, you have to perform each step for
better understanding. Make sure you have Ubuntu 20.04 Linux system installed.
Firstly, you have to open your Linux command-line terminal to start working on
grep. You are currently at the Home directory of your Ubuntu system right after
the command-line terminal has been opened. So, try to list all the files and
folders in the home directory of your Linux system using the below ls command,
and you will get all. You can see, we have some text files and some folders
listed in it.
ls

Example 01: Using ‘-A’ and ‘-B’

From the above-shown text files, we will have a look at some of these and try
to apply the grep command on them. Let’s open the text file “one.txt” first
using the popular “cat” command as underneath:
$ cat one.txt
We will first see some specific words matches in this text file using the grep
command as below. We are searching for the word “we” in the text file “one.txt”
using grep instruction. The output shows two lines from the text file having
“we” in them.
$ grep we one.txt
So, in this example, we will be showing the lines before and after the specific
word match in some text files. So using the same text file “one.txt” we have
been matching the word “we” while displaying the 3 lines before it as below.
The flag “-B” stands for “Before”. The output shows only 2 lines before the
specific word line because the file doesn’t have more lines before the line of
a specific word. It also shows those lines having that specific word present in
them.
$ grep –B 3 we one.txt
Let’s use the same keyword “we” from this file to display the 3 lines after the
line that have the word “we”. The flag “-A” presents “After”. The output again
shows only 2 lines because it has not more lines in the file.
$ grep –A 3 we one.txt
So, let us use a new keyword to be matched and display the lines or rows before
and after the line in which it lies. So we have been using the word “can” to be
matched. The line numbers are the same in this case. The 3 lines after the
matched word “can” have been displayed below using the grep command.
$ grep –A 3 can one.txt
You can see the output shows before the lines of a matched word using the
keyword “can”. In contrast, it shows only two lines before the line of the
matched word because there are no more lines before it.
$ grep –B 3 can one.txt

Example 02: Using ‘-A’ and ‘-B’

Let’s take another text file, “two.txt,” from the home directory and display
its contents using the below “cat” command.
$ cat two.txt
Let’s display 5 lines before the word “Most” from the file “two.txt” using the
grep command. The output shows 5 lines before the line contain a specific word.
$ grep –B 5 Most two.txt
The grep command to shows the 5 lines after the word “Most” from the text file
“two.txt” has been given below.
$ grep –A 5 Most two.txt
Let’s change the keyword to be searched. We will use “of” as a keyword to be
matched this time. Display the 2 lines before the word “of” from the text file
“two.txt” can be done by using the below grep command. The output shows two
lines for the keyword “of” because it comes twice in the file. Thus the output
contains more than 2 lines.
$ grep –B 2 of two.txt
Now displaying the 2 lines of file “two.txt” after the line that contains the
keyword “of” can be done using the below command. The output again displays
more than 2 lines.
$ grep –A 2 of two.txt

Example 03: Using ‘-C’

Another flag, “-C” has been used to display the lines before and after the
matched word. Let’s display the contents of the file “one.txt” using the cat
command.
$ cat one.txt
We choose “society” as a keyword to be matched. The below grep command will
display the 2 lines before and 2 lines after the line that contains the word
“society” in it. The output shows one line before the specific word line and 2
lines after it.
$ grep –C 2 society one.txt
Let’s see the contents of file “two.txt” using the below cat command.
$ cat two.txt
In this illustration, we are using “poems” as a keyword to match. So, execute
the below command for this. The output shows two lines before and two lines
after the matched word.
$ grep –C 2 poems two.txt
Let’s use one more keyword from the file “two.txt” to be matched. We are
consuming “nature” as a keyword this time. So, try the below command while
using “-C” as a flag having the keyword “nature” from the file “two.txt”. This
time, the output has more than two lines in the output. As the file contains
the word “nature” more than once, that’s the reason behind it. The keyword
“nature,” which comes first, has two lines before and two lines after it. While
the second matched the same keyword, “nature” has two lines before it, but
there are no lines after it because it is at the last line of the file.
$ grep –C 2 poems two.txt

Conclusion

We are successful in displaying the lines before and after the specific word
while using the grep instruction.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
