





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash For Loop 1 to 10

1 year ago
by Omar_Farooq
We all know that many of the basic concepts of programming contain many data
structures, variables, statements, and loops. Loops are very well-known among
all of them when running a series of instructions or doing some tasks under
certain conditions. The most famous and most used loop is the “for” loop. So,
today we will be looking at the syntax and working of the “for” loop for a
series of numbers, i.e., 1 to 10. Let’s start by opening a terminal shell with
the help of a “Ctrl+Alt+T” command on the Ubuntu 20.04 desktop system.

Example 01:

Our first example will cover the “for” loop for its most used syntax in the
programming language, i.e., simple brackets. Let’s make a bash file first with
the utilization of a “touch” query in your shell as per the output below.
$ touch bash.sh
The bash file has been successfully created in the basic home folder of Ubuntu
20.04. Open it within some editor tool to create a bash script in it. You can
also use the “vim” editor instead of the “nano” editor.
$ nano bash.sh
Now the file is opened in the GNU nano, 4.8 editors. We have added the bash
support in it at the start of a file. We want to run certain commands by using
the “for” loop for up to 10 iterations. The “for” uses simple brackets as the
first syntax and specifies the condition in it. The loop’s start value is “1”
as per the iterator “I”. It will continue to run until the iterator value
becomes less than or equivalent to 10. On every iteration, the iterator value
would be incremented by 1 until the iterator becomes 10. Within every
iteration, the “do” clause will be executed. It will run the “echo” statement
to show the iteration number using iterator “I”. Save this code by “Ctrl+S”.
Press Ctrl+X to exit the editor. Run your code using the “bash” keyword along
with the name of a file. You can see the output shows the result of 10
iterations achieved by a “for” loop.
$ bash bash.sh

Example 02:

The second easy method to use the “for” loop is to mention its iterations
within the curly brackets. Open the same bash file once again with the “nano”
command. Add the bash extension in it first. After that, the “for” loop has
been initialized with the word “for”. Now, you have to specify the iterator
variable “I” after the word “for”. To mention, the range of iterations in
brackets must be followed by the word “in” as per the below image. The range
has been defined from 1 to 10 with two dots in between. The “for” loop will
continue to run until 10 iterations, i.e., the “do” clause of the loop. The
main point about this syntax of the “for” loop is, there is no need to specify
the incrementation as it will automatically be incremented by 1.
The execution of this syntax for the “for” loop leads us to run the echo
statement within the “do” clause 10 times with the iteration number mentioned
below.
$ bash bash.sh

Example 03:

Another method to use the “for” loop in a bash script is quite similar to the
above method with a little change. In this technique, we will not be using any
brackets within the “for” loop. So, after the bash support, start the “for”
loop with the iterator variable “I” followed by the keyword “in”. After the
word “in”, you must specify the range as we have done within the code below,
i.e., 1 to 10. This loop will work as the above examples do and display the
message of the echo statement 10 times with the iteration number on the
terminal.
The code runs the “echo” statement 10 times with its iteration number as
expected.
$ bash bash.sh

Example 04:

Another unique way to define the “for” loop is using the “seq” expression in
it. So, open the same file and add the bash extension to it. The syntax of the
“for” loop has been shown in the snap attached below. The “for” loop has
started with the iterator variable “I” followed by the keyword “in”. Then we
have used the expression “seq” to define the range of this loop, i.e., 1 to 10.
The “seq” expression has been substituted by the single expression colons,
i.e., ““”. Until the sequence value reaches 10, the echo statement of a loop
will continue to be executed with the sequence number mentioned in it. You can
see this method has no increment expression mentioned in it. This means it will
automatically increment an iterator by 1.
 
After the execution of this “for” loop, the output is shown below. The display
shows the 10 iterations with the iteration number in the output line.
$ bash bash.sh

Example 05:

The last example is a bonus illustration of the “for” loop. The for loop has
been started, and the iterator “a” has been specified. This iterator is taking
English alphabets as their next consecutive iterator value. We have chosen the
first 10 English alphabets here, i.e., A to J. The “do” clause will continue to
run the echo statement that is used to display each alphabet every time until
the end of the loop. The loop ends here, and there is no proper increment
variable defined in this method as well.
Upon executing this bash code with the help of a bash command along with the
name of a file, we have got the 10 statements as an output showing alphabets
from A to J.
$ bash bash.sh

Conclusion:

The guide has covered a total of 5 methods to use the “for” loop in bash
script. All the examples used in this article are very simple to understand and
easy to implement by any naive bash user. Hence, we firmly believe that this
article will help every bash user.


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
