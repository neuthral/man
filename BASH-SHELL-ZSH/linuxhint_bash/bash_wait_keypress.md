





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash wait for keypress

4 years ago
by Fahmida_Yesmin
`read` command is used to take user input in a bash script. We can take input
in bash script by using various types of options with the read command.
Sometimes we need to write the script in such a way that the script will run
until a specific key is pressed or the particular script will execute based on
the specific key or the program will wait for the specific amount of time until
any key is pressed. How you can write bash script to wait for any particular
key or any key to some tasks is shown in this tutorial by using different
examples.

Example#1:

Create a bash file with the following script. When you will run the script, it
will continue until the user presses any key. The script will wait for the
user’s input in every 3 seconds and if the user doesn’t press any key then it
will print the message, “waiting for the keypress“.
#!/bin/bash
echo "Press any key to continue"
while [ true ] ; do
read -t 3 -n 1
if [ $? = 0 ] ; then
exit ;
else
echo "waiting for the keypress"
fi
done
Run the script.
$ bash key1.sh
Output:

Example#2:

Create a bash file with the following script. An infinite while loop is used in
this example that will terminate when the user will press ‘q’. If the user
presses any key without ‘q’ then the value of the counter variable will be
increased by 1 and print the value.
#!/bin/bash
echo "Press 'q' to exit"
count=0
while : ; do
read -n 1 k <&1
if [[ $k = q ]] ; then
printf "\nQuitting from the program\n"
break
else
((count=$count+1))
printf "\nIterate for $count times\n"
echo "Press 'q' to exit"
fi
done
Run the script.
$ bash key2.sh
Output:

Example#3:

Create a bash file with the following script that will do different types of
tasks based on the key pressed by the user. If the user presses ‘1’ then it
will add two command line arguments and print. If the user presses ‘2’ then it
will subtract two command line arguments and print. The script will run
continuously until the user presses ‘3’.
#!/bin/bash
v1=$1
v2=$2
while :
do
echo "1. Addition"
echo "2. Subtraction"
echo "3. Quit"
echo -n "Type 1 or 2 or 3 :"
read -n 1 -t 15 a
printf "\n"
case $a in
1* )     echo "$v1 + $v2 = $(($v1+$v2))";;
 
2* )     echo "$v1 - $v2 = $(($v1-$v2))";;
 
3* )     exit 0;;

 
* )     echo "Try again.";;
esac
done
Run the script with two numeric argument values.
$ bash key3.sh 35 15
Output:

Example#4:

Create a bash file with the following script. The script will terminate when
the user will press ESC key. This script will print the keys pressed by the
user until ESC key is pressed.
#!/bin/bash
userinput=""
echo "Press ESC key to quit"
# read a single character
while read -r -n1 key
do
# if input == ESC key
if [[ $key == $'\e' ]];
then
break;
fi
# Add the key to the variable which is pressed by the user.
userinput+=$key
done
printf "\nYou have typed : $userinput\n"
Run the script.
$ bash key4.sh
Output:

Example#5:

Create a bash file with the following code that will wait for ENTER key to
terminate the script. The script will take a server name as input and will try
to ping the server in every 2 seconds. If ping command gets the response from
the server then it will terminate the script by displaying the output otherwise
it will wait for the user’s response or ENTER key by printing the message,
“Trying to connect with…”.
#!/bin/bash
echo "Enter the server address that you want to ping"
read server
while ! ping -c 1 -n -W 2 $server
do
echo "Trying to connect with $server"
echo "Press [ENTER] to terminate"
read -s -N 1 -t 1 key
if [[ $key == $'\x0a' ]];        # if input == ENTER key
then
exit 0
fi
done
printf "%s\n" "$server is running"
Run the script.
$ bash key5.sh
Output:

Conclusion:

This tutorial shows how you can write the bash script in various ways that will
wait for the user’s input to do any specific task or terminate the script.
Hope, after practicing the above examples, you will be able to write the script
in such way that can wait for any keypress and do the particular task based on
the key pressed by the user.


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
