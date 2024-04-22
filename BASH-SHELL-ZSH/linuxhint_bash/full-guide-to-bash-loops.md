





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Full Guide to Bash Loops

1 year ago
by Sam_U
The most basic way to interact with the Linux system is the command-line
interface (CLI). The command-line interface is a front-end window to take
commands by the user to perform a specific task. A task can be creating a
directory, file, inserting data, removing a file or directory, etc. The shell
processes the commands entered by the user in the CLI. Linux has different
shells, such as Bourne Shell, C Shell, Z Shell, Korn Shell, and Bourne Again
Shell, which is also known as Bash. All of the mentioned shells have their own
capabilities, but one of the most widely used shells is Bash.
Bash shell comes out of the box with many Linux distributions and contains
features of many other shells, as well. Bash is much more efficient when it
comes to performing an operation via command. If you want to perform a task
that requires the execution of multiple commands with some logic, then there is
an entire programming language called Bash Scripting.
1._What_Is_Bash_Scripting?
2._What_Are_Bash_Loops?
3._Applications_of_Loops_in_Programming
4._Advantages_of_Loops_in_Programming
5._Types_of_Loops_in_Bash

* 5.1_Bash for loop_Syntax
* 5.2_Bash while loop_Syntax
* 5.3_Bash until loop_Syntax

6._Using_Loops_in_Bash
6.1_Implementation_of for loop_in_Bash

* 6.1.1_Bash for loop_Iterating_Through_a_List_of_Strings
* 6.1.2_Bash_for_loop_Iterating_Through_a_List_of_Numbers
* 6.1.3_Bash_for_loop_Iterating_Through_a_Range_of_Items
* 6.1.4_Bash_for_loop_Iterating_Through_an_Array
* 6.1.5_Bash_for_loop_in_C_Like_Syntax
* 6.1.6_Bash_for_loop_Infinite_Loop
* 6.1.7_Bash_Nested_for_loop

6.2_Implementation_of_while_loop_in_Bash

* 6.2.1_Bash_while_loop_to_Print_Numbers
* 6.2.2_Bash_infinite_while_loop
* 6.2.3_Bash_while_loop_With_Multiple_Conditions

6.3_Implementation_of_until_loop_in_Bash

* 6.3.1_Bash_until_loop_to_Print_Numbers
* 6.3.2_Bash_infinite_until_loop

7._Loop_Control_Statements

* 7.1_The_break_Statement
* 7.2_The_continue_Statement

8._Examples_of_Bash_Loops

* 8.1_Example_1:_Changing_the_Extension_of_the_Files_Using_Bash_Loops
* 8.2_Example_2:_Modifying_the_File_Names_Using_Bash_Loops
* 8.3_Example_3:_Reading_a_File_Using_Bash_Loops
* 8.4_Example_4:_Finding_a_File_Using_Bash_Loops
* 8.5_Example_5:_Creating_a_Simple_Counter_Using_Bash_Loops
* 8.6_Example_6:_Checking_Internet_Connection_Using_Bash_Loops
* 8.7_Example_7:_A_Simple_Calculator_With_Bash_Loops
* 8.8_Example_8:_Finding_Average_Using_Bash_Loops

9._Conclusion

1 What Is Bash Scripting?

A script is something that tells the system what specific operation it should
perform. Similarly, Bash scripts command Bash shell that what it should do. A
simple text file carrying the strings of Bash commands is called a Bash script
file. Bash script executes commands in a similar way the shell executes, but
you can apply logical operations to perform a specific function. The
programming language used in Bash is called Bash programming language.
Bash programming language is similar to  any other programming language where
you can assign variables, apply conditional statements, loops and arrays. You
can perform any task from basic level to complex programs with hundreds of
instructions in Bash scripting. To understand Bash scripting, let’s create a
simple HelloWorld script:
#! /bin/bash

echo "Welcome to Bash Scripting"
In the above script, “#!” is known as “shebang” or “hashbang,” and “/bin/
bash” is the path to the interpreter. The “echo” command displays the output on
screen; the above script is printing a string. Bash script can be written in
any editor; Linux comes with default editors such as nano, vim, etc. After
typing the script save the file with the “.sh” extension,
e.g., “helloworld.sh”. To execute a Bash script in CLI, use the “bash” command:
$bash helloworld.sh
The above command executes the Bash script and prints the string as shown in
the output image. Likewise, you can perform any logical operation using
conditional statements or execute instructions repeatedly; loops can be
implemented. This write-up is about Bash loops. Loops are used to run some
particular lines of code repeatedly. The following segment will thoroughly
cover the Bash loops:

2 What Are Bash Loops?

Loops are one of the fundamental programming structures utilized in executing a
sequence of instructions repeatedly until a specific condition is met.
Programmers use loops in various ways, such as iterating through the values of
an array, repeating functions, adding numbers, and creating counters.
Loop checks a set of instructions in the loop body until the loop condition is
satisfied, as demonstrated in the above image.

3 Applications of Loops in Programming:

Loops can be used for many purposes in programming, the primary usage of loops
is mentioned below:

* In algorithms to search for specific information
* In gaming to create game loops
* Creating counters that can be helpful for automation
* To repeat specific functions
* Solving complex mathematical problems

Loops are also useful to iterate through the arrays as well.

4 Advantages of Loops in Programming:

Loops in programming have various advantages:

* Loops can perform a task repeatedly without making any mistakes (assuming the
  instructions are correct)
* Loops allow to perform any number of instructions repeatedly
* Loops simplify the complex codes and make them efficient
* They prevent writing the same code again and again
* Loops can also be used in the data structure to iterate through the arrays


5 Types of Loops in Bash:

In Bash, there are three primary loop types:

  1. : for loop
  2. : while loop
  3. : until loop


5.1 Bash for loop Syntax:

The basic Bash for loop iterates through the elements list and executes the
mentioned instruction or commands in the loop body.
The syntax of bash for loop is:
for element in [list]

do

        [commands]

done
The list can be an array, sequence of numbers or strings, or output of a
command. The basic bash for loop can also be assigned using C language
structure:
for ((initialization; condition; increment))

do

        [commands]

done
The “initialization” runs only once, then “condition” is checked. If it is
true, the commands in the body will execute and keep on executing until the
condition evaluates as false.

5.2 Bash while loop Syntax:

The Bash while loop executes the set of statements or specific commands an
unknown number of times until the specified condition marked as false:
while [condition]

do

        [commands]

done
The condition is evaluated before the execution of the command. If the
condition is true, the command will execute; if the condition turns false, the
loop will be terminated.

5.3 Bash until loop Syntax:

The Bash until loop executes the set of statements or commands an infinite
number of times until the specified condition is marked as true:
until [condition]

do

        [commands]

done
Similar to the while loop, the condition is checked before the execution of the
command; if the condition is false, the set of statements will execute. If the
condition turns true, the loop will terminate.

6. Using Loops in Bash:

As mentioned above, Bash has three main types of loops, and the usage of each
type depends upon the task a user wants to perform. Let’s dive into the detail
of how various types of loops are assigned and manipulated in Bash.

6.1 Implementation of for loop in Bash:

The following section is focusing on how to implement Bash for loops in Bash
scripting. In Bash for loop is used to go over a list of objects,

6.1.1 Bash for loop Iterating Through a List of Strings:

The basic Bash for loop goes over a list of elements, array, or can be used to
execute a set of instructions in the loop body repeatedly. The following
example is an implementation of for loop that is going over a list of string
elements:
#! /bin/bash

for items in saturday sunday monday tuesday wednesday

do

        echo "The item in the list is:" $items

done

6.1.2 Bash for loop Iterating Through a List of Numbers:

To iterate through the list of numbers:
#! /bin/bash

for items in 1 2 3 4 5

do

        echo "The item in the list is:" $items

done

6.1.3 Bash for loop Iterating Through a Range of Items:

In Bash, sequence expression is used to print a sequence of numbers. Sequence
expression also supports range. The for loop can also be applied to go over the
sequence expression range. For example:
#! /bin/bash

for items in {1..5}

do

        echo "The item in the list is:" $items

done
The expression “{1..5}” is a representation of numbers from 1 to 5. The
sequence can also be defined with a specific increment, the expression to
follow would be “{Start…End…Increment}”:
#! /bin/bash

for items in {1..10..2}

do

        echo "The item in the list is:" $items

done

6.1.4 Bash for loop iterating Through an Array:

Loops are commonly used in iterating through an array. Let’s understand it
through an example:
#! /bin/bash

my_array=(jan feb mar apr may jun)

for items in ${my_array[@]}

do

        echo "Items in the array:" $items

done

6.1.5 Bash for loop in C Like Syntax:

As mentioned above, the Bash also supports for loop in the C language style.
The following example demonstrates how to use C-style for loop used in Bash:
#! /bin/bash

for((items=1 ; items<=10 ; i++))

do

        echo "Number:" $items

done
The C-style loop structure is widely used, easy to remember and implement.
Because many modern programming languages support similar loop syntax, the
above loop structure will print numbers from 1 to 10.

6.1.6 Bash for loop Infinite Loop:

The infinite loop has various uses in programming. The following example is
showing the implementation of infinite loop using bash for loop:
#! /bin/bash

count=0

for (( ; ; ))

do

        sleep 2

        echo $count

        echo "Press CTRL+C to stop the execution of the code"

        ((count++))

done

6.1.7 Bash Nested for loop:

Nested loops mean the loop structure within another looping structure; the
first loop will be called the outer loop, while the loop inside the outer loop
will be called the inner loop. Each outer loop iteration will run all the inner
loop iterations. The for loop in Bash can also be implemented in the nested
format:
#! /bin/bash

for items1 in jan feb mar

do

        for items2 in apr may jun

      do

        echo "$items1 : $items2"

      done

done

6.2 Implementation of while loop in Bash:

The key difference between Bash for loop and while loop is that while loop is
used when the number of integrations is unknown. Let’s learn how while loop is
assigned and implemented in Bash scripting:

6.2.1 Bash while loop to Print Numbers:

The following example will display numbers from 1 to 10:
#! /bin/bash

x=0

while [ $x -le 10 ]

do

        echo "The numbers is:" $x

        ((x++))

done

6.2.2 Bash Infinite while Loop:

The infinite loop continuously executes and never terminates. Infinite loop is
used to check the inputs from the users and respond accordingly. The most
common example is the game loop, where a player controls a character and the
loops prints response of every move:
#! /bin/bash

count=0

while :

do

        sleep 2        

        echo "Counter= " $count

        echo "Press CTRL+C to stop the execution of the code"

        ((count++))

done
The above code will print counter value and “Hello ! Press CTRL+C to exit the
infinite loop” after 1 second and repeatedly print it every second. The “sleep”
command adds delay to the execution of the program. The colon “:” after “while”
is the null command. The other way to assign infinite while loop:
#! /bin/bash

count=0

while true

do

        sleep 2        

        echo "Counter="$count

        echo "Press CTRL+C to stop the execution of the code"

        ((count++))

done

6.2.3 Bash while loop With Multiple Conditions:

The following example is demonstrating how multiple conditions are used with
Bash while loop:
﻿#! /bin/bash

num1=1

num2=5

while [[ $num1 -lt $num2 || $num1 == $num2 ]]

do

        echo "The number is:"$num1

        ((num1++))

done    

echo "Done !"
It can be seen that while loop is evaluating two conditions with OR operator
“||”. OR operator is a Boolean operator that outputs true if any of the
conditions is true.

6.3 Implementation of until loop in Bash:

The until loop is similar to the while loop, but it loops till the specified
condition evaluates as true. Let’s understand how to implement until loop in
Bash:

6.3.1 Bash until loop to Printing Numbers:

The following example of until loop is printing numbers in the output from 0 to
10:
#! /bin/bash

x=0

until [ $x -gt 10 ]

do

        echo "The numbers is:" $x

        ((x++))

done

6.3.2 Bash Infinite until loop in Bash:

The infinite loop using until loop operator is mentioned below:
#! /bin/bash

x=0

until false

do

        echo "Counter:" $x

        ((x++))

sleep 1

echo "Press CTRL+C to end the loop"

done

7. Loop Control Statements:

The loops are designed to loop continuously until a specific condition is met,
but there are statements through which loop flow can be controlled.

* The break statement
* The continue statement


7.1 The break Statement:

The break keyword ends the loop, no matter what kind of loop construct is used,
and runs the instruction of the code outside the loop body:
Let’s understand the break statement through a Bash example:
#! /bin/bash

for items in jan feb mar apr may jun jul

do

if [[ "$item" == "may" ]]

then

break

fi

        echo "Items are:" $items

done

        echo "Loop Terminated"
Similarly, break statement can also be used in a while loop:
#! /bin/bash

x=0

while [ $x -lt 10 ]

do

        echo "The number is:" $x

        ((x++))

        if [[ "$x" == "7" ]]

then

        break

        fi

done

echo "Loop Terminated"
The example of an until-break statement is mentioned below:
﻿#! /bin/bash

x=0

until false

do

        ((x++))

        if [[ $x -eq 5 ]]

then

        break

        fi

        echo "Values are:" $x

done

        echo "Loop Terminated"
When the value of increment (“x”) equals 5, the break statement will terminate
the loop, and the statements outside the loop body will execute.

7.2 The continue Statement:

The continue statement ends the loop’s current operation, returns to the
original loop condition, and executes the next iteration.
Let’s understand the continue control statement through an example:
#! /bin/bash

for items in jan feb mar apr may jun jul

do

if [[ “$item” == “may” ]]

then

continue

fi

        echo “Item in the list:” $items

done
The for loop will iterate through the list of months and stops when the value
becomes “may“. A new iteration will start, and the instructions under the
continue statement will not execute. It can be seen in the output image as well
that the “may” is missing from the list because the continue statement skipped
the execution of “echo” when the “items” variable becomes equal to the “may”
string.
Like for loop the “continue” statement can also be implemented in a while loop:
#! /bin/bash

x=0

while[ $x -lt 10 ]

do

        ((x++))

        if[[ "$x" -lt "5" ]]

then

        continue

        fi

echo “The number is:” $x

done
The above code will print numbers from 1 to 10 and skip 5, as demonstrated in
the output image. An example of implementation of “continue” statement
with until loop is mentioned below:
﻿#! /bin/bash

x=0

until [ $x == 10 ]

do

        ((x++))

        if [[ $x -eq 5 ]]

then    

        continue

        fi

        echo “Number is:” $x

done

8. Examples of Bash Loops:

Loop structures have various implementations in Bash. This section will focus
on more advanced Bash examples where loops are implemented.

8.1 Example 1: Changing the Extension of the Files Using Bash Loops:

The following example is taking file extension from the user; the script will
collect all the files of the extension given by the user and save them in a
file “file_list”. The for loop is going over the list of the files. Whereas
the “cp” command will create the copy of the file with the “.bak” extension in
the current directory.
﻿#! /bin/bash

echo "Enter the file extension"

read ext

echo "Enter the conversion extension"

read cov

ls *.$ext>files

for i in `cat files`

do

        cp "$i" "$i".$cov

done
Let’s enhance the above code:
﻿#! /bin/bash

echo "Enter the directory name"

read dir

echo "Enter the file name extension to be converted"

read f_ext

echo "Enter the file extension to be converted"

read cov

for file in $dir/*$f_ext

do

        mv -- "$file" "${file%$f_ext}$cov"

done
Now, the code is taking the directory name that contains the file, file name
extensions to be converted, and the extension name to convert the files in the
directory. A user can get any file and convert those files into the desired
extension.

8.2 Example 2: Modifying the File Names Using Bash Loops:

The space in the files or directory can create issues while running commands
that contain paths. The command-line interface does not recognize space in
files or folders name, as demonstrated in the following image:
You either have to use quotes or escape sequences. But luckily, we can create a
Bash script that can add underscore “_” or dash “-” to fill the space of the
file names and directories.
﻿#! /bin/bash

echo "Enter the folder name"

read folder

cd $folder

for files in *\ *

do

        mv "$files" "${files// /_}"

done
The above code is taking the folder name as input which is “my_folder”, and it
contains the files with space in their names as demonstrated in the above
output image. The script will replace space by underscore “_” in the file names
present in the directory mentioned by the user.

8.3 Example 3: Reading a File Using Bash Loops:

A file can also be read using the loop structure:
﻿#! /bin/bash

echo "Enter the file name"

read file

while true

        read -r l

do

        echo $l

done < "$file"
The above code is taking the text file name as an input from the user and
printing its content.

8.4 Example 4: Finding a File Using Bash Loops:

The following example finds the files by the extension user gives:
﻿#! /bin/bash

echo "Enter the file name extension"

read ext

IFS=$'\n'

for file in $(find -name "*$ext")

do      

        echo $file

done    

unset IFS
The IFS is a special shell variable, an internal field separator used to find
word boundaries. A user can mention any file type extension such as “.txt”,
“.sh”, or “.png”, the code will find all the files of that extension and
display them in the terminal.

8.5 Example 5: Creating a Simple Counter Using Bash Loops:

This example will count down from a number entered by the user:
﻿﻿#! /bin/bash

echo "Enter a number"

read counter

while [ $counter -gt 0 ]

do

        sleep 1

        echo $counter

        ((counter--))

done    

echo "done"
The above code is getting a number from the user, and the counter goes down by
one every second.

8.6 Example 6: Checking Internet Connection Using Bash Loops:

The loop structure can also be used to check the internet connection using the
“ping” command:
﻿#! /bin/bash

counter=5

while [[ $counter -ne 0 ]]

do

        ping -c 2 www.google.com

        check=$?

        if [[ $check -eq 0 ]]

        then

                echo "___________________"

                echo "Internet is working"

                echo "___________________"

                exit 0

        fi

        ((counter--))

done

echo "________________"

echo "Internet is down"

echo "________________"
The above code will ping to check the status of the Google website. The “-c”
flag is used for counting. The value of option “-c” is 2, which means the
“ping” will send the requests twice. If the exit code “$?” is 0, the ping
command is getting acknowledgment, and the internet is working. The ping will
check the status five times. If it does not get any acknowledgment, the
“Internet is down” error will be displayed.

8.7 Example 7: A Simple Calculator With Bash Loops:

The following example is taking two numbers from the user and asking for the
operation to perform. The following Bash script is performing addition,
subtraction, multiplication, and division:
﻿﻿#! /bin/bash

echo "Enter number 1"

read num1

echo "Enter number 2"

read num2


while true

do

        echo "Select the operation number"

        echo "1 Sum + : 2 Difference - : 3 Multiplication * :  4 Division \ : 5
Quit"

        read operator

if [[ "$operator" -eq "1" ]]

then

        ((output=num1+num2))

elif [[ "$operator" -eq "2" ]]

then

        ((output=num1-num2))

elif [[ "$operator" -eq "3" ]]

then

        ((output=num1*num2))

elif [[ "$operator" -eq "4" ]]

then

        ((output=num1/num2))

elif [[ "operator" -eq "5" ]]

then

        exit 0

fi

echo "The result is" $output

done
The calculator will keep on performing functions until the user gives the
command to end the infinite while loop.

8.8 Example 8: Finding Average Using Bash Loops:

The following example will take numbers as input from the user and calculates
the average:
﻿#!/bin/bash

while true; do

  echo -n "Enter a number from 0 to 100 and press a/A to get the average: "

  read e_num


  if (("$e_num"  "100"))

  then

    echo " !Invalid Entry! Enter number from 0 to 100"

elif  (("$e_num" == "a")) || (("$e_num" == "A"))

  then

    echo "Average is: $avg%"

    break

  else

    sum=$[$sum + $e_num]

    num=$[$num + 1]

    avg=$[$sum / $num]

  fi

done
The above code is getting numbers from the user from 0 to 100. If the entered
number is not 0 or greater than 100, the user will get an error message upon
entering the desired number. Press a/A to get the average in the output.

9. Conclusion:

The loop constructs are the key constructs of programming and are quite handy
for programmers especially in automating repetitive operations. Loops are used
to execute instructions repeatedly till the loop evaluates a particular test
statement. Loops have various uses in programming, such as creating algorithms,
automating, creating game loops, etc. Bash offers three types of loop
structures: for loop, while loop, and until loop. The controlled approach can
also classify loops; while loops and until loops are controlled loops because
the test condition is checked before the in-loop instructions are executed. The
Bash for loop can be initialized in two distinct ways, in typical Bash format
and C language syntax style. Basic for loop is simply used to iterate through
the list of the elements or arrays. In the for loop implementation, we already
know the iteration count, whereas while loops are used when the number of
iterations is unknown. The while loop continues to loop as long as the defined
check statement is true. It is important to note that if no condition is
specified, then the loop will be termed as an infinite loop. The infinite loop
keeps on executing the in-loop instructions as long as it is not interrupted.
Next comes the loop-controlled statements, the break, and
the continue statement. The break statement is used to terminate the loop and
runs the statements outside the loop body. However, the continue statement
functions in the opposite manner of the break statement. Instead of ending the
loop, the continue statement forces the loop for the new iteration and skips
the remaining instructions of the loop body.
All the Bash loop structures can also be used in a nested way. Nested loops
mean loops inside other loops, and they are extremely useful in iterating
through two different arrays. The final section of the write-up covers some
basic and advanced examples of the implementation of Bash loops, though there
are tons of ways to use Bash loops in Bash scripting.
Loops are a compelling programming structure and hold various benefits; they
simplify the complex codes and make them more efficient. If you want to execute
specific commands, you don’t need to type them; loops are designed to perform
such tasks.


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
