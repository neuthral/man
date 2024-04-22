





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash append to array

2 years ago
by Fahmida_Yesmin
The array data type is used in bash to store multiple data. The new data can be
inserted at the end of an array variable in various ways. Bash has no built-in
function like other programming languages to append new data in bash array. How
you can insert single and multiple data at the end of the array in bash is
shown in this article.

Example-1: Appending array element by using shorthand operator

Using shorthand operators is the simplest way to append an element at the end
of an array. In the following script, an array with 6 elements is declared.
Next ‘+=’ shorthand operator is used to insert a new element at the end of the
array. ‘for’loop is used here to iterate the array and print the array
elements.
#!/bin/bash

# Declare a string array
arrVar=("AC" "TV" "Mobile" "Fridge" "Oven" "Blender")

# Add new element at the end of the array
arrVar+=("Dish Washer")

# Iterate the loop to read and print each array element
for value in "${arrVar[@]}"
do
     echo $value
done
Output:
The following output will appear after running the script. Here, a new element,
‘Dish Washer,’ is inserted at the end of the array.

Example-2: Appending array element by defining the last index

Another simple way to insert a new element at the end of the array is to define
the last index of the array. The index of an array starts from 0, and the total
number of elements of the array can find out by using ‘#’ and ‘@’ symbol with
the array variable. In the following script, an array variable named ‘arrVar’
is declared that contains four elements. Next, the last index is defined by
using ${#arrVar[@]}. A new element is inserted at the end of the array by this
last index. The values of the array are printed like the previous example.
#!/bin/bash

# Declare a string array
arrVar=("PHP" "MySQL" "Bash" "Oracle")

# Add new element at the end of the array
arrVar[${#arrVar[@]}]="Python"

# Iterate the loop to read and print each array element
for value in "${arrVar[@]}"
do
     echo $value
done
Output:
The following output will appear after running the script. Here, the string
‘Python’ is inserted at the end of the array.

Example-3: Appending array element by using bracket

A new array element can be inserted by using the array variable and the new
element value within a first bracket. The following script shows the use of the
first brackets to append elements into an array. After appending a new element,
the array values are printed by using a loop.
#!/bin/bash

# Declare a string array
arrVar=("Banana" "Mango" "Watermelon" "Grape")

# Add new element at the end of the array
arrVar=(${arrVar[@]} "Jack Fruit")

# Iterate the loop to read and print each array element
for value in "${arrVar[@]}"
do
     echo $value
done
Output:
The following output will appear after running the script. Here, the string
‘Jack Fruit’ is inserted at the end of the array.

Example-4: Append multiple elements at the end of the array

To append multiple elements into an array, another array variable will require
to define that will contains new elements. In the following script, an array
variable named arrVar2 is declared to store the multiple elements that will be
appended into the array variable named arrVar1. Next, the values of arrVar2 are
appended into arrVar1 by using first brackets.
#!/bin/bash

# Declare two string arrays
arrVar1=("John" "Watson" "Micheal" "Lisa")
arrVar2=("Ella" "Mila" "Abir" "Hossain")

# Add the second array at the end of the first array
arrVar=(${arrVar1[@]} ${arrVar2[@]})

# Iterate the loop to read and print each array element
for value in "${arrVar[@]}"
do
     echo $value
done
Output:
The following output will appear after running the script. Here, four elements
of arrVar2 are appended to the array, arrvar1.

Conclusion:

Four different types of examples are shown in this article to append new
elements into an array.


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
