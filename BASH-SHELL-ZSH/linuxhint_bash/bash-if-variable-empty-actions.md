





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash If Variable is Empty Do Actions

1 year ago
by John_Otieno
Bash scripting is one of the perks of using Linux. It allows us to create
customized commands and tools to automate our daily tasks. Like most
programming languages, Bash gives us conditional statements to check for
specific conditions and perform actions based on the result.
This tutorial will show you how to use conditional statements to check if a
variable is empty and then perform an action after the fact. Such actions can
include looping a block of code until the variable is not empty, quit or simply
alert the user that the variable is empty.
Before we get started, it will be useful if you are familiar with basic Bash
scripting.

Bash Basic – Variables 101

Variables are core building blocks of any real programming language, and Bash
uses variables. Variables are data containers used to store values for use in
later sections of the program.
To create a simple variable in Bash, we use the name of the variable.
For example:
#!/bin/bash

$i_am
Once you have the variable initialized, you can assign the value to it by using
an equal sign as:
#!/bin/bash

i_am=ubuntu
Once it has been declared and assigned, you can call it by simply referencing
it by name as:
#!/bin/bash

echo $i_am
This will return the value stored in the variable, as shown in the screenshot
below.
NOTE: Referencing a variable in both single quotes and double quotes returns
different results. A variable inside single quotes will become a string
literal, while in a double quote, it gets the treatment of a variable name.
Here’s an example:
Now that we have the basics of variables in Bash, we can proceed to
conditionals and checking for an empty variable.
For a detailed guide on how to create bash variables, consider the resource
below:
https://linuxhint.com/variables_bash/

Bash Basics – If Statements

If statements are another fundamental programming block and Bash would be a
cripple without them. They allow us to perform an action if a condition is true
or false.
Let us take a quick recap of how to use Bash if, if…else and if…elif…else

The if Statement

The general syntax for using an if statement in Bash is as shown below:
#!/bin/bash

if {condition}

then

do

fi
We start an if statement by calling the if keyword. We then follow by
specifying the condition to check. The condition can be a simple or a complex
expression as long it evaluates to true or false.
Next, we set the keyword that specifies the code block to run if the condition
evaluates to true.
Finally, we close the if statement using the fi keyword.

If…else statements

A bash if…else statement specifies an extra action if the condition evaluates
to false. The general syntax is:
#!/bin/bash

if {condition}

then

do

else

do

fi

An Example Use Case

Allow me to use a simple example to illustrate the use of if statements.
The if statement is as shown below:
#!/bin/bash
num=1
if [[ $num -gt5 ]]
then
    echo "$num is greater than 5"
else
    echo "$num is less than 5"
fi
The output is as shown below:
Since we now have the basics of if statements ironed out, let us proceed with
this tutorial.
Check if statements in details below:
https://linuxhint.com/bash_conditional_statement/

How to Check if Variable is Empty

A popular and simple way to check if a variable is empty is to use the -
z option in the condition statement.
The -z $var returns true if a variable is empty and false if not.
The general syntax for such a test is:
#!/bin/bash
if [[ -z $var ]]
then
    do
else
   do
fi

Example Script

Let us illustrate a simple script that emulates the cd command and navigates
the specified directory.
Consider the script below:
#!/bin/bash
echo "Enter path to navigate to: "
 
read _path
 
while [[ -z $_path ]]; do
    echo "Please provide a path"
done
echo "Navigating to $_path"
cd $_path
Once we execute the above query, we get the output as shown below.
The script starts by asking the user to enter the directory to navigate to. It
then checks if the variable is empty. If empty, it recursively asks the user
for a path until the variable is not empty.
Once the path is available, it navigates to the set directory and prints the
status.

Conclusion

This short tutorial showed you how to check if a variable is empty using the -
z flag. This checks if the length of the variable is 0 and if 0, the variable
is empty. This can be very powerful when you need the value of a variable to be
true before proceeding.
You can also combine the above statement with other expressions to create a
complex tool if the variable is empty or not.
Thank you, and Happy Scripting time!!


About the author


John Otieno

My name is John and am a fellow geek like you. I am passionate about all things
computers from Hardware, Operating systems to Programming. My dream is to share
my knowledge with the world and help out fellow geeks. Follow my content by
subscribing to LinuxHint mailing list
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
