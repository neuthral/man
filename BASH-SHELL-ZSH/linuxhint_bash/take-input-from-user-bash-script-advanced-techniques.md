





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Take Input From a User in Bash Script [Advanced Techniques]

1 week ago
by Prateek_Jangid
You can create interactive scripts by taking input from the user during
execution. It also helps you to manipulate the output as per the requirements.
There are some easy methods to take input from the user. That’s why it is best
to use more advanced ways as an intermediate or expert. However, many bash
users need to learn advanced techniques to take input from the users in a bash
script. So in this tutorial, we will explain them all briefly.

How to Take Input From a User in Bash Script [Advanced Techniques]

With the read command, you can take input, but do you know that you can take
multiple inputs? Let’s take an example to get in-depth information. Suppose we
want to create a script to perform an arithmetic calculation using multiple (A,
B, C, D, E) numbers:
#!/bin/bash

echo "Please enter three numbers"

read A B C D E

sum=$((A+B+C+D+E))

echo "Addition is $sum"

multiply=$((A*B*C*D*E))

echo "Multiplication is $multiply"
Now, we can execute the script and enter the numbers to calculate the addition
and multiplication:
If you don’t want to create a separate echo statement, then you can add it in
the read command using the -p option:
#!/bin/bash

read -p "Please Enter Your Name and Age:" name age

if [ $age -lt 17 ]

then

echo "Sorry!! You are not eligible for the course"

else

echo "Great!! You are eligible for the course"

fi
The above script requires a user to be at least 17 years old to get eligibility
for the particular course:

Take Input Using Stdin (Standard Input)

If you want to go one step further in the advanced techniques, then you can use
the stdin concept. You can use the stdin in the script to get easy solutions.
Let’s take an example where we want to filter out the list of eligible
candidates that have already submitted the fees. We have a list that contains
details like candidate name, age, date of form submission, and fee submission
status. So we can use the below-given script to get the desired details:
#!/bin/bash

echo "details about the fees submission:"

cat /dev/stdin | cut -d' ' -f 1,4 | sort
This script provides the following result:

Wrapping Up

So this was all about the advanced techniques you can try to take input from
the user in a bash script. In this tutorial, we have explained different
options in the read command and the stdin to enter the input quickly. If you
are new to bash and want to know how to take input, please check out our
website to know more.


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
