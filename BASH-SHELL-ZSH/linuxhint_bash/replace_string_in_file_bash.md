





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Replace a String in a File in Bash

2 years ago
by Fahmida_Yesmin
As a programmer, you might need to work with different types of files to store
data temporarily or permanently. Sometimes, you may need to replace part of the
file or modify the particular content of the file. To replace content in a
file, you must search for the particular file string. The ‘sed’ command is used
to replace any string in a file using a bash script. This command can be used
in various ways to replace the content of a file in bash. The ‘awk’ command can
also be used to replace the string in a file. This tutorial will show you how
to replace any string value from a file using a bash script.A text file named
Sales.txt with the following content is created to show the replacement
operations.
Sales.txt
Date Amount Area

01/01/2020 60000 Dhaka
10/02/2020 76000 Rajshahi
21/03/2020 54000 Khulna
15/04/2020 78000 Chandpur
17/05/2020 45000 Bogra
02/06/2020 67000 Comilla

Replace String in a File with the `sed` Command

The basic syntax of the `sed` command for replacing the particular string in a
file is given below.
Syntax
sed -i 's/search_string/replace_string/' filename
Every part of the above syntax is explained below.
‘-i’option is used to modify the content of the original file with the
replacement string if the search string exists in the file.
‘s’ indicates the substitute command.
‘search_string’ contains the string value that will be searched in the file for
replacement.
‘replace_string’ contains the string value that will be used to replace the
content of the file that matches the  ‘search_string’value.
‘filename’ contains the filename where the search and replace will be applied.

Example 1: Replace File with the ‘sed’ Command

In the following script, the search-and-replace text will be taken from the
user. If the search string exists in ‘Sales.txt’, then it will be replaced by
the replacement string. Here, a case-sensitive search will be performed.
#!/bin/bash

# Assign the filename
filename="Sales.txt"

# Take the search string
read -p "Enter the search string: " search

# Take the replace string
read -p "Enter the replace string: " replace

if [[ $search != "" && $replace != "" ]]; then
sed -i "s/$search/$replace/" $filename
fi
Output

Example 2: Replace File with the ‘sed’ Command with ‘g’ and ‘i’ Flag

The following script will work like the previous example, but the search string
will be searched globally for the ‘g’ flag, and the case-insensitive search
will be done for the ‘i’ flag.
#!/bin/bash

# Take the search string
read -p "Enter the search string: " search

# Take the replace string
read -p "Enter the replace string: " replace

if [[ $search != "" && $replace != "" ]]; then
sed -i "s/$search/$replace/gi" $1
fi
Output

Example 3: Replace File with ‘sed’ Command and Matching Digit Pattern

The following script will search for all numerical content in a file and will
replace the content by adding the ‘$’symbol at the beginning of the numbers.
#!/bin/bash

# Check the command line argument value exists or not
if [ $1 != "" ]; then
# Search all string containing digits and add $
sed -i 's/\b[0-9]\{5\}\b/$&/g' $1
fi
Output

Replace String in a File with `awk` Command

The ‘awk’ command is another way to replace the string in a file, but this
command cannot update the original file directly like the ‘sed’command.

Example 4: Replace File with ‘awk’ Command

The following script will store the updated content in the temp.txt file that
will be renamed by the original file.
#!/bin/bash

# Check the command line argument value exists or not
if [ $1 != "" ]; then
# Search all string based on date
awk '{sub("02/06/2020","12/06/2020")}1' $1 > temp.txt && mv temp.txt $1
fi
Output

Conclusion

This article showed you how to use bash scripts to replace particular strings
in a file. The task to replace a string in a file should become easier for you
after practicing the above examples.


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
