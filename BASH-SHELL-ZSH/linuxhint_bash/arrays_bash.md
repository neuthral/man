





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to use arrays in Bash

1 year ago
by Fahmida_Yesmin
When you want to use multiple data using a single variable in any programming
language, you have to use array variables. The list of data can be assigned and
used using an array variable. Bash is a weakly typed language that does not
require defining any data type for declaring the variable. Array declaration in
bash is a little bit different from other standard programming languages. Two
types of the array can be declared in bash. Numeric array and associative
array. If the index of an array is numeric, then it is called a numeric array,
and if the index of an array is a string, it is called an associative array.
How you can declare a numeric array, associative array, and iterate elements of
the array using for loop are described with examples in this tutorial.

Example-1: Numeric Array Declaration:

The default index of an array is numeric, and all values are taken as a string
value. A simple numeric array of 5 string values are declared here. The echo
command is used here to print each array values separately. If you want to
print all values of the array by single echocommand, then the “*” symbol has to
be used in the array’s index. Create a bash file with the following script that
shows two ways to declare an array in the bash script.
#!/bin/bash
MyArray=( HTML Javascript CSS JQuery Bootstrap )

# Print 5 values individually

echo "----------Print 5 values individually---------------"
echo ${MyArray[0]}
echo ${MyArray[1]}
echo ${MyArray[2]}
echo ${MyArray[3]}
echo ${MyArray[4]}

#Print all values by using *
echo "-----------------Print all values-------------------"
echo ${MyArray[*]}
Output:
The following output will appear after executing the above script.

Example-2: Associative Array Declaration:

Each index of the array needs to be declared separately in the associative
array. Create a bash file with the following script to know the use of
associative array in bash. An associative array of 4 elements is declared in
the following examples. The values of the array can be printed by using each
index separately, like the previous example. Only the indexes of the
associative array can be printed by using the “!” and “@” symbols.
#!/bin/bash

# Associative array declaration
declare -A MyArr

# Value Initialization
MyArr=( [mark]=79 [john]=93 [ella]=87 [mila]=83 )

# Print values
echo ${MyArr[mark]}
echo ${MyArr[john]}
echo ${MyArr[ella]}
echo ${MyArr[mila]}

#Print indexes

echo ${!MyArr[@]}
Output:
The following output will appear after executing the above script.

Example-3: Reading Array values using for loop:

The total number of elements of any bash array can be counted by using the “#”
and “*”symbols shown in the first part of the following example. Create a bash
file with the following script to know the way of reading array values using
the loop. Forloop is commonly used to iterate the values of an array. You can
also read array values and array indexes separately by using for loop.
Different loops are used in the following example to read array indexes, array
values, and both.
#!/bin/bash

# Associative array declaration
declare -A MyArr

# Value Initialization
MyArr=( [os]=Windows [web]=PHP [db]=Oracle )

echo "Total number of elements=${#MyArr[*]}"

echo "Array values are"
for value in ${MyArr[@]}
do
echo $value
done

echo "Array indexes are"
for key in ${!MyArr[@]}
do
echo $key
done

echo "Array values and indexes:"
for key in ${!MyArr[*]}
do
echo "$key => ${MyArr[$key]}"
done
Output:
The following output will appear after executing the above script.

Example-4: Add element into the array

The new element can be added to an array in different ways. The way to add one
or more elements using shorthand operator(+=) has shown in this example. Create
a bash file with the following script to know how the new element can be
inserted into an array.
#!/bin/bash

# Declare a numeric array
declare -a MyArr

# Initialize array with two elements
MyArr=( Ubuntu CentOS )

# Print total number of elements
echo "Total number of elements of the current array=${#MyArr[*]}"

# Add one element
MyArr+=(Fedora)

# Print total number of elements after adding one element
echo "Total number of elements after adding one element=${#MyArr[*]}"

# Add two elements
MyArr+=(RedHat LinuxMint)

# Print total number of elements after adding two elements
echo "Total number of elements after adding two elements=${#MyArr[*]}"

# Print all elements of the array
echo "Array elements are:"
echo "${MyArr[@]}"
Output:
The following output will appear after executing the above script.

Example-5: Delete an element from the array

The `unset` command is used to delete one or all elements from the array.
Create a bash file with the following script to know how to delete one and all
elements from a numeric array.
#!/bin/bash
# Declare a numeric array
declare -a MyArr

# Initialize array with two elements
MyArr=(Dell HP Lenavo Acer Asus Avita )

# Print total number of elements
echo "Total number of elements of the current array=${#MyArr[*]}"

# Print array values before delete
echo "Array values before delete:"
echo "${MyArr[@]}"

# Delete fourth element
unset MyArr[3]

# Print total number of elements after deleting an element
echo "Total number of elements after deleting one element=${#MyArr[*]}"

# Print array values after delete
echo "Array values after deleting one element:"
echo "${MyArr[@]}"

# Delete all elements
unset MyArr

# Print array values after deleting all elements
echo "Array values after deleting all elements:"
echo "${MyArr[@]}"
Output:
The following output will appear after executing the above script.

Example-6: Print the string value of multiple words

The value of the array requires to enclose with double quotes(“”) to add string
value of multiple words into an array. Create a bash file with the following
script where an associated array has initialized with the string values of
multiple words.
#!/bin/bash
 
# Declare an associative array
declare -A MyArr

# Initialize the array with the string value of multiple words
MyArr=([cse-101]="Computer Fundamental" [cse-207]="Java Programming" [cse-
312]="Web Programming")
 
# Print the array values of multiple words
echo "Array values are:"
for val in "${MyArr[@]}"; do
  echo $val
done
Output:
The following output will appear after executing the above script.

Conclusion:

The array is used in programming for many purposes. Some common and very simple
uses of the array in bash have been shown in this tutorial. After exercising
the above examples, the basic concept of bash array will be cleared for the
bash users, and they will be able to use bash array appropriately in their
script.


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
