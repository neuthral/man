





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Redirect stderr to stdout in Bash

2 years ago
by Sam_U
Commands in Linux take some input from the user, which could be a file or any
attribute, and upon executing, they give some output called standard output.
The standard output could be a success output or an error output; both will be
displayed on your terminal screen. But in some cases, you want to store
standard outputs to a file for testing or debugging of the code. In Linux,
these outputs can be redirected to a file, and the process of capturing it
called redirection.
Every process In Linux produces three data streams, “stdin,” “stdout,” and
“stderr”:

* stdin: Takes input from the user via keyboard
* stdout: Displays output on the screen
* stderr: Shows error information on the screen

Every data stream has a numeric id:

Numeric Id Name
0          stdin
1          stdout
2          stderr

Let’s explain redirection a bit more with detail:

How to redirect Standard output and Standard error in Bash:

To redirect the standard output of the command, we will use “1” with a
redirection operator that is greater than the “>” sign:
$ls 1> stdout.txt
The above command will create a file and place the standard output of the “ls”
command in the “stdout.txt” file.
To read the “stdout.txt” file, use:
$cat stdout.txt
We can redirect standard error to a file as well by using the command:
$cat myfile.txt 2> stderr.txt
To view the “stderr.txt” file, use:
$cat stderr.txt
Make sure use “2” will greater than the “>” sign. Since there is no
“myfile.txt” file in the directory, the “cat” command will give an error that
will be appended in the “stderr.txt” file.
These standard outputs can be redirected with a single command also, use:
$ls 1> stdout.txt 2> stderr.txt
The output of the “ls” command will be written in the “stdout.txt” file, but
the “stderr.txt” will remain empty because there would be no error.
Now let’s do for “stderr.txt”:
$cat myfile.txt 1> stdout.txt 2> stderr.txt
Use the below-mentioned command to read “stderr.txt.”
$cat stderr.txt
And of course, “stdout.txt” will be empty.

Conclusion:

Linux command upon executing gives standard output that could be a success
output or an error output. Generally, these outputs cannot be redirected using
redirection operators; we need to use specific numeric ids with the “>” sign.
In this guide, we learned how to use these numeric keys to redirect standard
output to a file with examples.


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
