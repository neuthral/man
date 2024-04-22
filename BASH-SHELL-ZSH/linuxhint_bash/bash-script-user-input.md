





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Script User Input

1 year ago
by Fahmida_Yesmin
Taking input from the user is a common task for any programming language. You
can take input from a user in bash script in multiple ways. A read command is
used in the bash script to take data from the user. Single or multiple data can
be taken in bash script by applying different options of the read command. Some
common uses of the read command are shown in this tutorial.

Option of Read Command:


Option Purpose
-p     It is used to provide a helping message for the user before the input
       prompt.
-s     It is used to take invisible input from the user. This option is used to
       take a password or secret data. It is called silent mode.
-t     It is used to set time in seconds to wait for taking input from the
       user.
-n     It is used to set the limit of input characters.


Example-1: Use of read command without variable

The read command can be used without any variable. The $REPLY variable is used
to read the input taken from the user by the read command without variable.
Create a bash file with the following script to know how to use the read
command without any variable.
#!/bin/bash  
   
echo "What is your favorite programming language?"  
# Take input without defining variable    
read  
# Print the input value
echo "Your answer is $REPLY"
Output:
The following output will appear after executing the above script.

Example-2: Using simple read command

Create a bash file with the following script to know how to use the read
command with a variable. After running the script, the program will wait for
the user input. When the user types the data and press enter, the data will be
stored in the answer variable. The value of the answervariable will be printed
later.
#!/bin/bash
echo -n "What is your favorite food: "
# Assign input value into a variable
read answer
# Print the value of the variable
echo "Oh! you like $answer!"
Output:
The following output will appear after executing the above script.

Example-3: Using read command with options

Create a bash file with the following script to know how to use both –p and –s
options together in the bash script. In this example, the username and password
will be taken from the user and compared with the particular value to check the
username and password are valid or not.
#!/bin/bash
# Type your Login Information
read -p 'Username: ' user
read -sp 'Password: ' pass

# Check the username and password are valid or not
if (( $user == "admin" && $pass == "12345" ))
then
    echo -e "\nSuccessful login"
else
    echo -e "\nUnsuccessful login"
fi
Output:
The following output will appear after executing the above script.

Example-4: Using read command to take multiple inputs

The multiple inputs can be taken at a time by using the read command with
multiple variable names. In the following example, four inputs will be taken in
four variables by using the read command.
#!/bin/bash

# Taking multiple inputs
echo "Type four names of your favorite programming languages"
read lan1 lan2 lan3 lan4
echo "$lan1 is your first choice"
echo "$lan2 is your second choice"
echo "$lan3 is your third choice"
echo "$lan4 is your fourth choice"
Output:
The following output will appear after executing the above script.

Example-5: Using read command with the time limit

Create a bash file with the following script to take time-restricted input from
the user. Here, the time will be counted in seconds. In the following example,
the program will wait for 5 seconds for the user’s input, and if the user is
unable to type the data within 5 seconds, the program will exit without value.
#!/bin/bash
# Take input with time limit
read -t 5 -p "Type your favorite color : " color
# Print the input value
echo $color
Output:
The following output will appear after executing the above script. The input
value has been given in the first execution, and in the second execution, no
input value has been given within 5 seconds.

Example-6: Use of read command with -n option

Create a bash file with the following script to take input of a specific
length. According to the script, the user will be able to enter a maximum of 15
characters as input.
#!/bin/bash

echo "Enter your phone number(Maximum 15 characters):"
# Take input of a maximum 15 characters long
read -n 15 phone
# Add a newline
echo
# Print the input value
echo "Your phone number is $phone"
Output:
The following output will appear after executing the above script.

Example-7: Checking a taken path is file or directory

Create a bash file with the following script to take input a path value from
the terminal and check the input path is a directory or file.
#!/bin/bash

# Take the path value from the input
read -p "Enter the valid path: " path

# Check the input values is a directory or not
if [ -d $path ]; then
     echo "$path is a directory."
# Check the input values is a file or not
elif [ -f "$path" ]; then
     echo "$path is a file."
else
     echo "Invalid path."
fi
Output:
The following output will appear after executing the above script.

Example-8: Initialize array using the read command

The array variable can be declared and initialized by using the read command.
Create a bash file with the following script to know how to create and
initialize an array by using the read command. Next, all elements of the array,
the first element of the array, the first two elements, and the last element of
the array will be printed.
#!/bin/bash  

echo "Enter five numeric values for the array with space:"
# Read values for the array
read -a MyArr

# Print all array values
echo  ${MyArr[@]}

# Print the first value of the array
echo  ${MyArr[0]}

# Print the first two values of the array
echo  ${MyArr[@]:0:2}

# Print the last value of the array
echo  ${MyArr[4]}
Output:
The following output will appear after executing the above script.

Conclusion:

Different uses of the read command have been shown in this tutorial by using
multiple examples for helping the bash users to know the uses of this command
properly and apply it to their script.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
