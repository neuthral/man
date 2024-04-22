





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Split String Examples

4 years ago
by Fahmida_Yesmin
We need to split the string data for various purposes in the programming. Many
programming languages have a built-in function named ‘split’ for divide any
string data into multiple parts. But there is no built-in function in bash for
dividing the string. Normally, single or multiple delimiters are used to split
any string data. How you can split the string in bash is shown in this tutorial
by using different examples.






Using $IFS variable

The special shell variable $IFS is used in bash for splitting a string into
words. $IFS variable is called Internal Field Separator (IFS) that is used to
assign the specific delimiter for dividing the string. Word boundaries are
identified in bash by $IFS. White space is the default delimiter value for this
variable. Any other value like ‘\t’, ‘\n’, ‘-‘ etc. Can be used as the
delimiter. After assigning the value into $IFS variable, the string value can
be read by two options. These are ‘-r’ and ‘-a’. The option, ‘-r’ is used to
read backslash(\) as a character rather than escape character and ‘-a’ option
is used to store the split-ted words into an array variable. The string can be
split-ted without using $IFS variable in bash. Different ways to split string
data (with $IFS or without $IFS) are shown in the following examples.

Example-1: Split string based on space

The string value is divided by white space by default. Create a file named
‘split1.sh’ and add the following code. Here, $text variable is used to assign
a string value. The shell variable, $IFS is used to assign the character that
will be used for dividing the string data. Space is used in this script as the
separator. ‘-a’ option is used with reading command to store the split-ted data
into an array variable named $strarr. ‘for’ loop is used to read each element
of the array, $strarr.
split1.sh
#!/bin/bash

#Define the string value
text="Welcome to LinuxHint"

# Set space as the delimiter
IFS=' '

#Read the split words into an array based on space delimiter
read -a strarr <<< "$text"

#Count the total words
echo "There are ${#strarr[*]} words in the text."

# Print each value of the array by using the loop
for val in "${strarr[@]}";
do
  printf "$val\n"
done
Output:
Run the script.
$ bash split1.sh
The following output will appear after running the script.

Example-2: Split string based on a particular character

Any specific character can be used as the separator for dividing the string
value. Create a file named split2.sh and add the following code. Here, book
name, author name and price value are taken by adding comma(,) as an input
string. Next, the string value is split-ted and stored in an array based the
value of the shell variable, $IFS. Each value of the array elements is printed
by the index value.
split2.sh
#!/bin/bash

#Read the string value
echo "Enter book name, author name and price by separating comma. "
read text

# Set comma as delimiter
IFS=','

#Read the split words into an array based on comma delimiter
read -a strarr <<< "$text"

#Print the splitted words
echo "Book Name : ${strarr[0]}"
echo "Author Name : ${strarr[1]}"
echo "Price : ${strarr[2]}"
Output:
Run the script.
$ bash split2.sh
The following output will appear after running the script.

Example-3: Split the string without $IFS variable

This example shows how the string value can be divided without using $IFS in
bash. Create a file named ‘split3.sh’and add the following code. According to
the script, a text value with the colon(:) has to take as input for splitting.
Here, ‘readarray’ command with -d option is used to split the string data. ‘-d’
option is used to define the separator character in the command like $IFS.
Next, ‘for’ loop is used to print the array elements.
split3.sh
#!/bin/bash

#Read the main string
echo "Enter the string with colon(:) to split"
read mainstr

#Split the string based on the delimiter, ':'
readarray -d : -t strarr <<< "$mainstr"
printf "\n"

# Print each value of the array by using loop
for (( n=0; n < ${#strarr[*]}; n++))
do
  echo "${strarr[n]}"
done
Output:
Run the script.
$ bash split3.sh
The following output will appear after running the script.

Example-4: Split the string with a multi-character  delimiter

The string value is split-ted by a single character delimiter in all previous
examples. How you can split the string by using multi-character delimiter is
shown in this example. Create a file named ‘split4.sh’and add the following
code. Here, $text variable is used to store a  string data. $delimiter variable
is used to assign a multi-character data that is used as the delimiter in the
next statements. $myarray variable is used to store each split-ted data as an
array element. Finally, all split-ted data are printed by using ‘for’ loop.
split4.sh
#!/bin/bash

#Define the string to split
text="learnHTMLlearnPHPlearnMySQLlearnJavascript"

#Define multi-character delimiter
delimiter="learn"
#Concatenate the delimiter with the main string
string=$text$delimiter

#Split the text based on the delimiter
myarray=()
while [[ $string ]]; do
  myarray+=( "${string%%"$delimiter"*}" )
  string=${string#*"$delimiter"}
done

#Print the words after the split
for value in ${myarray[@]}
do
  echo -n "$value "
done
printf "\n"
Output:
Run the script.
$ bash split4.sh
The following output will appear after running the script.

Conclusion:

The string data need to split for different programming purposes. Various ways
of splitting string data in bash are shown in this tutorial. Hope, after
practicing the above examples, the readers will be able to split any string
data based on their requirement.
For more information watch the_video!


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
