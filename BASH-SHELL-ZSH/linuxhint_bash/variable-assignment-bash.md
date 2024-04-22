





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Variable Assignment

2 weeks ago
by Prateek_Jangid
Variables in Bash can be a character, a number, or any string that is nothing
more than a pointer to actual data. You can specify any value such as a
filename, device name, text, number, or data type. Shell has multiple options
to create, edit, and execute the scripts easily. Assigning multiple variables
in a Bash script makes your code look compact and benefits better performance.
Assigning variables in one line of code in languages such as PHP, Python, etc.
is easy. In this tutorial, we will give you the complete brief on the variable
assignment in Bash.

Variable Assignment in Bash

Entering a variable in the Bash script is simple, so let’s start with a simple
example to print a variable:
#!/bin/bash
NAME="Mr.Valuable"
echo "Name of the content write is $NAME"
Once we execute the script, it automatically prints the entered variable in the
output:
./<script>.sh
Next, let’s create a script to give a clear overview of the variable assignment
in Bash. For example, if we want to assign multiple variables, we can use the
following script:
!/bin/bash
read var_1 var_2 var_3 var_4

echo "$var_1 is the best."
echo "However, you can try $var_2."
echo "Or else you may use $var_3."
echo "In case you are a beginner, $var_4 is the best."
You may get the following result by executing the script in the terminal:
./<script>.sh
Similarly, you can assign the numbers to print the script’s output accordingly.
For instance, you can change the value of “X” and print them in the terminal
through the following script:
#!/bin/bash
echo
X=142
echo "Value "X" is now $X."
let X=231+3
echo "Value of "X" is now $X."
echo
echo -n "values of "X" in the loop are:"
for X in 4 5 6 7
do
 echo -n "$X"
done
Now, let’s execute the script, and the system will ask you to assign a variable
to print the output:
./<script>.sh

Conclusion

This is how you can assign the variables in the Bash script. The read command
is simple and prints the input in the terminal. Moreover, we also included a
different example to explain the variable assignment in Bash. If you want to
know more about the Bash-related stuff, don’t worry because Linuxhint has
everything for you.


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
