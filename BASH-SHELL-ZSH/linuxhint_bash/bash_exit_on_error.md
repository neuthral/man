





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash exit on error

3 years ago
by Fahmida_Yesmin
An exit status code is returned when any Linux command is executed from the
terminal, either the command is successful or unsuccessful. This status code
can be used to show the error message for unsuccessful execution or perform any
particular task by using shell script. The exit status code always represents
by a number. The value of this code is 0 for the successful execution of any
Linux command and it returns any number from 1 to 255 for the unsuccessful
execution of the command. How the exist status code can be used from the
terminal and in the bash script are shown in this tutorial.
Some common error status codes are mention below.

Code Description Comments
     It
0    indicates
     successful
     execution.
     It is used
1    to catch    “Divide by zero”, “Operation not permitted” etc. can be the error messages of this
     all general code.
     errors.
     It
     indicates   “Missing keyword”, “No such file or directory” etc. can be the error messages of this
2    the abuse   code.
     of shell
     built-ins.
     It
     generates
126  when the    Permission problem or required key not available can generate this status code
     any command
     is unable
     to execute.
     It normally
     generates
127  for the     “Command not found” can be the message for this error code.
     command
     path
     problem.
     It
130  generates   “Script terminated by Ctrl+C” can be the message of this code.
     for fatal
     error.
     It
     indicates
255* exit code
     out of
     range.


Example-1: Reading exit code from the terminal

‘$?’ shell variable can be used to display the exit code of any command. ‘ls
–la’ is a valid command and it shows the list of files and folders of the
current working directory. The value of ‘$?’ will be 0 after executing ‘ls -la’
command. ‘ls –xyz’ is an invalid command and ‘$?’ will return 2 as error code
after executing the command.
$ ls -la
$ echo $?
$ ls -xyz
$ echo $?

Example-2: Reading exit code in bash script

Create a bash file named read_file.sh with the following script. In this
script, the file name will be taken as user’s input and, total number of lines,
words and characters of that file will be counted by using `wc` command. If the
file name is valid then the value of $status_code is 0 and if the file name is
invalid, then then the value of $status_code is 1.
read_file.sh
#!/bin/bash
echo "Enter the filename"
read filename
wc -lwc $filename
status_code=$?
echo "The exit of ‘wc’ command is : $status_code"

Example-3: Using exit code value for doing specific task

Create a bash file named read_month.sh with the following code. Here, a date
value will be taken as input. The name of the month will retrieve from the date
value if the input date is valid otherwise “invalid date” error message will
appear.  ‘if’ condition is used in the script to check the exit status code of
the date command. If the condition is true, then the success message and month
name of the date will be printed. If the condition is false, then the failure
message and exit status code, 1 will print.
read_month.sh
#!/bin/bash
echo "Enter a date in the format: YYYY-MM-DD"
read date_value
current_month=$(date -d "$date_value" '+%B')
if [ $? -eq 0 ]
then
echo "Date command is executed Successfully"
echo "Current month is $current_month"
else
echo "Date command is not executed Successfully"
exit 1
fi
Run the script.
$ bash read_month.sh

Example-4: Using && and || with exit code

‘&&’ Logical operator is used for successful exit code and ‘||’ logical
operator is used for unsuccessful exit code. The following command will print
‘File exists’ if book.txt file exists in the current location and print ‘File
not exists’ if book.txt file not exists in the current location.
$ cat book.txt && echo "File exists" || echo "File not exists"

Conclusion:

Different uses of exit status code are shown in this tutorial. Hope, the reader
will get a clear concept about exit status code of bash after reading this
tutorial.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
