





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to check the variable is set or empty in bash

3 years ago
by Fahmida_Yesmin
A variable can be defined or undefined. When any variable is not declared or
declared but no value is assigned then the variable is not set or undefined.
When any variable is declared and assigned with a value then the variable is
set. Many times it requires to know the particular variable is set or not for
the programming purposes. One of the important purposes of checking the
variable is set or not is data validation. Bash has no built-in function like
other standard programming languages to check a variable is set or not. But
bash has a feature to do this task. How you can check the variable is set or
not in bash is shown in this tutorial.
Syntax:
[[ -v variable ]] Or [[ -z variable ]]
‘-v’ or ‘-z’ option is used to check the variable is set or unset. The above
Boolean expression will return true if the variable is set and returns false if
the variable is not set or empty.
${variable+string}
Parameter substitute is another way to check the variable is set or unset. If
the variable is set, then the value of the string will return otherwise null
will return.

Example-1: Check the variable is set or unset using ‘-z’ option

Create a bash file named check_var1.sh with the following script. Here, the
first `if` condition will return true and “Num variable is not set” will print.
In the next statement, 20 is assigned to the variable, $Num. The second `if`
condition will returns false and “Num is set and the value of Num=20” will
print.
check_var1.sh
#!/bin/bash
#Check the variable is set or not
if [ -z ${Num} ]; then
  echo "‘Num’ variable is not set"
else
  echo "‘Num’ variable is set"
fi
#Assign a value
Num=20
#Check the variable is set or not after assigning the value
if [ -z ${Num} ]; then
  echo "’Num’ variable is not set"
else
  echo "’Num is set and the value of Num=$Num"
fi
Run the script.
$ bash checkvar1.sh

Example-2: Check the variable is set or unset using parameter substitute

Create a bash file named “check_var2.sh” and add the following script. Here, a
string value is assigned to the variable, $str before checking the variable is
set or unset. The ‘if’ condition will return true and the message, “’str’
variable is set and the value is Hello” will print.
check_var2.sh
#!/bin/bash
#Set the variable
str=”Hello”
#Assign the value “World” to checkval if the str variable is set
checkval=${str+”World”}
#Check the variable is set or unset
if [ $checkval -eq “World” ]; then
  echo "‘str’ variable is set and the value is $str"
else
  echo "‘str’ variable is not set"
fi
Run the script.
$ bash checkvar2.sh

Example-3: Check the variable is empty or not

Create a bash file named “check_var3.sh” and add the following script. The
script will store the first command-line argument into a variable, $argv that
is tested in the next statement. The output will be “First argument is empty”
if no argument is passed otherwise the value of the first argument will be
printed.
check_var3.sh
#!/bin/sh
#Read the first command-line argument value
argv="$1"
#Check the first argument value is provided or not
[  -v "$argv" ] && echo "First argument is empty" ||
echo "The value of the first argument is $argv"
Run the script without any argument.
$ bash checkvar3.sh
Run the script with an argument.
$ bash checkvar3.sh test

Conclusion

Different ways to check the variable is set or unset or empty are shown in this
tutorial by using various examples. Hope, this tutorial will help the users to
learn the ways of testing any bash variable.


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
