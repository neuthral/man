




















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to read file line by line in Bash script

4 years ago
by Fahmida_Yesmin
How would you write a Bash script that can process a text file one line at a
time.  First you need a syntax and approach to read the file line by line. The
methods for this approach are shown in this tutorial.
Suppose, you have a file named company.txt which contents the company names.
This file contains the following content.
Company.txt
Samsung
Nokia
LG
Symphony
iphone

Example -1: Reading file content from command line

Suppose, you want to read the file, company.txt, line by line from the command
line without ‘cat’ command. Run the following command to do the task. while
loop will read each line from the file company.txt in each step and store the
content of the line in $linevariable which will be printed later.
$ while read line; do echo $line; done < company.txt

Example -2: Reading file content using script

Create a bash file and add the following code to read the content of a
particular file. Here, an existing filename is stored in $filename variable and
$n variable is used to keep the value of the line number of that file. Like
previous example, while loop is used to read this file with line number.
#!/bin/bash
filename='company.txt'
n=1
while read line; do
# reading each line
echo "Line No. $n : $line"
n=$((n+1))
done < $filename
Run the following command to execute the script.
$ bash readfile1.sh
Run ‘cat’ command with company.txt file to display the original content of
company.txtfile.
$ cat company.txt

Example -3: Passing filename from the command line and reading the file

Create a bash file and add the following script. This script will take the
filename from the command line argument. First argument value is read by the
variable $1 which will contain the filename for reading. If the file exists in
the current location then while loop will read the file line by line like
previous example and print the file content.
#!/bin/bash
filename=$1
while read line; do
# reading each line
echo $line
done < $filename
Run the above script with employee.txt file as argument value. The output will
show the content of employee.txt file by removing extra space. You can show the
original content of employee.txt file by using ‘cat’ command.
$ bash readfile2.txt employee.txt
$ cat employee.txt

Example – 4: Reading file by omitting backslash escape

If you want to read each line of a file by omitting backslash escape then you
have to use ‘-r’ option with read command in while loop.
#!/bin/bash
while read -r line; do
# Reading each line
echo $line
done < company2.txt
Create a file named company2.txt with backslash and run the following command
to execute the script. The output will show the file content without any
backslash.
$ bash readfile3.sh
You will need to read the file for many programming purposes. For example, you
can search or match any particular content easily from any file by reading each
line separately. So, it is an essential task for any programming. Some simple
examples of reading file in bash script are shown in this tutorial. These will
help you to get the idea of reading file content line by line using while loop
in bash script and apply in your script more efficiently. For more information
watch the_video!


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
