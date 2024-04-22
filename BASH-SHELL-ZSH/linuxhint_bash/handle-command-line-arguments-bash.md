





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Handle Command Line Arguments in Bash?

1 week ago
by Prateek_Jangid
In Linux, we use command-line arguments as input for the bash script. Bash can
take these command-line arguments sequentially and parse them as an option.
These arguments allow you to affect the actions and the script’s output
dynamically.
You can configure these arguments differently to influence the input and
output. That’s why handling command-line args in bash is essential, but many
new users need to learn how to do it. So in this guide, we will explain
different ways to handle command-line arguments in bash.

How to Handle Command Line Arguments in Bash?

There are various ways to handle command line args in Bash so let’s take a look
at them to get brief information:
The getopt Function
The getopt function is handy as it provides the options and syntax for defining
and parsing arguments in bash. It is a built-in function of Linux that you can
use while creating a database file or report in a specific format based on the
arguments. The getopt function helps parse the short command-line arguments
because there are two types of arguments:

* Short Arguments: These are the single-character arguments followed by a
  hyphen. For example, -a, -l, -h, etc., are a few examples of single
  arguments.

 

* Long Arguments: These are the multi-character arguments followed by a double-
  hyphen. There are various examples of long arguments, such as –all, –list,
  –help, etc.

Let’s take an example where we will handle the command line arguments using the
getopt utility. We have created a bash script named “getopt.sh” that contains
the following information:
!/bin/bash

while getopts 'A:B:C:D:' details; do

case "$details" in

A)

echo "Citizen Name is $OPTARG" ;;

B)

echo "Citizen ID is $OPTARG";;

C)

echo "Birth Place is $OPTARG";;

D)

echo "Occupation is $OPTARG";;

*)

exit 1;;

esac

done

shift "$(($OPTIND -1))"

 

if [ ! -z $1 ]; then

echo "Marital Status $1"

else

echo "No Entries"

exit 1

fi

 

if [ ! -z $2 ]; then

echo "Family Members $2"

fi
Now let’s execute the script with the required arguments in the input:
As you can see in the above image, we run the script with getopt functions only
and then add normal arguments to get the complete result.

Using Flags

Flags are nothing but single characters preceded by hyphens(-). When we pass
the arguments using the getopt function, we use flags. -a, -b, -c are some
examples of flags. For example,  a script requires a citizen’s name, ID, place,
age, and occupation. Hence, we used flags j, k, l, m, n, to define citizen’s
name, ID, place, age, and occupation simultaneously:
#!/bin/bash

While getopts j:k:l:m:n: flag_info

do

case "${flag_info}" in
<ol>
    <li>j) citizenname=${OPTARG};;</li>
    <li>k) citizenid=${OPTARG};;</li>
    <li>l) place=${OPTARG};;</li>
    <li>m) age=${OPTARG};;</li>
    <li>n) occupation=${OPTARG};;</li>
</ol>
esac

done

echo "Here are the entered details:"

echo "Citizen Name: $citizenname";

echo "Citizen ID: $citizenid";

echo "Place: $place";

echo "Age: $age";

echo "Occupation: $occupation";
The script will give the following result in the terminal:
./<script>.sh -j Danny -k 476 -l Toronto -m 25 -n Author

Using [email protected] With Loops

The “[email protected]” variable is nothing but the array of all input
arguments. We can pass any number of inputs using the “[email protected]”
variable. You can use this variable as a loop to iterate through the arguments.
The “[email protected]” variable comes in handy then; you don’t know the input
size and can’t take the positional arguments. Hence, you can use the “
[email protected]”  rather than defining the getopt function again and again.
Here is an example of using loops and [email protected] together in a script:
#!/bin/bash

num=(“$@”)

 

if [ $# -gt 1 ]

then

 

add=$((${num[0]}+${num[1]}))

echo "Addition of all numbers is: $add"

 

subtraction=$((${num[0]}-${num[1]}-${num[2]}))

echo "Subtraction of the numbers is: $subtraction"

 

multiply=$((${num[0]}*${num[1]}*${num[2]}))

echo "Multiplication of the numbers is: $multiply"

 

division1=$((${num[0]}/${num[1]}))

echo "Division of the ${num[0]} and ${num[1]} is: $division1"

 

division2=$((${num[1]}/${num[2]}))

echo "Division of ${num[1]} and ${num[2]} is: $division2"

 

division3=$((${num[0]}/${num[2]}))

echo "Division of ${num[0]} and ${num[2]} is: $division2"

 

fi
The above script performs different arithmetic calculations based on the
command-line arguments. For example, we have entered 50, 35, and 15 as the
input:

Using Positional Parameters

You can access the positional parameters as they access $1 first, then $2, and
so on. For example, let’s create a script that reads a name as the first
argument and then a city as the second. However, if you pass the city first and
then the name, then it considers the name as the city and vice versa. Let’s
take a deeper dive into the following script to understand this concept:
#!/bin/bash

echo "Here are the entered details"

echo "name $1"

echo "city $2"
You need to add the name and city at the time of executing the script in the
terminal:

Wrapping Up

This is everything you need to know about the methods to handle command line
arguments in bash. We have explained different approaches you can try with the
appropriate examples. There are various commands if you want to add arguments
in the script. So make sure you visit Linuxhint to learn more about them.


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
