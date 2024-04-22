





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Basic Ways on How to Take Input from a User in Bash Script

2 weeks ago
by Prateek_Jangid
Reading the user input is an integral part of an interactive Bash script. A
Bash script includes specific commands that the terminal executes in a fixed
sequence. At the same time, an interactive Bash script is where the user
decides what happens next.
Both have pros and cons, but it is good to learn the basic ways to read an
input from the users while executing a Bash script. This guide includes the
method to read the user input through the read command and passing the inputs
as a parameter when running a Bash script.

Basic Ways on How to Take Input from a User in Bash Script

The read command pauses the console and awaits the user input. You can use this
command as it is in the terminal or it can be used with the other commands
inside a Bash script to accept the user input while executing a script. For
instance, let’s create a sample Bash script that contains the following codes:
#!/bin/bash

# Read the user input using read command
read PARAM1

echo $PARAM1
In the previous code snippet, we created a Bash script to accept an input from
the user using theread command and print it back in the console using the echo
command. Now, we can run the script in the terminal and enter the word “Linux”.
The system automatically reprints the word:
./<script>.sh

Linux

Linux
If you want to input the multiple variables, you can use the following script
as an example:
#!/bin/bash

# Read the user input using read command
read PARAM1

read PARAM2
read PARAM3

read PARAM4

echo "Best Linux OS are:"
echo $PARAM1

echo $PARAM2

echo $PARAM3

echo $PARAM4
Once you run this script, the terminal will ask you to provide 4 inputs to
print them as an output:
./<script>.sh

Ubuntu

Fedora

Kali Linux

Arch Linux

Best Linux OS are:

Ubuntu

Fedora

Kali Linux

Arch Linux
You can add a -s flag with the read command if you don’t want to print the
input. The -s flag silently accepts the user input in the terminal and prints
it when a user presses the Enter button. Here is the script code that you can
try:
#!/bin/bash

# Read the user input using read command
read -s PARAM1

echo $PARAM1
The previous script prints the following results after the successful
execution:
./<script>.sh

Linux
If you want to print something with a specific time limit, use the-t flag with
the read command. When you provide the input at that specified time, the script
proceeds as normal or it simply skips the input and continues with the rest of
the script.
#!/bin/bash

# Read the user input using read command
read -t 5 PARAM1

echo $PARAM1
echo "Will this be printed?"
According to the previous script, the system will wait for 5 seconds for the
input and then skips it to run the rest of the script.
./<script>.sh

Will this be printed?
You can use the -n flag to limit the number of input characters for a script.
For example, the following script requires 7 characters to run the rest of the
script successfully:
#!/bin/bash

# Read the user input using read command
echo "The input will be submitted after accepting 7 characters"
read -n 7 PARAM1

# Print the input that the user typed
echo $PARAM1
As per the script, you would have submitted the input after 7 characters, and
that’s what happened in the following:
./<script>.sh

LinuxOSLinuxOS

Conclusion

This is the brief information on the methods on how to take an input from a
user in a Bash script. All of them are pretty simple. On a side note, we can
also mix and match these parameters to input the variable. As a beginner, the
given examples may help you create the script and input the desired details.


About the author


Prateek Jangid

A passionate Linux user for personal and professional reasons, always exploring
what is new in the world of Linux and sharing with my readers.
View_all_posts

RELATED LINUX HINT POSTS


* 10_Cool_and_Awesome_Bash_Loop_Examples
* What_are_Double_Parentheses_in_Bash
* Floating_Point_Math_in_Bash
* Bash_Continue_Built-In_Statement
* 10_Most_Important_Things_to_Know_About_Bash_Scripting
* Mastering_Backticks_in_Linux_Bash_Scripts
* Making_a_Bash_Script_Return_with_Different_Return_Codes_on_Exit

Linux Hint LLC, [email protected]
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
