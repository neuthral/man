





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash eval command

3 years ago
by Fahmida_Yesmin
`eval` command is used in bash to execute arguments like a shell command.
Arguments are joined in a string and taken as input for the shell command to
execute the command. `eval` executes the command in the current shell. This
command is useful when it requires to execute any command that contains a
special operator or reserved keywords. This command can be used in any script
also where the variable name is unknown until executing the script. This
tutorial will help Linux users to learn the use of this command.

Syntax:

eval [argument ...]
Here, arguments are parsed and combined into a string that will execute by the
shell. `eval` returns an exit status code after executing the command. `eval`
returns 0 as exit status code if no argument is provided or only null argument
is provided.

Example-1: Execute `wc` command using `eval`

Suppose a text file named “department.txt” contains the following text. The
total number of lines of the file can be counted by `wc` command.
department.txt
CSE
EEE
ETE
ENGLISH
BBA
PHARMACY
The following command will store `wc` command to count the total number lines
of the file, department.txtto the variable, $mycommand.
$ mycommand="wc -l department.txt"
The following `eval` command will run `wc` command and print the total number
of lines.
$ eval $mycommand
Output:
The output shows that department.txt file has 6 lines.

Examplel-2: Execute `expr` command using `eval`

Create a bash file named evaltest.sh and add the following script. This script
will assign two integer values into the variable $x and $y. The `expr` and
`echo` commands are assigned into two variables, $c1 and $c2 which are executed
later by using `eval` command.
evaltest.sh
#!/bin/bash
#Initialize the variable x and y
x=5
y=15

#The first command variable is used to assign `expr` command to add the values
of $x and $y
c1="`expr $x + $y`"

#The second command variable is used to assign `echo` command
c2="echo"

#`eval` will calculate and print the sum of $x and $y by executing the commands
of $c1
and $c2 variables
eval $c2 $c1
Run the script.
$ bash evaltest.sh
The sum of 5 and 15 is 20 that is shown in the output.

Example-3: Print the value of a variable that is assigned in another variable

Create a bash script named evaltest2.sh with the following script. Here, one
variable is used to assign the name of another variable that contains a string
data. `eval` command will print the value of the variable that contains another
variable’s name as content.
evaltest2.sh
#!/bin/bash

# Assign a string value into the variable, $str1
str1="Shell Script"

# Assign the variable name, “str1” to the variable $str2
str2=str1
#Store the command into the variable, $command
command="echo"

# `eval` command will execute the `echo` command and print the value of the
variable
that contains in another variable
eval $command \${$str2}
Run the script.
$ bash evaltest2.sh
The value of the variable, $str1 is printed.
There is another way to access the value of a variable which name is the value
of another variable. Using ‘!’ symbol the value of this type of variable can be
accessed. The following command can be used as an alternative of the previous
script and the output will be the same.
$ str1="Shell Script"; str2=str1; command="echo"; eval $command ${!str2}

Example-4: Create a series of variables with values and calculate the sum of
the values using `eval` command

Create a bash script named evaltest3.sh and add the following script. This
script will create a series of variables and store the values into the
variables using `eval` command. The values of the variables will be added and
stored into a variable named $sum. Next, `echo` command with string values is
assigned into a variable that is used in the `eval` command to print the value
of the $sum variable.
evaltest3.sh
#!/bin/bash

# Initialize the variable $sum with the value 0
sum=0

# Declare a for loop that will iterate for 4 times
for n in {1..4}
do
# Create four variables using eval command
eval x$n=$n

# Add the values of the variable with $sum
sum=$(($sum+$x$n))
done

# Assign `echo` command with string into a variable
command="echo 'The result of the sum='"

# `eval` command print the sum value using variables
eval $command $sum
Run the script.
$ bash evaltest3.sh
The sum of the four variables is, 1+2+3+4=10 that is printed.

Example-5: Using `eval` command to remove the list of files

Create a bash file named evaltest4.sh with the following script. This script
will read three command-line arguments as filenames that will be removed and
store the argument values into an array variable, $fn. `rm’ command is stored
in a variable, $command. For loop is declared here to retrieve each filename
and remove the file using `eval` command if the file exists.
evaltest4.sh
#!/bin/bash

#Declare an array
declare -A fn

# Read three command line arguments and store into three index of the array
fn[0]=$1
fn[1]=$2
fn[2]=$3

# Store the remove command into a variable
command="rm"

# for loop will iterate for three times to read three array element
for index in 0 1 2
do
# Check the file exists or not exist
if [[ -f ${fn[$index]} ]]; then
# if the file exists then remove the file
eval $command ${fn[$index]}
# Inform the user that the file is removed
echo "${fn[$index]} is deleted."
Else
#Inform the user that the file is not exist
echo "${fn[$index]} not exist."
fi
done
Run the script.
$ bash evaltest4.sh marks.docx item.txt product.docx
Here, three file names are provided at the time of executing the script. The
output shows that marks.docx and product.docx exist in the current location and
the files are removed and, item.txt does not exist in the current location.

Conclusion

Any bash command can be executed by `eval` command by declaring as a string.
`eval` command is used in this tutorial for executing different built-in
commands of bash and creating a series of variables. The uses of `eval` command
will be cleared for the users and they will be able to use this command for
various purposes after reading this tutorial.


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
