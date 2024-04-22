





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Generate a random number in bash

1 year ago
by Fahmida_Yesmin
The number that is changed in each script execution is called a random number,
and it is unpredictable. The random numbers are used in the programming for
various purposes, such as testing data, generating lottery tickets, generating
a password, etc. The integer number or floating number can be used to generate
a random number in bash. The random number of a specific range or a size can be
generated using a bash script. Different ways to generate random numbers in
bash have been shown in this tutorial.

Use of random generator:

The random number or a range of random numbers can be generated using the
$RANDOM variable. It generates a random number between 0 and 32767 by default.
But you can set the range of numbers for generating random numbers by dividing
the value of $RANDOM with a specific value. Different uses of the $RANDOM
variable to generate random numbers are shown in the tutorial’s next part.

Random number generation using $RANDOM variable:

The ways to generate the random number in the terminal and execute a script
file are shown here.
A. Generate Random numbers from the terminal
Run the following command to generate a random number within the range 0 to
32767.
$ echo $RANDOM
You can generate a random number of a specific range by dividing the $RANDOM
variable with a particular value and getting the remainder value. Run the
following command to generate a random number within the range of 1 to 50.
Here, double first brackets with $ have been used.
$ echo $(( $RANDOM % 50 + 1 ))
Run the following command to generate a random number within the range of 10 to
40. Here, the third bracket with $ has been used.
$ echo $[ $RANDOM % 40 + 10 ]
B. Generate Random numbers using the script
Create a bash file with the following script to generate a random number of the
specific range where the minimum and maximum range values will be taken from
the user. An error message will be displayed if the taken maximum value is
smaller than the minimum value. If the difference between the maximum and the
minimum value is 1, another error message will be displayed. A random number
will be generated in each execution of this script if the valid minimum and
maximum values will be taken as input.
#!/bin/bash
# Generate a randomly based range defined by the user

#Take the lower and the upper value from the user
echo "Enter the minimum value:"
read minimum
echo "Enter the maximum value:"
read maximum

#Check the taken values are valid
if [[ $maximum < $minimum ]]; then
    echo "Maximum value can't be lower than minimum value"
    exit 1
fi

#Find out the difference between the numbers
diff=$(($maximum-$minimum))

#Check the difference value
if [[ $diff == 1 ]]; then
    echo "The range of numbers must be more than 1"
    exit 1
fi

#Generate the random number
randomNumber=$(($minimum + $RANDOM % $maximum))
#Print the generated number
echo "The generated random number is: $randomNumber"
The following output will appear if the script is executed multiple times.
Here, the above script has been executed three times. The error message has
been printed for the first two executions for invalid input, and a random
number has been generated for the last execution.

Random number generation using `shuf` command:

Using the `shuf` command is another way to generate the random number of a
specific range. The ways to generate a random number from the terminal and use
a script have been shown in this tutorial.
A. Generate Random numbers from the terminal
Run the following command to generate a random number between 0 to 50 using the
`shuf` command.
$ shuf -i 0-50 -n1
According to the following output, the above command has been executed three
times, and three random numbers have been generated.
B. Generate Random numbers using the script
Create a bash file with the following script to generate a list of random
numbers based on the input value. The `for` loop has been used to execute the
`shuf` command multiple times to generate the list of random numbers between 1
to 100 and print the numbers.
#!/bin/bash
# Generate a random using `shuf` command
echo "How many random numbers do you want to generate?:"
read number

#Print the generated random numbers
echo "The generated random numbers are:"
for n in `seq "$number"`
do
randomNumber=$(shuf -i 1-100 -n1)
echo $randomNumber
done
The following output shows that 5 has been taken as the input value, and 5
random numbers have been generated, which are not more than 100 and not less
than 1.

Random number generation using /dev/urandom:

The /dev/urandom can be used with different commands to generate different
types of random values. It can’t be used to specify the range values like the
`shuf` command and $RANDOM variable. But the number of the digits of the random
number can be defined in command with /dev/urandom. The use of the `od` command
with /dev/urandom has shown in the next part of this tutorial. This command can
be used to specify the number of bytes where each byte can be defined by a
decimal number within 0 to 255.
Run the following command to generate a random number between 0 and 255.
$ od -A n -t d -N 1 /dev/urandom
The output shows that the above command has been executed three times, and
three different random numbers have been generated here where the values are
not more than 255.

Conclusion:

Three different ways to generate random numbers have been explained in this
tutorial by using various examples. The coder can generate a specific range of
random numbers by using the $RANDOM variable or `shuf` command in bash. The
coder can use /dev/urandom with any other command to generate a random number
of particular bytes or lengths. Generating random numbers is a very common
requirement for programming, and I hope the readers will be able to generate a
random number based on their requirements after reading this tutorial.


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
