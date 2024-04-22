





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


BASH while loop examples

1 year ago
by Fahmida_Yesmin
Three types of loops are used in bash programming. While loop is one of them.
Like other loops, a while loop is used to do repetitive tasks. This article
shows how you can use a while loop in a bash script by using different
examples.
Syntax of while loop:
while [ condition ]
do
    commands
done
The starting and ending block of the while loop is defined by do and
donekeywords in the bash script. The termination condition is defined at the
starting of the loop. Open a text editor to write a bash script and test the
following while loop examples.

Example-1: Iterate the loop for a fixed number of times

Create a bash file named while1.sh with the following content. Here, the loop
will iterate 5 times and print the counter value in each iteration.
#!/bin/bash

# Initialize the counter
n=1
# Iterate the loop for 5 times
while [ $n -le 5 ]
do
    # Print the value of n in each iteration
    echo "Running $n time"
    # Increment the value of n by 1
    (( n++ ))
done
Output:
The following output will appear after executing the above script.

Example-2: Using break statement for conditional exit

the break statement is used to exit from the loop early based on a particular
condition. Create a bash file named while2.sh with the following code. Here,
the loop is defined to iterate 10 times, but the iteration will be stopped when
the counter value is 6.
#!/bin/bash

# Initialize the counter
n=1
# Iterate the loop for 10 times
while [ $n -le 10 ]
do
    # Check the value of n
    if [ $n == 6 ]
    then
        echo "terminated"      
        break
    fi
    # Print the current value of n
    echo "Position: $n"
    # Increment the value of n by 1
    (( n++ ))
done
Output:
The following output will appear after executing the above script.

Example-3: Using continue statement to omit particular step

Create a bash file named while3.sh with the following code. In this example,
the loop will iterate for 5 times, but it will not print all 5 positions. When
the loop iterates for the 3rd time, the continue statement will be executed,
and the loop will go for the next iteration without printing the text of the
3rd position.
#!/bin/bash

# Initialize the counter
n=0
# Iterate the loop for 5 times
while [ $n -le 5 ]
do
    # Increment the value of n by 1
    (( n++ ))
   
    # Check the value of n
    if [ $n == 3 ]
    then
        continue
    fi
    # Print the current value of n
    echo "Position: $n"
   
done
Output:
The following output will appear after executing the above script.

Example-4: Read the command-line argument with options

Create a bash file named while4.sh with the following code. Here, the loop is
used to read the command-line arguments with options. The script will print the
formatted argument values after the execution if the three-argument values pass
with the valid option.
#!/bin/bash

# Read the command-line arguments values with option using loop
while getopts n:a:e: OPT
do
        case "${OPT}"
        in
           n) name=${OPTARG};;
           a) address=${OPTARG};;
           e) email=${OPTARG};;
           *) echo "Invalid option"
              exit 1;;
        esac
done
# Print the argument values
printf "Name:$name\nAddress:$address\nEmail:$email\n"
Output:
The following output will appear after executing the above script.

Example-5: Read file line by line

Create a bash file named while5.sh with the following code. Here, a filename
will be given in the first command-line argument at the execution time. If the
file exists, then the content of the file will be printed line by line using
the loop; otherwise, an error message will be printed.
#!/bin/bash

# Check the command-line argument value is given or not
if [ $# -gt 0 ]; then
    # Assign the filename from comand-line argument value
    filename=$1
   
    # Read file line by line
    while read line; do
        # Print each line
        echo $line
    done < $filename
else
    # Print message if no argument is provided
    echo "Argument value is missing."
fi
Output:
The following output will appear after executing the above script.

Example-6: Write content into a file

Create a bash file named while6.sh with the following code. Here, the filename
will be taken from the user in which the text content will be written. The user
has to type Ctrl+D after typing the content of the file.
#! /bin/bash

echo -n "Enter the filename to create: "
# Take the filename that will be created
read filename
# Read the content of the file from the terminal
while read line
do
    echo $line >> $filename
done
Output:
The following output will appear after executing the above script.

Example-7: Creating an infinite loop

Sometimes, it is required to declare an infinite loop for various programming
purposes. Create a bash file named while7.sh and test the code of the infinite
loop. No termination condition is set for the loop in this example. This type
of loop is called an infinite loop. Here, an exit statement is used to quit
from the infinite loop. So, this loop will be iterated 10 times, and when the
iteration value becomes equal to 10, the exit statement will execute for
exiting from the infinite loop.
#!/bin/bash

# Initialize the counter
n=1
# Declare an infinite loop
while :
do
    printf "The current value of n=$n\n"
    if [ $n == 3 ]
    then
        echo "good"
    elif [ $n == 5 ]
    then
        echo "bad"
    elif [ $n == 7 ]
    then
        echo "ugly"
    elif [ $n == 10 ]
    then
        exit 0
    fi  
    # Increment the value of n by 1
    ((n++))

done
# Take the filename that will be created
read filename
# Read the content of the file from the terminal
while read line
do
    echo $line >> $filename
done
Output:
The following output will appear after executing the above script.

Example-8: Using C-style while loop

Create a bash file named while8.sh with the following code. Here, the while
loop has been declared in a c-style format that will iterate 5 times by
incrementing the counter value by 10.
#!/bin/bash

# Initialize the counter
n=5
# Define the while in C-style
while((n <= 50))
do
   echo $n
   # Increment counter by 10
   ((n=n+10))
done
Output:
The following output will appear after executing the above script.

Conclusion:

Different uses of the while loop have been explained in this tutorial by using
multiple examples. I hope the bash user will be able to use this loop properly
in their script after practicing these examples.


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
