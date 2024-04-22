




















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


BASH command output to the variable

4 years ago
by Fahmida_Yesmin
Different types of bash commands need to be run from the terminal based on the
user’s requirements. When the user runs any command from the terminal then it
shows the output if no error exists otherwise it shows the error message.
Sometimes, the output of the command needs to be stored in a variable for
future use. Shell command substitution feature of bash can be used for this
purpose. How you can store different types of shell commands into the variable
using this feature is shown in this tutorial.


Command Substitution Syntax:

variable=$(command)
variable=$(command [option…] argument1 arguments2 …)
variable=$(/path/to/command)
OR
variable=`command`
variable=`command [option…] argument1 arguments2 …`
variable=`/path/to/command`
***Note: Don’t use any space before and after the equal sign when using the
above commands.

Single command output to a variable

Bash commands can be used without any option and argument for those commands
where these parts are optional. The following two examples show the uses of
simple command substitution.

Example#1:

bash `date`command is used to show the current date and time. The following
script will store the output of `date`command into $current_date variable by
using command substitution.
$ current_date=$(date)
$ echo "Today is $current_date"
Output:

Example#2:

`pwd` command shows the path of the current working directory. The following
script stores the output of `pwd` command into the variable, $current_dir and
the value of this variable is printed by using `echo`command.
$ current_dir=`pwd`
$ echo "The current directory is : $current_dir"
Output:
Command with option and argument
The option and argument are mandatory for some bash commands. The following
examples show how you can store the output of the command with option and
argument into a variable.

Example#3:

Bash `wc`command is used to count the total number of lines, words, and
characters of any file. This command uses -c, -w and -l as option and filename
as the argument to generate the output. Create a text file named fruits.txt
with the following data to test the next script.
fruits.txt
fruits.txt
Mango
Orange
Banana
Grape
Guava
Apple
Run the following commands to count and store the total number of words in the
fruits.txtfile into a variable, $count_words and print the value by using
`echo` command.
$ count_words=`wc -w fruits.txt`
$ echo "Total words in fruits.txt is $count_words"
Output:

Example#4:

`cut` is another bash command that uses option and argument to generate the
output. Create a text file named weekday.txt with seven-weekday names to run
the next script.
weekday.txt
Monday
Tuesday
Wednesday
Thursday
Friday
Saturday
Sunday
Create a bash file named cmdsub1.sh with the following script.  In this script,
while loop is used to read the content of weekday.txt file line by line and
read the first three characters of each line by using `cut` command. After
cutting, the string value is stored in the variable $day. Next, If the
statement is used to check the value of $day is ‘Sun’ or not. The output will
print ‘Sunday is the holiday‘ when if the condition is true otherwise it will
print the value of $day.
cmdsub1.sh
#!/bin/bash
filename='weekday.txt'
while read line; do
day=`echo $line | cut -c 1-3`
if [ $day == "Sun" ]
then
echo "Sunday is the holiday"
else
echo $day
fi
done<$filename
Run the script.
$ cat weekday.txt
$ bash cmdsub1.sh
Output:

Using command substitution in loop

You can store the output of command substitution into any loop variable which
is shown in the next example.

Example#5:

Create a file named cmdsub2.sh with the following code. Here, `ls -d */
` command is used to retrieve all directory list from the current directory.
For loop is used here to read each directory from the output and store it in
the variable $dirname which is printed later.
cmdsub2.sh
#!/bin/bash
for dirname in $(ls -d */)
do
echo "$dirname"
done
Run the script.
$ bash cmdsub2.sh
Output:

Using nested commands

How you can use multiple commands using pipe(|) is shown in the previous
example. But you can use nested commands in command substitution where the
output of the first command depends on the output of the second command and it
works opposite of the pipe(|) command.
Nested command syntax:
var=`command1 \`command\``

Example#6:

Two commands, `echo` and `who` are used in this example as the nested command.
Here, `who` command will execute first that print the user’s information of the
currently logged in user. The output of the `who` command will execute by
`echo` command and the output of `echo` will store into the variable $var.
Here, the output of `echo` command depends on the output of `who` command.
$ var=`echo \`who\``
$ echo $var
Output:

Using Command path

If you know the path of the command then you can run the command by specifying
the command path when using command substitution. The following example shows
the use of command path.

Example#7:

`whoami`command shows the username of the currently logged in user. By default,
this command is stored in /usr/bin/ folder. Run the following script to run
`whoami` command using path and store in the variable, $output,and print the
value of $output.
$ output=$(/usr/bin/whoami)
$ echo $output
Output:

Using Command Line argument

You can use the command line argument with the command as the argument in the
command substitution.

Example#8:

Create a bash file named cmdsub3.sh with the following script. `basename`
command is used here to retrieve the filename from the 2nd command line
argument and stored in the variable, $filename. We know the 1st command line
argument is the name of the executing script which is denoted by $0.
#!/bin/bash
filename=`basename $1`
echo "The name of the file is $filename."
Run the script with the following argument value.
$ bash cmdsub3.sh Desktop/temp/hello.txt
Here, the basename of the path, Desktop/temp/hello.txtis ‘hello.txt’. So, the
value of the $filename will be hello.txt.
Output:

Conclusion:

Various uses of command substitutions are shown in this tutorial. If you need
to work with multiple commands or depended commands and store the result
temporary to do some other tasks later then you can use this feature in your
script to get the output.
More info in the video:



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
