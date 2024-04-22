





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to check if a File exists in bash

2 years ago
by Aqsa_Maqbool
There are several ways to check the availability of a file in Linux. The “test”
command in bash scripting is one of the key approaches to checking a file’s
existence.
The focus of this guide is to discuss the existence of a file in your system
through bash scripting:

How to check file existence using bash scripting:

1) By entering the file name in the terminal:
Firstly, we need to create a bash script file, use the below-mentioned command:
$ touch testfile.sh
The name of the file I created is “testfile.sh”, the “.sh” extension indicates
the shell script file:
Open the “testfile.sh” in any text editor. Then write the script, save it by
pressing “save”.
One way is to find a file by asking for a filename from the user in the
terminal.
Use “-f” to check the file’s existence.
Write the below script:
#!/bin/bash
echo "Enter your filename"
read newfile1
if [ -f "$newfile1" ]
then
echo "File is found"
else
   echo "File is not found"
fi
Go back to the terminal and run the file to print output:
./filename.sh
Permission denied message would be displayed in the terminal.
Make it executable by executing the below-mentioned command:
$chmod +x testfile.sh
Enter the file name, and it will print the output:
2) By entering the file name while writing the script:
Another way to find a file by giving the file name while writing the script. We
have three ways to check the availability of the file. The first one is using
the “test” command, the second is using “if” with an expression in square
brackets, and the third is also with “if” but double square brackets as
indicated below:

  1. “test EXPRESSION.”
  2. “if [ EXPRESSION ]”
  3. “if [[ EXPRESSION ]]”

Let’s understand it with examples:
1) test [ Expression ]
Copy the given script and paste it into the editor, save it:
#!/bin/bash
filename=file1
if test -f "$filename";
then
    echo "$file has found."
else
    echo "$file has not been found"
fi
Output:
As there is no such file in my directory, therefore the code displays the “File
is not found” message.
2) if [ Expression ]
Copy the following script to check the if file exists or not:
#!/bin/bash
filename=myfile.txt
if [ -f "$filename" ];
then
    echo "$filename has found."
else
    echo "filename has not been found"
fi
Output:
3) if [[ Expression ]]
Copy the below-written script and paste it on the terminal:
#!/bin/bash
filename=testfile
if [[ -f "$filename" ]];
then
    echo "$filename has found."
else
    echo "$filename has not been found"
fi
Output:

To check directory:

3) By entering the directory name while writing a script
Use the “-d” flag to check the existence of a directory.
In the below-mentioned script, “dir11” is the variable in which you store the
file the one you are finding; in this example, I want to check directory name
“testDir” exists or not.
#!/bin/bash
dir11=testDir
if [ -d "$dir11" ]
then
echo "Directory has found"
else
   echo "Directory has not been found"
fi
Output:
2) By entering the file name in the terminal:
When you run the command in the terminal to check whether the directory exists
or not, you are required to enter the directory name that you are searching
for:
#!/bin/bash
echo "type your directory name."
read Dir1
if [ -d "Dir1" ]
then
echo "directory has been found"
else
   echo "directory has not found"
fi
Output:

Checking the file without using the “if” statement:

The “test” command can be executed without the “if” statement. It will only
display output if the file exists; else, there would be no output:
Write script:

  1. test -f myfile.txt && echo "file has been found"
  2. [ -f myfile.txt ] && echo "$file has been found."
  3. [[ -f myfile.txt ]] && echo "$file has been found."

Output:

Checking the directory without using the “if” statement:

Use the below-mentioned statements to check a directory exists or not:

  1. [[ -d testDir ]] && echo "directory does exist"
  2. 2) [ -d testDir ] && echo "directory does exist"

Output:

Checking multiple files/Directories:

1) Checking multiple files with “if” statements:
Use the “-a” flag to check the existence of various files instead of using
nested “if/else” statements:
#!/bin/bash
if [ -f new_file.txt -a -f newfile.txt ]; then
    echo "Both files exist."
fi
Another way is:
#!/bin/bash
if [[ -f new_file.txt && -f newfile.txt ]]; then
    echo "Both files exist."
fi
Output:
2) Checking multiple files without using the “if” statement:
Use the following statement to check multiple files simultaneously 1without
using “if”:

  1. [[ -f new_file.txt  && -f  newfile.txt ]] && echo “Both files exits.”
  2. [[ -f new_file.txt  && -f  newfile.txt ]] && echo “Both files exits.”

Output:

Conclusion:

This article has shown how to use bash scripting to check a file or a
directory. We used different options to check the availability of a file.
Firstly, we use the “test” command with different flags. Then we learned the
usage of “if”, nested “if-else,” and without the “if” statements to check the
file or directory. We also looked over how to check multiple files or
directories.


About the author


Aqsa Maqbool

As a Software engineer, I am passionate to write about various IT related
articles but have deep interest in Linux. I spend most of my time reading Linux
related blogs and IT related books. I want to serve the world with my writing
skills.
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
