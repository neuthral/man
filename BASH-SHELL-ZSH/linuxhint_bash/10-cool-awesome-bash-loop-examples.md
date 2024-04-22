





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


10 Cool and Awesome Bash Loop Examples

1 week ago
by Prateek_Jangid
In the programming language, there are mainly three types of loops (for, while,
and until). All three types of loops are important in different ways. There is
not much difference between the while and until loops, but for loop works quite
differently from these two. That’s why you can use these loops to create
interactive scripts as a bash user.
So learning bash examples can help you improve your skills in creating scripts.
So in this tutorial, we will include 10 cool and awesome bash loop examples you
can try to enhance your scripting skills.

10 Cool and Awesome Bash Loop Examples

In this section, we will explain various examples and the approaches we have
used in the loops.

Seq Command With Loop in Bash

You can use the seq command in the for loop to create the sequence of numbers.
For example, you have a bash script “File.sh” that contains the following code:
#!/bin/bash
for A in $(seq 5 2 25)
do
  echo "numbers of $A are"
done
You will get the following result after executing the script in the terminal:
./File.sh
 

Rename Files Using Loop

Using a bash script, you can use the for loops to rename multiple files. For
example, you have multiple .txt files and want to add the current date with the
name. So here is the example script you can use:
#!/bin/bash
for A in $(ls *.txt); do
mv $A (basename $A .txt)_$(date %d%m%).txt
done
 
Now, you can run the script, and it will change the name of all .txt files by
adding the current date:
./MyFile.sh
 

Similarly, you can change the extensions of a file through a single script. So
let’s change the .txt extension into .sh through the following script:
#!/bin/bash
for file in *.txt; do
mv -- "$file" "{file%.txt}.sh"
done
 
After executing the script in the terminal, you will get the .sh rather than
.txt files:
./MyFile.sh
 

Infinite For Loop in Bash

When no termination condition is defined in the loop, it is called an infinite
loop. In this example of a Bash loop, we will look at the infinite for loop in
bash. The following infinite for loop is defined by a double semicolon ( ; ; )
and does not contain any initial, action, or termination parts.
The below script will continue until you press Ctrl+C or type “quit” as input.
This script will print every number from 10 to 50 that is given as input.
Otherwise, it will print “number is out of range.”
#!/bin/bash
#infinite loop
for (( ; ; ))
do
  echo "Enter a number between 10 to 50"
  read n
  if [ $n == "quit" ]
  then
    echo "terminated"
    exit 0
  fi
  if (( $n < 10 || $n > 50 ))
  then
    echo "The number is out of range"
  else
    echo "The number is $n"
  fi
done
 
We gave 45 and 23 valid inputs on the above script. After that, we print 2 as
input which tells in the output that “the number is out of range.” After that,
to close the script, we type quit as input. Here you can also press Ctrl+C to
quit the infinite loop.

Three Expression Loop in Bash

It is known from the name of the three-expression loop that it comprises three
expressions, also called control expressions. The first expression (EXP1) is
the initializer, the second expression (EXP2) is the loop test or condition,
and the third expression (EXP3) is the counting expression/step. Let us run a
three-expression loop in bash:
#!/bin/bash
for  (( n=5; n>=1; n-- ))
do
 echo "Book $n"
done
 
On running the above script, you will get the following output.

Loop With Multiple Conditions

We have used the until loop with multiple conditions in the following bash loop
example. In this script, we took “m” and “n,” two variables whose values ​​are
20 and 10, respectively, and kept the limit of 15. Here we put “m” and “n”
conditions together in the loop, in which the loop will run till the value of
“m” is less than the limit and “n” is more than the limit.
#!/bin/bash
limit=15
m=20
n=10
until [[ $m -lt $limit || $n -gt $limit ]];
do
echo "If M = $m then N = $n"
((m--))
((n++))
done
 
You can see that running the above script will run until the values ​​of “m”
and “n” come to the same level.

Read File in Bash

In bash, you can read the contents of a file in several ways. In this example
of bash loop, we will read the file’s contents through the filename. We can use
the following script to read the file in bash:
#!/bin/bash
echo "Content of the entered file is:"
while
read line
do
 echo $line
done <~Documents/Linuxhint.txt
 
After running the above script, you can read the full content of the entered
file.

Writing to a File

You can use the loops in the script to edit a file right from the terminal. For
example, if we have a txt file “Example.txt,” and we want to add up some
information, then we can use the following script:

If you run the above script, it will ask you to enter the details:

Once you enter the details, please CTRL + D to save the file and CTRL + Z to
finish the process successfully.

Break and Continue Statement Loop in Bash

In bash, you can continue your loop statement after the break. The break
statement exits the loop and then passes control to the next given statement.
Iteration number two begins after the current iteration is skipped with the
same continue statement.
#!/bin/bash
num=16
until false
do
 ((num--))
 if [[ $num -eq 13 ]]
 then
  continue
 elif [[ $num -le 4 ]]
 then
  break
 fi
 echo "LinuxHint = $num"
done
In the following bash script, you can see that when the “num” is equal to 13,
it skips the rest of the loop body and jumps to the next iteration. Similarly,
the loop will break when “num” is less than or equal to 4.

The above script shows that the loop starts at 15, breaks at 13, and continues
till 5.

Calculating an Average in Bash

You can calculate the average by running the script in a bash loop. In this,
the user can calculate the average of numbers within a defined range. The
following script calculates the average of provided input by the user.
#!/bin/bash
marks="0"
AVERAGE="0"
SUM="500"
NUM="5"
while true; do
 echo -n "Enter your marks or press 'q' to abort "; read marks;
 if (("$marks" < "0")) || (("$marks" > "100")); then
  echo "Please enter your marks"
 elif [ "$marks" == "q" ]; then
  echo "average marks are: $AVERAGE%"
  break
 else
  SUM=$[$SUM + $marks]
  NUM=$[$NUM + 1]
  AVERAGE=$[$SUM / $NUM]
 fi
done
 
If the input is not within the range, a message is printed that “Please enter
your marks.” When the user presses “q” after entering all the marks, the script
calculates the approximate average of all the numbers entered.
When the above script is run, your output will be something like this.

Read the Command-Line Arguments in Bash

In bash, you can read single command-line arguments using loops. The script
prints the formatted argument values. We run command line arguments in bash
using a while loop in the following script. Through this, you will print the
value passing the argument value valid option with the help of a single
command.
#!/bin/bash
while getopts N:F:M: OPT
do
 case "${OPT}"
 in
  N) name=${OPTARG};;
  F) fathername=${OPTARG};;
  M) mothername=${OPTARG};;
  *) echo "Invalid"
    exit 1;;
   esac
done
printf "Name:$name\nFather Name:$fathername\nMother Name:$mothername\n"
 
Thus, you can print the formatted argument values ​​to the output by running
the above script in a bash.

Wrapping Up

So this was the brief information on the 10 cool and awesome bash loop examples
you can learn. We have used different types of loops to create the interactive
script easily. Moreover, we also explained the basic approaches used in the
above examples. If you have in-depth details about the loops in bash, please
visit our official website to know more.


About the author


Prateek Jangid

A passionate Linux user for personal and professional reasons, always exploring
what is new in the world of Linux and sharing with my readers.
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
