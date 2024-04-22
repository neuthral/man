





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Getopts

4 years ago
by Fahmida_Yesmin
Sometimes we need to read command line arguments and options in bash scripts.
Command line arguments can be easily read by argument variables. But for
reading both command line arguments and options, bash used a built-in command
`getopts`. This command can be used to parse short options like ‘-a’ or ‘-1′
and long options like ‘–package-name’. How `getopts` command can be used to
parse command line arguments and options are shown in this tutorial by using
different examples.
Syntax:
getopts optstring name [args]
Options:
Some mostly used getopts options are mentioned here.

Tag                Description
-o or –options   Identify one-character option.
-l or –longoptionIdentify multi-character options.
-n or –name      Report errors coming from getopts command
-q or –quiet     Disable error reporting
-T or –test      Test getopts version
-a or –alternativAllow long option with single ‘-’


Example-1: Using a singleoption

This example shows the very simple use of getopts command. Create a bash file
named ‘getopts1.sh’ with the following code to test the code. Here, while loop
will continue for the option of getopts command. Case statement will check the
option. If the option is ‘c’ then the script will print ‘My favorite color is
BLUE’. If the option is ‘f’ then the script will print ‘My favorite food is
ice-cream’. If the option is ‘-m’ then the script will print ‘My favorite movie
is titanic’. For any other option value,  “You have to use: [-c] or [-f] or [-
m]” will print.
#!/bin/bash
# read the option and store in the variable, $option
while getopts "cfm" option; do
case ${option} in
c ) #For option c
echo "My favorite color is BLUE"
;;
f ) #For option f
echo "My favorite food is ice-cream"
;;
m ) #For option m
echo "My favorite movie is titanic"
;;
\? ) #For invalid option
echo "You have to use: [-c] or [-f] or [-m]"
;;
esac
done
Run the script by using four options, ‘-c’, ‘-f’, ‘-m’ and ‘-k’.
$ bash getopts1.sh -c
$ bash getopts1.sh -f
$ bash getopts1.sh -m
$ bash getopts1.sh -k
Output:

Example-2: Using option with a single argument

This example shows the use of getopts command with an argument. Create a bash
file named ‘getopts2.sh’ with the following code to test the code. Here, ‘:’ is
used with ‘p’ to define that the command will take argument with the option.
The script will print the argument value with other string if the argument with
‘-p’ option provides at the run time. If any option will provide rather than ‘-
p’ then it will show an error message with option value. If ‘-p’ option will
provide without any argument another error message will print.
#!/bin/bash
while getopts "p:" opt; do
case ${opt} in
p )#print the argument value
echo "I like $OPTARG programming"
;;
\? )

#print option error
echo "Invalid option: $OPTARG" 1>&2
;;
: )

#print argument error
echo "Invalid option: $OPTARG requires an argument" 1>&2
;;
esac
done
Run the script with the option -p and the argument value ‘bash’, with only
option -p and with the option -t.
$ bash getopts2.sh -p bash
$ bash getopts2.sh -p
$ bash getopts2.sh -t
Output:

Example-3: Using option with multiple arguments

This example shows the uses of getopts command with multiple arguments. Create
a bash script named grtopts3.sh with the following code to test the script.
According to the script, comma separated argument values will be provided from
the command line.
Here, ‘-f’ option and IFS variable are used to split the arguments and stored
in an array, $numarr. If the comma-separated arguments will provide then it
will print the total number of arguments. Two options will support the command.
The sum of the argument values will be calculated and printed if ‘-a’ option
will provide with the arguments. The multiplication of the argument values will
be calculated and printed if the ‘-m’ option will provide with the arguments.
#!/bin/bash
while getopts "a:m:" opt; do
set -f; IFS=','
numarr=($2)
echo "Total Number of arguments = ${#numarr[@]}"
 
case $opt in
a ) result=0
for i in "${numarr[@]}"; do
((result=$result+$i))
done
echo "The sum of all arguments = $result" ;;
 
m ) result=1
for i in "${numarr[@]}"; do
((result=$result*$i))
done
echo "The multiplication of all arguments = $result" ;;
* ) echo "Invalid option or argument"
exit 1
esac
done
Run the scripts with ‘-a’ option and three arguments, with ‘-m’ option and
three arguments and the ‘-t’ option without any argument.
$ bash getopts3.sh -a 3,2,5
$ bash getopts3.sh -m 3,2,5
$ bash getopts3.sh -t
Output:

Example-4: Using multiple options and arguments

This example shows the use of getopts command with multiple options and
multiple arguments. Create a bash file named ‘getopts4.sh with the following
code to test the example. Here, two options will work with two arguments
separately. If none of the options will provide then it will print an error
message.
#!/bin/bash
while getopts "n:m:" opt; do
case $opt in
n)

#Reading first argument
echo "The name of the student is $OPTARG" >&2
;;
m)

#Reading second argument
echo " and the marks is $OPTARG" >&2
;;
*)

#Printing error message
echo "invalid option or argument $OPTARG"
;;
esac
done
When the script will run by the ‘-n’ option with ‘Ella’ and ‘-m’ option with 85
then two case statements will true and print two outputs. When the script will
run by only the ‘-n’ option with ‘Ella’ then only one case statement will true
and print one output. When the script is run by ‘-p’ option then an error
message will print.
$ bash getopts4.sh -n Ella -m 85
$ bash getopts4.sh -n Ella
$ bash getopts4.sh -p Ella

Conclusion

Basic uses of `getopts` command are shown in this tutorial by using the above
examples. Hope, after practicing this tutorial you will be able to use command
line options and arguments in your bash script.


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
