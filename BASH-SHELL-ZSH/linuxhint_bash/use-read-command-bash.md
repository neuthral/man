





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use the read Command in Bash

2 years ago
by Sam_U
In Bash scripting, the “read” command is used to obtain input from users.
Understanding the “read” command is key to making your code more interactive.
The “read” command is used to obtain inputted information from the user. This
article shows you how to use the “read” command in Bash to interact with users.
First, check out the basic syntax of the “read” command:
read [option] variable
Using the “read” command means that you are interacting with Bash to obtain
information from the user. It saves the value in a variable, but with no “$”
sign. You will be able to better understand this concept with an example.

Example 1: Using the “read” Command in a Bash Script

To examine the “read” command more in-depth, we will create a simple script
that will ask for the user’s name. First, open any text editor; for this
tutorial, I am using the Vim text editor due to its many useful features. To
install Vim, execute the following command in the terminal:
$sudo apt install vim
Next, type the following in the text file:
#! \bin\bash

echo “Please type your name”

read name

echo “Your name is” $name
Save the file by any name, then press Esc and type “:w readcom.sh.” To run the
script, issue the following command:
$ bash readcom.sh
The above script will ask the user to write his/her name. The “read” command
will then save the input from the user. The next line will print the name that
the user input.

Example 2: Simplifying Code Using the “prompt” Operator

The above example can be simplified further using the “prompt” operator. Let us
re-write the above example to comprehend the code:
#! /bin/bash

read –p “Please type your name” name

echo “Your name is” $name

Example 3: Hiding the User Input Using the “secret/silent” Operator

The “-s” flag can be used to hide the input of the user. The following Bash
script example shows you how to use the “-s” operator:
#! /bin/bash

read –p “Please type your username” username

read –s –p “Please type your password” $password

Example 4: Limiting the Character Length

The “-n” flag can be used to add a constraint to the number of characters that
the user may input.
#!/bin/bash

read –n 8 –p “Please type your username not exceeding 8 characters” username

echo “Your username is” $username
With the “-n” option, the user can still write less than eight characters. To
further restrict the input length, the “-N” flag can be used, which limits the
user’s response to exactly eight characters.

Example 5: Getting the Input in an Array

The user input can also be taken in an array with the “-a” flag. For instance,
to get the user’s name, age, and email address in one go, then we can use an
array. Let us look at an example:
#! /bin/bash

echo “Please type your name, age, and email”

read –a array name age email

echo “Your name, age, and email address are: ${array[@]} name age email”

echo “Your name and age are: ${array[@]:0:1} name age”

echo “Your email address is: ${array[2]} email”

* “${array[@]}” will loop through all variables.
* To iterate through the indexes 0 to 1, use “${array[@]:0:1}” with the
  variable names.
* To obtain the value of a particular variable at a specific index, use “$
  {array[2]}” with the variable name.


Example 6: Adding a Timeout to the “read” Command

As the name of the command indicates, a timeout can be added as a condition of
reading the code using the “-t” flag, which makes the user enter information
for a specific time. Otherwise, the program will move to the next line of code.
#! \bin\bash

echo “What is the capital of Japan? Answer in 5 seconds”

read –t 5 answer


if [ “$answer” = “tokyo” ] || [ “$answer” = “Tokyo” ];

then

echo “Your answer is Correct!”

else

echo “Your answer is Wrong!”

fi

Conclusion

Getting input from a user input is one of the most important parts of
programming, making your programs more interactive. This article showed you how
to use the “read” command, one of the key commands in Bash scripting. In this
article, you learned about some of the various approaches that you can use with
the “read” command, from basic flag operators to advanced operators.


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
