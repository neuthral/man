





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


10 Most Important Things to Know About Bash Scripting

1 week ago
by Prateek_Jangid
Linux contains various types of shell scripting such as sh, csh, ksh, tcsh,
Bash, etc., but Bash or Bourne Again Shell is the most famous one. Bash is a
fantastic command line shell that works as a scripting language. Although Bash
does not contain a full-blown programming language, it supports loops,
variables, conditions, and chaining commands. Therefore, Bash is much more
grown than the regular command-line interpreter.
It allows you to use the shell abilities and automate various tasks. After
mastering Bash for administrative tasks, you can quickly learn Python as you
have a solid knowledge of Linux’s capabilities. However, a few things are
essential to follow while creating Bash. So in this guide, we’ll list the 10
most important things to know about Bash scripting.

10 Most Important Things to Know About Bash Scripting

Now let’s discuss all the essential factors you need while working on a bash
script:

Use the Special Characters Correctly

In Bash, you can use strings that include plain words. However, it can be an
issue when you use a special character with a different meaning in the script.
So here is the list of special characters that have different meanings in Bash:

Special Characters     Description
$_                     Represents the absolute path of a shell executing the
                       particular script.
$0                     Shows the path of Bash script execution.
$N                     Shows the Nth argument passed for the Bash script
                       execution.
$*Or [email protected]Represents all the arguments passed for the Bash script
                       execution.
$#                     Represents the number of arguments passed for Bash
                       script execution.
$?                     Shows the exit status code of the last foreground
                       command executed.
$!                     Represents the process ID of the last background command
                       executed.
$$                     Shows the process ID of the Bash script execution.

That’s why we recommend you use the special characters correctly. For instance,
if you want to use * in the string, please use \* or “*” rather than * only.

Key Bindings

As a bash user, you must focus on the key bindings to increase your working
efficiency. Many users still need to learn the correct key bindings for bash
and sometimes get errors. So here is the list of all key bindings you can use
for bash:

*
  o CTRL and A to move the cursor at the start of the line.
  o CTRL and E to move the cursor at the end of the line.
  o ALT and F to move the cursor forward a word.
  o ALT and B to move the cursor backward.
  o CTRL and L to clear the current screen except for the current command.
  o CTRL and U to capitalize the word
  o ALT and Lto lowercase the word
  o CTRL and C to interrupt the currently running process
  o CTRL and S to stop the output
  o CTRL and Q to resume output
  o CTRL and Zto suspend the current process.



Create Clean Structure

As a bash user, it is essential to describe everything correctly. For example,
declare the global variables first and then go for the functions to make the
structure cleaner and more explainable. Furthermore, ensure that you use the
local variables in the function and then write the main body of the script.

Get Your Hands on Scripts

If you are a beginner and want to sharpen your skills, create as much script as
possible. It will improve your critical thinking over shell scripting and allow
you to create interactive scripts easily. Moreover, you can visit our official
website to learn about bash through our courses.

Debug the Script

After writing thousands of lines of code, the worst thing you can face is
getting errors and fixing those in the script. To avoid the mess, you should
always debug the script before execution. We can enable shell debugging mode
using the following:

*
  o -v: to activate the verbose mode, –v is used. All lines in the script will
    be shown while reading the script
  o -n: to check the syntaxes –n is used
  o -x: to activate shell tracing mode



Adopt Command Substitution

You can use $(VAR) rather than “(VAR)” as a command substitution to use the
output of the command inside the other. For example, if you want to  show a
command in another, please use the following script:
#!/bin/bash
information=$(ls -h)
 echo $information
 
This script will print all the names available in the home directory:

Functions are Important

The function is nothing but a reusable piece of code. You need to write the
code once, and you can reuse it multiple times. Use functions to write huge
lines of code in your script. Functions not only help to divide the code into
modules but also make your code more readable. Use functions to modularize your
program or script to make your code more professional and easy. Following is
the syntax to write the functions:
function get_value(){
        statement1;
        statement2;
}
 
OR
get_valuet(){
        statement1;
        statement2;
}
 
As you can see, “;” is a termination character for a single line of code or
command.

Work Smartly With = and ==

Unlike other programming languages, the bash script uses a single “=” character
to compare two variables with each other. In programming languages like Python,
we use double equal to the “==” character for comparing two variables. See the
example for more details:
#Comparison of two strings in bash script
str1= “hello”
str2= “User”
if [ "$str1" = "$str2" ]
 
In the above example, first, we have declared two variables, str1 and str2.
Then we compare those variables with a single “=” character. Although there is
no huge difference between == and =, you can use = instead of == to work
efficiently.

Write Comments

A comment is a description or information about the statement in the code. The
comment feature is available in bash and various programming languages. Proper
use of comments makes the code understandable to the developer. Furthermore, it
is a good practice that helps to keep track of the code or to update the code.
In bash, scripting comments start with “#,” and here is an example:
#This is an example of a comment in bash scripting
 
Similarly, we use # at the beginning of the sentence to start the comments in
Python. See the following example:
#This is an example of a comment in Python
 

Verify the Positional Arguments

The positions of the positional arguments matter because it is important to
place the first positional argument when the first function is called. So in
case you want to get the arguments directly through the position without any
extra function, then you can use the following verification script:
#/bin/bash
echo "Here are the entered details:"
Student name=${1:?"Name not entered"}
ID=${2:?"ID not entered"}
Branch=${3:?"Branch not entered"}
Age=${4:?"Age not entered"}
 
This above script will give the following result if you don’t enter specific
details:

Wrapping Up

So, this is all about the 10 basics you should know before writing the bash
script. These basics will definitely help you write a thousand lines of bash
script without any hesitation. Moreover, if you want to know more about the
bash script-related tricks, please check out our official website.


About the author


Prateek Jangid

A passionate Linux user for personal and professional reasons, always exploring
what is new in the world of Linux and sharing with my readers.
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
