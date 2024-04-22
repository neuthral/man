





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to trim string in bash

3 years ago
by Fahmida_Yesmin
Sometimes it requires to remove characters from the starting and end of the
string data which is called trimming. There is a built-in function named trim()
for trimming in many standard programming languages. Bash has no built-in
function to trim string data. But many options are available in bash to remove
unwanted characters from string data, such as parameter expansion, sed, awk,
xargs, etc. How you can trim string in bash is shown in this tutorial by using
different examples.

Example-1: Trim string data using parameter expansion

Space or any character can be trimmed easily from the string data by using bash
parameter expansion. The following commands show the uses of parameter
expansion for removing space from the starting and end of the string.
# Declare a variable, $myvar with a string data.
$ myVar=" everyone "

# The following command will show the spaces at the starting and end of the
variable, $myVar
$ echo "Hello $myVar"

# The following command will print the output after removing the spaces from
the beginning
of the variable, $myVar
$ echo "Hello ${myVar##*( )}"

#The following command will print the output after removing the spaces from
the ending of the
variable, $myVar
$ echo "${myVar%%*( )} is welcome to our site"

Example-2: Trim string data using `sed` command

`sed` command is another option to remove leading and trailing space or
character from the string data. The following commands will remove the spaces
from the variable, $myVar using `sed` command.
# Declare a variable, $myVar with a string data
$ myVar="     Web Design Courses    "

# The following command will print the output with the leading and trailing
spaces of the
variable,$myVar
$ echo "I want to learn $myVar from this site"

# The following `sed` command will remove the trailing spaces from the variable
$ myVar=`echo $myVar | sed 's/ *$//g'`

# Print the output after removing the spaces
$ echo "I want to learn $myVar from this site"
Use sed ‘s/^ *//g’, to remove the leading white spaces.
There is another way to remove whitespaces using `sed` command. The following
commands removed the spaces from the variable, $Var by using `sed` command and
[[:space:]].
# Declare the variable, $Var with a string value
$ Var=" PHP and MySQL "

# Print the value of $Var before trimming
$ echo "$Var are very popular now."

#Remove the spaces from the variable
$ Var=`echo $Var | sed -e 's/^[[:space:]]*//'`

# Print the value of $Var after trimming
$ echo "$Var are very popular now."

Example-3: Trim string data using `awk` command

`awk` command is another way to trim the string value. The following commands
uses `awk` command to remove spaces from the starting and ending of the
variable, $Input_text.
# Declare a variable with a string data
$ Input_text=" Desiginning Website with CSS3 "
# Print the value of the variable before trimming
$ echo "${Input_text}"
# Print the string after Removing the spaces from the beginning of the variable
$ echo "${Input_text}" | awk '{gsub(/^[ \t]+/,""); print $0, " JQuery" }'
# Print the string after Removing the spaces from the end of the variable
$ echo "${Input_text}" | awk '{gsub(/[ \t]+$/,""); print $0, " JQuery" }'
# Print the string after Removing the spaces from the beginning and end of the
variable
$ echo "${Input_text}" | awk '{gsub(/^[ \t]+| [ \t]+$/,""); print $0, " JQuery"
}'

Example-4: Trim string data using xargs command

`xargs` is another simple command to trim string data.
# Remove the spaces from the string data using `xargv`
$ echo " Bash Scripting Language " | xargs

Conclusion:

This tutorial shows the different ways to trim string data. The string data
needs to trim for various reasons. For example, it is better to remove extra
spaces from the starting and end of the data before inserting into the database
or compare with other value. This tutorial will help the new users to learn
trimming options in bash.


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
