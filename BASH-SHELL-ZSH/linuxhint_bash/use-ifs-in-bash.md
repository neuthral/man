





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use $IFS in Bash?

2 years ago
by Aqsa_Yasin
In scripting, we must break string data for a variety of reasons. Split is an
integrated feature in many computer languages that divides every string of data
into various pieces. However, bash lacks a built-in feature for splitting a
string. To break any string value, there are many single and compound
delimiters to be used. A variable IFS (Internal Field Separator) is being used
to specify a particular delimiter for string division. In this guide, you will
learn how to use various methods to illustrate the process of breaking a string
value in bash using the $IFS.

Prerequisites

Make sure you have the Linux-based system installed and configured. We will be
working on Ubuntu 20.04 Linux system. Login from your Ubuntu account user to
start working on IFS. It will be better if you log in from your root user
account. After logging in, launch the command-line terminal in your system from
the Activity area.

Example 01: IFS Split a String Using Space as Value

For our first example, we will understand the concept of splitting a string in
bash while using space as a delimiter value using the IFS variable. First, we
have to create a bash file in our system. We can create new files in our Linux
system using the ‘touch’ command. As shown below, we have created a bash file
‘file1.sh’ using the ‘touch’ instruction:
$ touch file1.sh
Open the Home directory of your Linux system using the folder icon displayed at
the left corner of your Ubuntu 20.04 desktop. You will find your newly created
bash file “file1.sh” in it. Open the file “file1.sh” and type the below script.
First, we have defined a string named “str” with some string value in it. Then,
we define a delimiter variable IFS as a variable having space as its value.
After that, we used the read statement to save and read the split data into an
array “strarr” using the “-a” flag. An ‘echo’ statement is used to print a line
of string along with the count of total words of an array using the “${#strarr
[*]}”. The “for” loop is used to print the values of an array in split form
using the variable “var”. The backslash “\n” had been used within the print
line along with the variable “var” to give a split break of one line after
every value of the array. Save the script using the “Ctrl+S” key and close the
file to proceed further.
Come back to the terminal side. Now, we will check the output of the above
code. For this, we will be using the ‘bash’ command along with the name of a
file “file1.sh” to execute it which is shown below. First, it displayed the
line mentioned in the “echo” statement along with the count of words of an
array. After that, it displayed all the values of the array using the “for”
loop split by IFS.
$ bash file1.sh

Example 02: IFS Split a String using Character as Value

In the above-mentioned example, you have seen how to split string variables
into parts while using space as a delimiter of IFS. Now, we will use a
character to split a string using an IFS delimiter. Open your command terminal
and create a new bash file “file2.sh” in your home directory of the Linux
system using the “touch” command as follows:
$ touch file2.sh
Open the home directory of your Linux system. You will find your newly created
file in it. Open your newly created file and write the below-presented bash
code. On line 3, we have initiated an “echo” statement to print a line. The
next line reads the input given by a user in a terminal using the ”read”
keyword. Next, we defined the “IFS” delimiter and set comma “,” as its
character value. Another “read” statement has been specified to read and save
the comma split values of a string that is input by a user to an array
“strarr”. At last, we have initiated three echo statements to print the comma-
separated split values as variables as shown in the image. Save and close this
file.
Now, we have to execute this saved file. Execute the below-shown bash command
followed by the name of a file in a terminal to do so. You have to add some
string value that must contain comma “,” within values, and hit the Enter
button. Now your data has been saved into an array “strarr”. The last three
lines show the output of the “echo” statements. You can see, every text before
and after the comma has been used as a separate value.
$ bash file2.sh

Example 03: IFS Split String

We have done both prior examples in a bash file. We will now have an
illustration of using “IFS” without creating a bash file. Open your command
shell to do so. First, we need to create a string “var” with a string value in
it. This string contains commas after every word.
$ var=”Hi, I, am, 25, years, old.”
Next, initialize the ‘IFS’ variable with the character comma as the delimiter
value.
$ IFS=,
After that, we used the “for” loop to search each word from the variable “var”
separated by an IFS delimiter comma and print it using the “echo” statement.
$ for i in $var
>do
>echo [$i]
>Done
You will have the output below. It will show each word of a string variable
“var” at a new line because of the delimiter comma “,” used as a split
character.

Conclusion:

In this guide, you have learned a variety of methods to split the input values
in a bash, e.g., with space or with a character. We hope that the illustrations
mentioned in this tutorial guide will help you break every string using the IFS
delimiter.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
