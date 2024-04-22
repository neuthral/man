




















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to compare strings in Bash

5 years ago
by Fahmida_Yesmin
For different programming purposes, we need to compare the value of two
strings. Built-in functions are used in many programming language to test the
equality of two strings. You can check the equality and inequality of two
strings in bash by using ifstatement. “==” is used to check equality and “!=”
is used to check inequality of the strings. You can partially compare the
values of two strings also in bash. How you can compare the string values in
bash is shown using various examples in this tutorial.

Example-1: String Comparison using “==” operators

There is no built-in comparison function to check equality of two string values
in bash like other standard programming language. In the following script, two
string variables, strval1and strval2 are declared. The equity of these two
string variables are tested using the first if statement of the script. The
value of strval1 is compared with a string value to check the equality in the
second if statement.
#!/bin/bash

strval1="Ubuntu"
strval2="Windows"

#Check equality two string variables

if [ $strval1 == $strval2 ]; then
  echo "Strings are equal"
else
  echo "Strings are not equal"
fi

#Check equality of a variable with a string value

if [ $strval1 == "Ubuntu" ]; then
  echo "Linux operating system"
else
  echo "Windows operating system"
fi
Output:
First comparison is not equal and second comparison is equal.

Example-2: String Comparison using “!=” operator

The inequality of two string variables are checked in the following example.
Here two values are not equal. So, if condition will be true and “Windows
operating system” will print.
#!/bin/bash

strval1="Ubuntu"
strval2="Windows"

#Check inequality of a variable with a string value

if [ $strval2 != "Ubuntu" ]; then
  echo "Windows operating system"
else
  echo "Linux operating system"
fi
Output:

Example-3: Partial String Comparison

You can compare partial value by using wild card character in bash script. In
the following script, “*” is used as wild card character for partial matching. 
The string variable, strval contains the word “Internet”.So, the first if of
the script will return true and print “Partially Match”. Bash is case
sensitive. For this, the second if of the script will return false for using
“internet” as partial string which is  not equal by letter wise comparison.
#!/bin/bash

strval="Microsoft Internet Explorer"

if [[ $strval == *Internet* ]];
then
  echo "Partially Match"
else
  echo "No Match"
fi

if [[ $strval == *internet* ]];
then
  echo "Partially Match"
else
  echo "No Match"
fi
Output:

Example-4: Compare string with user input value

Sometimes, we need to compare the string value taken by the user with specific
string value for programming purpose. In the following example, a string data
will be taken from user as input and compared the inequality of the data with a
fixed value. If the condition is true then it will print “No Record Found”,
otherwise it will print “Record Found”.
#!/bin/bash

echo "Enter Your Name"
read input

if [ $input != "Fahmida" ];
then
  echo "No Record Found"
else
  echo "Record Found"
fi
Output:
Video of this lesson is here:
String comparison task in bash will be easier for you after completing the
above examples with clear understanding.


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
