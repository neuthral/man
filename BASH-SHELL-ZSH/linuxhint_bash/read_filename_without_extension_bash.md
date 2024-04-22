





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Read filename without extension in Bash

3 years ago
by Fahmida_Yesmin
Linux users need to work with files regularly for many purposes. Sometimes the
users need to read the basename of the file only by removing the file
extension. Filename and extension can be separated and stored on different
variables in Linux by multiple ways. Bash built-in command and shell parameter
expansion can be used to remove the extension of the file. How the filename
without extension can be read by using the ways mentioned above are explained
in this tutorial.

Using `basename` command to read filename

`basename` command is used to read the file name without extension from a
directory or file path.
Syntax:
basename NAME [SUFFIX]
or
basename OPTION... NAME...
Here, NAME can contain the filename or filename with full path. SUFFIX is
optional and it contains the file extension part that the user wants to remove.
`basename` command has some options which are described below.
Options

Name     Description
-a       It is used to pass multiple filenames with path or without path as
         command arguments.
-s       It is used to pass the extension as suffix that needs to remove.
-z       It is used to display the multiple filenames by separating each file
         with null.
–help  It is used to display the information of using `basename` command.
–versioIt is used to display the version information.


Example-1: Using NAME and SUFFIX

The following `basename` command will retrieve the filename with extension.
SUFFIX is omitted from this command. Here, the output is ‘product.txt’.
$ basename /home/fahmida/code/product.txt
If you want to retrieve the filename without extension, then you have to
provide the file extension as SUFFIX with `basename` command. Here, the
extension is “.txt”. Run the following command to remove the extension from the
file.
$ basename /home/fahmida/code/product.txt .txt

Example-2: Using ‘-a’ option and NAME

The use of ‘-a’ option of `basename` command is shown in this example. Here,
two file paths are passed as arguments with `basename` command. Each filename
with extension will retrieve from the path and print by newline.
$ basename -a /home/fahmida/index.html /home/fahmida/code/emp.txt

Example-3: Using ‘-z’ option and NAME

‘-z’ option is used with `basename` command to print the multiple filenames
with null value instead of newline. The following command uses two options
together, ‘-a’ and ‘-z’. Here, two filenames, index.html and emp.txt will print
without any space or newline.
$ basename -az /home/fahmida/index.html /home/fahmida/code/emp.txt

Example-4: Using ‘-s’ option and NAME

The following command can be used as an alternative of SUFFIX with `basename`.
File extension needs to pass with ‘-sh’ option to remove the file extension
from the file. The following example will remove the extension, ‘-sh’ from the
file, ‘addition.sh’.
$ basename -s .sh addition.sh

Example-5: Remove file extension without SUFFIX

If you don’t know the extension of the file that you want to remove from the
filename, then this example will help you to solve the problem. Create a file
named read_file.sh with the following code to retrieve filename of any
extension. `sed` command is used in this example to remove any type of
extension from the filename. If you run the script, the output will be
‘average’ after removing the extension ‘py’.
read_file.sh
#!/bin/bash
# Set the filename with path
filename="/home/fahmida/code/average.py"
# Read the filename without extension by using ‘basname’ and `sed` command
echo "$(basename "$filename" | sed 's/\(.*\)\..*/\1/')"
Run the script.
$ bash read_file.sh

Example-6:  Convert file extension from txt to docx

Filename without extension needs to convert the file from one extension to
another. This example shows that how you can change the extension of all text
files (.txt) into the word files (.docx) by using `basename` command in the
bash script. Create a file named, convert_file.sh with the following code.
Here, a for-in loop is used to read all the text files with “.txt”extension
from the current directory. The filename without extension is read by
`basename` command and renamed by adding “.docx” extension in each iteration of
the loop.
convert_file.sh
#!/bin/bash
# the loop will read each text file from the current directory
for filename in `ls *.txt`
do
  # Print the text filename before conversion
  echo "Filename before conversion : $filename"
  # Change the extension of the file txt to docx
  mv -- "$filename" "$(basename -- "$filename" .txt).docx"
done
Run the script.
$ bash convert_file.sh
Check the text files are converted or not by using `ls` command.
$ ls

Example-7: Read filename without extension using Shell parameter expansion

Shell parameter expansion is another way to read the filename without extension
in bash. This example shows the uses of shell parameter expansion. The
following command will store the file pathname in the variable, $filename.
$ filename="/var/usr/temp/myfile.tar.gz"
The following command will remove all types of extension from the path and
store the file path without extension in the variable, $file1.
$ file1="${filename%%.*}"
The following command will print the filename only from the path. Here, the
output will ‘myfile’.
$ echo "${file1##*/}"
If the filename contains two extensions with two dot(.) and you want to read
the filename by removing the last extension of the file then you have to use
the following command. Run the following command that store the file path into
the variable, $file2 by removing the last extension of the file.
$ file2="${filename%.*}"
Now, run the following command to print the filename with one dot (.)
extension. Here, the output will be “myfile.tar”.
$ echo "${file2##*/}"

Conclusion

Filename without extension is required for various purposes. Some uses of
filename without extension are explained in this tutorial by using some
examples such as file conversion. This tutorial will help those users who are
interested to learn the ways to separate the file name and extension from the
file path. Two ways are explained here. The user can follow any of these ways
to extract the filename only from the file path.


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
