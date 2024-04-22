





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash yes Command

4 years ago
by Fahmida_Yesmin
Bash `yes` command is one of those commands of Linux that is related to the
operation of another command. Using this command is useless when you execute
the command independently. By default, `yes` command repeats the character ‘y’
if no string value is specified with this command. When `yes` command uses with
pipe and another command then it will send the value ‘y’ or `yes` for any
confirmation prompt. This command can help to save time by doing many
confirmation tasks automatically.


Syntax

You can use `yes` command with an option or any string value, but both are
optional for this command.
yes [OPTION]
yes [STRING]…

Options

This command has not more options.  Two options of this command are mentioned
below.
–version
It is used to display the installed version of this command.
–help
It is used to get detail information of this command.

Example#1:

When you run the `yes` command without any option and string value then it will
print ‘y’ for infinite times.
$ yes
Output:
The following output will appear.

Example#2:

When you run the `yes` command with a specific string value then it will print
the string value for infinite times.
$ yes test
Output:
The following output will appear.

Example#3:

`cp` command is used in bash to create any new file by copying an existing
file. If the new filename exists then it will ask for overwrite permission if
you run cp command with -i option. In this example, two text files hello.txt
and sample.txt are used. If these two text files exist in the current location
and `cp` command is run for copying sample.txt to hello.txt with -i option then
it will ask for overwrite permission.
$ cat hello.txt
$ cat sample.txt
$ cp -i sample.txt hello.txt
You can use `yes` command to prevent from overwriting the existing file or
forcefully overwrite the existing file. In the following commands, the first
command is used to prevent the overwrite and the second command is used to
overwrite the file without any permission.
$ yes n | cp -i sample.txt hello.txt
$ yes | cp -i sample.txt hello.txt
Output:

Example#4

You can use `yes` command to run any script multiple times in the command line.
In this example, `yes` command is used to run while loop repeatedly ten times.
Here, `yes` command will continuously send the numeric value from 1 to 10 to
the loop and the loop will print the values in regular interval of one second.
$ yes "$(seq 1 10)" | while read n; do  echo $n; sleep 1; done
Output:

Example#5:

You can use `yes` command to send any string value to a script while executing
the script file. Create a bash file named ‘yes_script.sh’ and add the following
script. If you run the script using `yes` command with empty string then it
will print “Empty value is passed by yes command” otherwise it will print the
string value send by `yes` command by combining with other string.
#!/bin/bash
#Read the value passed from yes command
read string

#check the string value is empty or not
if [ "$string" == "" ]; then

echo "Empty value is passed by yes command"
else
newstr="The value passed by yes command is $string"
echo $newstr
fi
Run the `yes` command with an empty string and the bash script file,
yes_script.sh.
$ yes "" | bash yes_script.sh
Output:
Run the yes command with a string value, “testing” and the bash script file,
yes_script.sh.
$ yes testing | bash yes_script.sh
Output:

Example#6:

You can use `yes` command for the testing purpose also. You can run the
following command to create a file with a huge amount of data for testing.
After executing the command, a file named ‘testfile’ will be created that will
contain 50 lines with the content, ‘Add this line for testing’.
$ yes 'Add this line for testing' | head -50 > testfile
Output:

Conclusion

The basic uses of `yes` command are shown in this tutorial by using different
types of examples. It is a very useful command when you are confirmed about any
task and don’t want to waste time for unnecessary confirmation. You can use
this command for some advanced level tasks, such as comparing processors
ability or the loading capacity of any computer system etc.


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
