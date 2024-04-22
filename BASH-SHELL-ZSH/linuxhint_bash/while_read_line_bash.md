





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash: while read line

2 years ago
by Karim_Buzdar
When you are working on bash scripts, sometimes you may need to read a file
line by line. Let’s explain with an example. You have some data in a text file
that should be executed or processed by using a script. So, running a bash
script to process a text file is much different. You need to follow a specified
syntax to read a file line by line. This article will help you to read a line
from a file using the while loop in Bash.

Basic Syntax of while read line

The following syntax is used for bash shell to read a file using while loop:
while read -r line;
do
   echo "$line" ;
done < input.file
The option ‘-r’ in the above-mentioned syntax passed to read command that
avoids the backslash escapes from being interpreted. The ‘input_file’ option
has represented the name of your file that you want to access by using the
‘read’ command.
The internal field separator abbreviated as IFS can be used before the read
command is set to the null string that prevents leading or trailing whitespace
from being trimmed.
while IFS= read -r line;
do
   echo $line;
done < input.file
Open the terminal using Ctrl + Alt + t shortcut and then run the following
commands on it.

Example # 1: File Reading line by line

Let’s take an example in which suppose we have a file named OS.txt containing
the names of all important Linux distributions. If you want to read a file
without using the ‘cat’ command then, for this purpose you can execute the
following command to perform the particular task. We will use the while loop
that will read each line from the file OS.txt and stores the content in each
step in a variable $line that you can display later.
Paste the following names of Linux distributions in the OS.txt
CentOS
Ubuntu
Debian
LinuxMint
$ while read line;
do
echo $line;
done < OS.txt

From the above command, you will get the following response on the terminal
window:

Example # 2: Reading file using the bash script

Create a bash file and then add the below-mentioned code in this file to read
the file content. You can store the previous text file into a new variable
$filename and variable $n is used to keep the value of each line. Now, using
the while loop we will read each line from a file with a particular line
number.
#!/bin/bash
filename='OS.txt'
n=1
while read line;
do
# for read each line
echo "OS distribution line no. $n : $line"
n=$((n+1))
done < $filename
Save the file with a name OSinfo.sh and type the following command on the
terminal to run the above bash script.
$ bash OSinfo.sh
Now, run the cat command to view the original file content.
$ cat OS.txt

Alternative Method for file reading


Using passing file name from a command

In a bash file, you need to add the following code script. In this script, we
have to take a filename as an argument. First, the value of an argument is read
by a $1 variable which has a filename for reading.  It will check that filename
exists at the specified location then using the while loop it read a file line
by line similar to the previous example.
#!/bin/bash
filename=$1
while read line; do
# reading each line
echo $line
done < $file.txt
Save the above script with named ‘Readline.sh’ and execute the following
command on the terminal to run the above-mentioned script:
In the above output, you will observe that the file ‘OSinfo.txt’ is passing as
an argument and the content of ‘OSinfo.txt’ will be displayed after removing
extra spaces. You can display the original file content by running ‘cat
OSinfo.txt’.

Conclusion

In this article, we have discussed how to read lines using the while loop in
bash programming. We have implemented different methods using the bash script
or you can simply use a text file to perform reading a file line by line task.
If you are interested to learn more examples then using the above-mentioned
syntax you can execute on your system as well. I hope you enjoyed this tutorial
and would unique for you. Let’s know in case of any error.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
