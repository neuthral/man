




















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Loop Through a List of Strings

4 years ago
by Fahmida_Yesmin
A list of strings or array or sequence of elements can be iterated by using for
loop in bash. How you can iterate the list of strings in Bash by for loop is
shown in this tutorial by using various bash script examples. If you are novice
is bash programming then you can read the tutorial on BASH_For_Loop_Examples
before starting this tutorial.


Example-1: Iterating a string of multiple words within for loop

Create a bash file named ‘for_list1.sh’ and add the following script. A string
value with spaces is used within for loop. By default, string value is
separated by space. For loop will split the string into words and print each
word by adding a newline.
#!/bin/bash
# Read a string with spaces using for loop
for value in I like programming
do
    echo $value
done
Output:
$ bash for_list1.sh

Example-2: Iterating a string variable using for loop

Create a bash file named ‘for_list2.sh’ and add the following script. Assign a
text into the variable, StringValand read the value of this variable using for
loop. This example will also work like the previous example and divide the
value of the variable into words based on the space.
#!/bin/bash
# Define a string variable with a value
StringVal="Welcome to linuxhint"

# Iterate the string variable using for loop
for val in $StringVal; do
    echo $val
done
Output:
$ bash for_list2.sh

Example-3: Iterate an array of string values

Create a bash file named ‘for_list3.sh’ and add the following script. An array
of string values is declared with type in this script. Two values in the array
which contain space are “Linux Mint” and “Red Hat Linux”.   This script will
generate the output by splitting these values into multiple words and printing
as separate value. But this is not the proper output. The solution of this type
of problem is shown in the next example.
#!/bin/bash
 
# Declare an array of string with type
declare -a StringArray=("Linux Mint" "Fedora" "Red Hat Linux" "Ubuntu" "Debian"
)
 
# Iterate the string array using for loop
for val in ${StringArray[@]}; do
   echo $val
done
Output:
$ bash for_list3.sh

Example-4: Print multiple words string value as a single value

Create a bash file named ‘for_list4.sh’ and add the following script. In this
example, every element of the array variable, StringArray contains values of
two words.  To print each value without splitting and solve the problem of
previous example, you just need to enclose the array variable with double
quotationwithin for loop.
#!/bin/bash
 
# Declare a string array with type
declare -a StringArray=("Windows XP" "Windows 10" "Windows ME" "Windows 8.1"
"Windows Server 2016" )
 
# Read the array values with space
for val in "${StringArray[@]}"; do
  echo $val
done
Output:
$ bash for_list4.sh

Example-5: Iterating string values of an array using ‘*’

Create a bash file named ‘for_list5.sh’ with the following code. Here, ‘*’
symbol is used to read all string values of the array. The first for loop is
used to display array values in multiple lines and the second for loop is used
to display array values in a single line.
#!/bin/bash
 
#Declare a string array
LanguageArray=("PHP"  "Java"  "C#"  "C++"  "VB.Net"  "Python"  "Perl")
 
# Print array values in  lines
echo "Print every element in new line"
for val1 in ${LanguageArray[*]}; do
     echo $val1
done
 
echo ""
 
# Print array values in one line
echo "Print all elements in a single line"
for val2 in "${LanguageArray[*]}"; do
    echo $val2
done
echo ""
Output:
$ bash for_list5.sh
 

Example-6: Iterating comma separated string values

Create a new bash file named ‘for_list6.sh’ with the following code. Here,
comma (,) is used to split the string values.  IFS variable is used to set the
field separator.
#!/bin/bash
DataList=" HTML5, CCS3, BootStrap, JQuery "
Field_Separator=$IFS
 
# set comma as internal field separator for the string list
IFS=,
for val in $DataList;
do
echo $val
done
 
IFS=$Field_Separator
Output:
$ bash for_list6.sh

Example-7: Reading multiple string arrays together

Create a bash file named ‘for_list7.sh’ and add the following script. In this
example, two string arrays are defined and combined into another array. The
outer for loop is used to read the combined array and the inner for loop is
used to read each inner array.
#! /bin/sh
str_array1=("Magento 2.2.4" "WooCommerce")
str_array2=("CodeIgnitor" "Laravel")
combine=(str_array1 str_array2)
for arrItem in ${combine[@]}
do
   eval 'for val in "${'$arrItem'[@]}";do echo "$val";done'
done
Output:
$ bash for_list7.sh

Example-8: Using pattern to read the list of strings

Create a new bash file named for_list8.sh with the following code. Here, ‘/, /
’pattern is used to split the string values based on comma.
#! /bin/sh
 
# Define a list of string variable
stringList=WordPress,Joomla,Magento
 
# Use comma as separator and apply as pattern
for val in ${stringList//,/ }
do
   echo $val
done
Output:
$ bash for_list8.sh
Hope, the examples of this tutorial will help you to understand the use of for
loop for iterating the list of strings, for a video on this topic, see below:


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

Linux Hint LLC, [email protected]hint.com
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
