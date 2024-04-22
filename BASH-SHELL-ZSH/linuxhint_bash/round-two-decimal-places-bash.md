





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Round to 2 Decimal Places in Bash

1 year ago
by Shehroz_Azam
Bash is a well-known shell and command language used for performing tasks
efficiently. While working in Bash scripting and explicitly playing with the
floating numbers, it is often needed to round off the floating numbers. In this
post, we will learn a few commands and techniques of Bash scripting to round
off the number to 2 decimal places.
While displaying the numbers or variables that include float numbers in them,
different commands can print the text or variables like echo, print, and
printf. Although we can show the variables and numbers directly from such
commands, however, the only command that has some extra features and
capabilities is the printf command that concerns our goal.

printf Command

The printf command is similar to the printf() function in C language. It allows
us to format and print the arguments.

Syntax

The syntax for writing the printf command in bash is:
printf "string" arguments
In the printf command, we first have to provide the string in inverted commas,
and then we can give it the arguments.

Example

Let’s first print a simple text using the printf command:
printf "Hello from Linuxhint."
You can see it has just printed out the string, but the username and hostname
come right after the string.
For getting the string in a single line, we can use the newline character ‘\n’
to have the clean and clear output:
printf "Hello from Linuxhint \n"
Now we have a clean and clear output.
Now, let’s see how to provide the arguments to give this printf command a float
number and round it off.
To provide the arguments, we need to use the specifier (%s) in the string which
will be replaced by the arguments provided. For example:
printf "User number: %s \n" 24
Alright, now you have understood the primary usage and functionality of the
printf command. Let’s provide it a float number and see how to round off to 2
decimal places.

Precision Directive

Precision modifier is used for rounding off a float number.
The syntax to write a precision modifier is to give the number of decimal
points you want to round off the number followed by the dot(.).
"%.2f"
To round off a float number to 2 decimal places, you can execute the printf
command as shown below:
printf "%.2f \n" 4.4444
You can see in the screenshot attached that the number “4.4444” is rounded off
to “4.44”, as we desired it to be.
Similarly, instead of directly providing it a number, we can give a variable
here as well.
num=4.4444

printf "%.2f \n" $num
To provide multiple values:
num1=3.333

num2=4.4444

printf "%.2f %.3f \n" $num1 $num2
If you still want to use the echo command and round off the number, in that
case, you have to use the echo command with awk command to round off the number
as shown below:
echo "3.333" | awk '{printf("%.2f \n",$1)}'
OR
num=3.333

echo num | awk '{printf("%.2f \n",$1)}'

Conclusion

This post contains a detailed and profound guide on the printf command and we
have learned to round off any number to 2 decimal places using the printf
command. In addition, we have tried several examples to have sound knowledge on
how to use the precision modifier to round off a number using the printf
command. Moreover, we learned to round off any float number using the echo and
awk command.


About the author


Shehroz Azam

A Javascript Developer & Linux enthusiast with 4 years of industrial experience
and proven know-how to combine creative and usability viewpoints resulting in
world-class web applications. I have experience working with Vue, React &
Node.js & currently working on article writing and video creation.
View_all_posts

RELATED LINUX HINT POSTS


* How_to_Take_Input_From_a_User_in_Bash_Script_[Advanced_Techniques]
* 10_Cool_and_Awesome_Bash_Loop_Examples
* How_to_Handle_Command_Line_Arguments_in_Bash?
* What_are_Double_Parentheses_in_Bash
* Floating_Point_Math_in_Bash
* Bash_Continue_Built-In_Statement
* 10_Most_Important_Things_to_Know_About_Bash_Scripting

Linux Hint LLC, [email protected]
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
