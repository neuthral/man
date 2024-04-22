





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Z Test Condition in Bash

2 weeks ago
by Prateek_Jangid
In Bash, the characters and strings can be represented as other sequence
structures and data types. Computers do not use strings for storing
information, but they are useful for transferring it from one program to
another.
Sometimes, it is essential to check whether a string is empty, as it clarifies
the intent of the string. You can use the -z flag with the test command to test
the string. However, the -z test condition in Bash sometimes becomes confusing
for beginners. In this tutorial, we will explain through examples on how to use
the -z test condition in a Bash script.

Z Test Condition in Bash

You can test in Bash whether your string is empty using the z-test condition.
If the string is empty, it returns 0; otherwise, it returns 1. The general
syntax to execute the z-test condition in Bash is as follows:
test -z <stringname>

echo $?
The “echo $” command tells you whether the command you have written is correct.
This command also returns 0 if the previous command is true and 1 if it is
false. Let’s create a string and check with the z-test condition whether the
string is empty.
#!/bin/bash

name= 'jack'

details= "This script is related to $name, from the programming world"

echo $details

Output:

Upon running the given Bash script, we get 1 in our output, which means that
our string is not empty. This way, you can check whether your string is empty
with the z-test condition in Bash.

Conclusion

Strings are a data type that includes a sequence of characters, elements, etc.
It comes in handy when communicating the information from a program to a
program user. You can check this in Bash using the z-test condition. In this
tutorial, we used an example to show you how to check if a string is empty
using the z-test Bash condition.


About the author


Prateek Jangid

A passionate Linux user for personal and professional reasons, always exploring
what is new in the world of Linux and sharing with my readers.
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
