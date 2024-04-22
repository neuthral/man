





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Arithmetic Operation

1 year ago
by Fahmida_Yesmin
Doing arithmetic operations in bash is not similar to other standard
programming languages. One of the limitations of bash is that it can’t handle
floating point or double numbers like other scripting languages. Another
command tool is used in bash to solve this problem. Different types of
arithmetic operations are shown in this tutorial by using different examples.

Example – 1: Using ‘expr’ Command

The oldest command for doing arithmetic operations in bash is ‘expr‘. This
command can work with integer values only and prints the output directly in the
terminal. You have to use space with each operand when you want to use the
‘expr’ command to do any mathematical operations. Create a bash file named
expr.bash with the following script to know the use of ‘expr’ command.
#!/bin/bash

# Works as the string
expr '10 + 30'

# Works as the string
expr 10+30

#Perform the addition
expr 10 + 30

#Find out the remainder value
expr 30 % 9

#Using expr with backtick
myVal1=`expr 30 / 10`
echo $myVal1  

#Using expr within command substitute
myVal2=$( expr 30 - 10 )
echo $myVal2
Run the following command to execute the script.
$ bash expr.bash
Output:
The output shows that arithmetic operators worked only when space is used with
each numeric value and no single quotation is used with the expr command. You
can also assign the output of the exprcommand into a variable and print the
variable later by using backtickor command substitute. 30/10 is calculated by
using backtick and 30-10 is calculated by using command substitute.

Example – 2: Using ‘let’ Command

‘let’ is another built-in command to do arithmetic operations in bash. ‘let’
command can’t print the output to the terminal without storing the value in a
variable. But the ‘let’ command can be used to remove the other limitations of
the ‘expr’ command. Create a bash file named let.bash with the following script
to know the use of the ‘let’ command.
#!/bin/bash

# Multiplying 9 by 8
let val1=9*3
echo $val1

# Dividing 8 by 3
let "val2 = 8 / 3"
echo $val2

# Subtracting 3 from 9
let val3=9-3
echo $val3

# Applying increment
let val4=7
let val4++
echo $val4

# Using argument value in arithmetic operation
let "val5=50+$1"
echo $val5
Run the following command to execute the script.
$ bash let.bash 50
Output:
The output shows that the ‘let’ command is more flexible than the ‘expr’
command. You can evaluate any arithmetic expression with or without quotations.
But you can’t use space within any mathematical expression. The increment or
decrement operator can be used in the ‘let’ command. How the arithmetic
operation can be done with the argument values using the ‘let‘ command is shown
in the last part of the example.

Example – 3: Using Double Brackets

Any arithmetic operation can be done in bash without using any command. Here,
double brackets are used to do the arithmetic tasks, and using double brackets
for executing mathematical expressions is more flexible than the command like
the ‘expr’ or ‘let’. Create a bash file named dbl.bash with the following
script to test the arithmetic operations by using double brackets.
#!/bin/bash

# Calculate the mathematical expression
val1=$((10*5+15))
echo $val1

# Using post or pre increment/decrement operator
((val1++))
echo $val1
val2=41
((--val2))
echo $val2

# Using shorthand operator
(( val2 += 60 ))
echo $val2

# Dividing 40 by 6
(( val3 = 40/6 ))
echo $val3
Run the following command to execute the script.
$ bash dbl.bash
Output:
The output shows that double brackets can execute any mathematical expression
with space or without space and you can also use increment/decrement and
shorthand operators in double brackets expressions.

Example – 4: Using ‘bc’ Command for Float or Double Numbers

One of the major limitations of the above ways of doing arithmetic operations
in bash is that ‘expr’ or ‘let’ or double brackets expressions are not able to
produce floating-point or double numbers. The output of division operations of
the above examples are integers. ‘bc’ command can be used to solve this problem
and it works as a basic calculator for the Linux operating system. Create a
bash file named bc.bash with the following script to know the use of the ‘bc’
command in arithmetic operations.
#!/bin/bash

# Dividing 55 by 3 with bc only
echo "55/3" | bc

# Dividing 55 by 3 with bc and -l option
echo "55/3" | bc -l

# Dividing 55 by 3 with bc and scale value
echo "scale=2; 55/3" | bc
Run the following command to execute the script.
$ bash bc.bash
Output:
The output shows that the simple ‘bc’ command produces integer value like other
options when any division expression is executed. ‘bc -l’ command generates the
exact output of the division and you can limit the fractional part by using
scalevalue. Here, scale=2 is used. So the output shows 2 digits after the
decimal point.

Example-5: Using the printf Command for Float or Double Number

The `printf` command is another way to work with fractional data. This command
can be used to generate the floating-point value more efficiently than the `bc`
command after the arithmetic operation. This command can also be used to
calculate the power of a number. The uses of the `printf` command for different
arithmetic operations have shown in this example. Create a bash file named
prn.bash with the following script to check the use of the `printf` command for
the fractional output of the division of two numbers.
#!/bin/bash
# Take the dividend value from the user
read -p "Enter the dividend value: " n1
# Take the divisor value from the user
read -p "Enter the divisor value: " n2

# Find the division using `echo` and `bc`
echo "scale=2; $n1/$n2"|bc

# Find the division using `printf`
printf "%.2f\n" "$((10**2 * $n1/$n2))e-2"
Run the following command to execute the script.
$ bash prn.bash
Output:
The following output shows that the division value generated by the `bc` and
`printf` commands of two integer numbers are the same.
The following output shows that when the dividend value is a floating-point
number then the division value generated by the `bc` command is correct but the
`printf` command generated an error.
Create a bash file named prn2.bash with the following script to know the use of
the `printf` command for the correct fractional output when the dividend value
is a floating-point number.
#!/bin/bash
# Take the dividend value from the user
read -p "Enter the dividend value: " n1
# Take the divisor value from the user
read -p "Enter the divisor value: " n2

# Find the division using `printf`, `echo` and `bc`
printf "%.2f\n" `echo $n1/$n2|bc -l`
Run the following command to execute the script.
$ bash prn2.bash
Output:
The output shows that the `printf` with ‘`bc` command generates the correct
output.

Example-6: Using the awk Command for Arithmetic Operation

Using the `awk` command is another way to perform the arithmetic operation that
can generate output properly for floating-point numbers. The arithmetic
operations using the `awk` command without formatting and with formatting have
shown in this example. Create a bash file named awk.bash with the following
script to check the use of the `awk` command for arithmetic operation.
#!/bin/bash
# Initialize the dividend value
n1=90
# Initialize the divisor value
n2=43

# Print the output without formating
awk "BEGIN {print $n1/$n2}"
# Print the output with formatting
awk "BEGIN {printf "%.2f\n", $n1/$n2}"
Run the following command to execute the script.
$ bash awk.bash
Output:
The output shows that the `awk` command can generate appropriate fractional
output.

Example-7: Calculate the Percentage of a Value

Sometimes we need to calculate the percentage value of particular criteria. The
percentage can be calculated in bash by using the `printf` command and `echo`
command. Suppose, we need to find out the percentage of passed students on an
exam based on the total number of students and total passed students. The
solution to this problem has shown in this example. Create a bash file with the
following script to calculate the percentage value of passed students using the
`printf` command.
#!/bin/bash
# Take the total number of students from the user
read -p "Total number of students: " total_std
# Take the total number of passed students from the user
read -p "Total number of passed students: " passed_std

# Calculate the percentage of passed students
printf "The percentage of passed students: %.2f%%\n" "$((10**3 * 100 *
$passed_std/$total_std))e-3"
Run the following command to execute the script.
$ bash percentage.bash
Output:
The output shows the percentage of passing students based on the total number
of students and passed students.

Conclusion

The uses of different arithmetic operators in bash and the ways to perform the
arithmetic operations using different commands have shown in this tutorial by
using multiple examples to help the bash users.


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
