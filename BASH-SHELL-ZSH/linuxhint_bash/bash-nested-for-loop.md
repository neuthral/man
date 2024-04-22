





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Nested For Loop

8 months ago
by Omar_Farooq
Loops are the data structure used in many languages to perform some task in
iterations i.e., repeatedly until the actual goal is achieved. One of the many
loops of programming is the “For” loop. The “for” loop can be used alone and
more than one “for” loop in a sequence is said to be “nested”. Therefore, we
have decided to use the “nested” for loops in Bash programming within our
examples of today’s article. So, let’s start with the opening of the terminal
shell in the Ubuntu 20.04 system via the “Ctrl+Alt+T” shortcut.

Example 01: Simple For Loop

Within the terminal shell, we will be creating a new Bash file named “bash.sh”
with the “touch” instruction. This file will be created in our system’s home
directory. This file needs to be opened in some editor i.e., nano, vim, or text
to add code to it. So, we have opened this newly created file from the home
folder within the “nano” editor as per the shown below nano instruction in the
shell followed by the name of a file.
$ touch bash.sh

$ nano bash.sh
We have added the bash extension within the Bash file as “#!/bin/bash”. The
simple “for” loop has been started with double “simple” brackets as below. This
loop began with the value 1 (variable “I”) and will continue until the value
equals 5. At each iteration, the increment operator has also been used to
increase the value of a variable “I” by one. The “do” part of the “for” loop
displays here. On each iteration, the “do” part will get executed and the echo
statement will be showing the iteration number using “$i” in it. The term
“done” indicates the end of the loop. Let’s save our Bash code for execution.
Press Ctrl+X to exit. The code is attached here.
On running this Bash file, we have got all the iteration numbers printed on the
shell. The output is presented in the affixed image.
$ bash bash.sh

Example 02: Nest For Loop

Let’s start with the nest for loop now. For this, we need to add two “for”
loops one after another in a sequence within the Bash code. Thus, we have
opened the same file and updated our code as below. Both the “for” loops will
be started from 1 and end at value 3 with an increment of 1. The inner loop
will execute entirely i.e., up to three values, on the first execution of the
outer loop. At the next iteration of the outer loop, the inner “for” loop will
be executed 3 times again to value 3 and so on for the last iteration as well.
The inner loop will be repeated 9 times, whereas the outer loop will be
operated 3 times in this manner. The outer loop cannot go to its next increment
until the inner loop fully executes itself 3 times. The inner loop will be
responsible for showing the iteration number of the outer loop as well as the
inner loop using the “echo” statement within its “do” clause. Both the loops
have been ended via “done”. The code is attached here.
On the execution of this updated code with the Bash command, we have got the
inner loop executed 9 times i.e., 3 times for each iteration of the outer loop.
The output is presented in the affixed image.
$ bash bash.sh

Example 03: Nested For Loop in One line

The nested “for” loop can also be used within the Bash code in a single line.
So, we have updated the same Bash file after opening it within the nano editor
as below. For the first “for” loop, we have used the values x, y, and z. For
the inner “for” loop, we have used three numbers 1, 3, and 5. Within the “do”
statement both inner and outer loop iteration values will be displayed. Both
loops are ended using the “done” clauses shown below. The code is attached
here.
On running this piece of 1-line code, we have shown the below output. For each
value of the outer loop, the inner loop is executed up to its three values
i.e., 1, 3, 5. The output is presented in the affixed image.
$ bash bash.sh

Example 04: Nested For Loop

Let’s take another example to illustrate the working of the nested “for” loop.
This time, we have been using the outer loop for a total of 10 iterations
starting from 1 to 10. Within this loop, another “for” loop has been used. The
inner “for” loop has been utilizing the “seq” function to create a sequence of
any character multiplied by the iteration value of the outer loop. This means
the value of the outer loop will decide how many of the characters will be
displayed on the shell. Within the inner loop, we have used the “echo”
statement using the “-n” flag to test if the next string to be inserted in the
statement is some character or is empty. The character “*” has been added as a
value to be multiplied by the iteration number. The first “for” loop ends and
another “echo” statement will be used to just put the line break. The outer for
loop ends after 10 iterations. Let’s save this code to see its result on the
shell. The code is attached here.
On running this Bash code, we have got the below shown beautiful pattern of “*”
characters in a sequence of 1 to 10 increasing gradually. The output is
presented in the affixed image.
$ bash bash.sh

Conclusion

To sum up, this was all about the use of the nested “for” loop in the Bash
script of the Ubuntu 20.04 Linux system. We have discussed the examples to see
a simple “for” loop in Bash, nested “for” loop, and a one-line nested “for”
loop in Bash script.


About the author


Omar Farooq

Hello Readers, I am Omar and I have been writing technical articles from last
decade. You can check out my writing pieces.
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
