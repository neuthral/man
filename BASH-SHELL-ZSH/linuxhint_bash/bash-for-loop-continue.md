





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash For Loop Continue

8 months ago
by Omar_Farooq
Bash programming is quite well-known amongst Linux users. Within the bash
script, we tend to use many loops, statements, and clauses to perform different
operations. The most famous loop is the “for” loop in any programming language.
Bash programming came up with the “continue” and “break” statements. If you are
using any Linux distribution and want to know about the use of the “continue”
clause in the “for” loop, then this article is especially for you.

Example 01:

Let’s get started with our very first example of today’s Bash article. For
this, we need a Bash file. If you don’t have one, try creating it with the
“touch” instruction and name this file as “bash.sh”. To open this file, use the
“GNU Nano” editor. You may use the “nano” instruction along with the name of a
file to be opened. Now, the empty file is opened in the nano editor.
Let’s start the Bash code with the addition of bash extension i.e. “#!/bin/
bash”. We have been using the “for” loop here to utilize the “continue” clause
in it further. The loop will start from 1 and end at value 18 with an increment
of 2 at each iteration. On increment, we will achieve 3, 5, 7, 9, 11, 13, 15,
and 17. Within the “for” loop, we have been using the “do” clause to perform
some action until the loop ends. The “echo” clause is used to display each
iteration value i.e., “$i”.
Now, here comes the “if-then-else” statement within the “for” loop. In most
cases, we won’t be able to use the “continue” statement without this
declaration. So, the double square brackets are utilized to add the condition
to be checked in the “if” clause via the “-eq” operator. If the “$i” iteration
value gets equal to “11”, the echo statement will be executed and the loop will
be broken using the “break” clause.
Otherwise, the loop will execute its “else” part and execute the “continue”
clause to continue the loop towards the end. The “if-else” statement will be
ended after that and the loop will be completed. The example code for this
example is affixed here.
Let’s run this newly made Bash code within the terminal shell of Ubuntu 20.04
after saving it with Ctrl+S. After running this code with the “bash”
instruction, we have got the below-shown output. The loop started from the
value 1 and increment by 2 each time. Hence, it continues to show the iteration
value until the value “11” is reached. On reaching the “11” value, our
condition met and the loop got broken as shown in the image below. So, the
“echo” statement got executed and the loop doesn’t get executed anymore. Take a
look at the output of the code beneath.
$ bash bash.sh

Example 02:

Let’s take another example to use the “continue” clause in the “for” loop of
the Bash script. So, we have been opening the same bash file within the “nano”
editor. The Bash extension has been used at the first line. The for loop has
been initiated from 1 and it will complete at 10 with the increment of 1 at
each iteration. Within its “do” clause, we have been using the “if-then”
statement in a single line. It will check if the iteration value “$i is greater
than or equal to 4 and equal to or less than 8, the “then” statement will be
executed. The “-gt” operator for greater than, “-eq” operator for equal to, and
the “-lt” operator is used for less than has been used for the checking of
condition. Both conditions have been separated by && operator.
The “echo” statement will show the value on the shell after the condition got
satisfied and the loop will continue as per the “continue” keyword. Whenever
the value is between 4 and 8, it will continue to execute the loop and show the
value. Otherwise, the “if” statement will not be executed anymore. Let’s run
this code to see check happens. The example code for this example is affixed
here.
After executing the Bash file update code, the below-demonstrated code. Values
from 4 to 8 are displayed in the image. Take a look at the output of the code
beneath.
$ bash bash.sh

Example 03:

Take a glance at our article’s last illustration. So, we have started our Bash
code with the Bash extension and added a “for” loop starting from a and ending
at “e”. This “for” loop has been using the “if-then” statement to check out for
some conditions. If the iteration value from the “for” loop is “c” or “e”, it
will run its “then” statement and leads to the execution of the “echo”
statement. The “continue” clause will continue to iterate the loop if the value
is matched. After the “if-then” clause, another “echo” statement will be
executed showing the iteration value at that point if the value doesn’t match.
Now, the “for” loop has been completed as well as per the below output. The
example code for this example is affixed here.
Let’s run the Bash code file using the “bash” instruction. After running it, on
the execution of the first 2 iterations and 4th iteration of the “for” loop, no
value has been matched. Therefore, the “if-then” statement has not been
implemented. On the 3rd and 5th iterations, the value matched and the “if-then”
statement got executed. Take a look at the output of the code beneath.
$ bash bash.sh

Conclusion

Finally! We have done with the use of the “for” loop with the “continue”
statement in the Bash script. We have discussed a total of three examples to
illustrate the use of the “continue” clause in the “for” loop. The examples
covered in this article are easy to do and understand.


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
