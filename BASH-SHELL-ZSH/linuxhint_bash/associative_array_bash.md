





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Associative array in Bash

3 years ago
by Fahmida_Yesmin
An array variable is used to store multiple data with index and the value of
each array element is accessed by the corresponding index value of that
element. The array that can store string value as an index or key is called
associative array. An associative array can be declared and used in bash script
like other programming languages. This feature is added in bash 4. How
associative array can be declared and accessed in bash are explained in this
tutorial.
Check the current version of Bash before starting the next part of this
tutorial. Run the following command from the terminal to check the installed
version of bash. If the installed bash version in your operating system is less
than 4 then you have to installed the bash version 4 first to continue this
tutorial.
$ bash --version
The following output shows that the current version of bash is 4.4.19.

Declaring and initializing Associative Array:

An associative array can be declared in bash by using the declare keyword and
the array elements can be initialized at the time of array declaration or after
declaring the array variable. The following script will create an associative
array named assArray1 and the four array values are initialized individually.
$ declare -A assArray1
$ assArray1[fruit]=Mango
$ assArray1[bird]=Cockatail
$ assArray1[flower]=Rose
$ assArray1[animal]=Tiger
Output
The following script will initialize the associative array, assArrat2 at the
time of array declaration. Here, three array values with keys are defined at
the time of array declaration.
$ declare -A assArray2=( [HDD]=Samsung [Monitor]=Dell [Keyboard]=A4Tech )
Output:

Accessing the Associative Array:

Array elements of an associative array can be accessed individually or by using
any loop. These two ways are shown in this part of the tutorial. Array keys and
values can be print separately and together.
The following commands will print two values of the array, assArray1 (declared
earlier) by specifying the key value.
$ echo ${assArray1[bird]}
$ echo ${assArray1[flower]}
Output:
The following output will appear after running the above commands.
Sometimes, it is required to print all keys or all values of the array. All
keys of an array can be printed by using loop or bash parameter expansion. The
following first command will print all keys of the array in each line by using
for loop and the second command will print all array keys in one line by using
bash parameter expansion. Here, ‘!’  symbol is used for reading the keys of the
associative array.
$ for key in "${!assArray1[@]}"; do echo $key; done
$ echo "${!assArray1[@]}"
Output:
The following output will appear after running the above commands.
All values of an array can be printed by using loop or bash parameter
expansion. The following first command will print all values of the array in
each line by using for loop and the second command will print all array values
in one line by using bash parameter expansion.
$ for val in "${assArray1[@]}"; do echo $val; done
$ echo "${assArray1[@]}"
Output:
The following output will appear after running the above commands.
Both keys and values of an associative array can be printed by using for loop.
The following script will print all values with keys of the associative array
named assArray1. Here, each key of the array will be parsed in each step of the
for loop and the key is used as the index of the array to read the value of the
corresponding key.
$ for key in "${!assArray1[@]}"; do echo "$key => ${assArray1[$key]}"; done
Output:
The following output will appear after running the script.

Adding new data in Associative Array:

A new array element can be added easily in the associative array after
declaring and initializing the array. The following commands will check the
current array values of the array, assArray2, add a new value, “Logitech” with
the key, “Mouse” and again check the current elements of the array.
$ echo "${assArray2[@]}"
$ assArray2+=([Mouse]=Logitech)
$ echo "${assArray2[@]}"
Output:
The following output will appear after running the commands.

Deleting data from Associative Array:

Any element value of the associative array can be removed based on the key
value. `unset` command is used to delete the particular value of the
associative array. The following commands are used check the current value of
the array with the key, “Monitor”, delete the value using unset command and
again run the `echo` command to check the value is deleted or not.  $ echo $
{assArray2[Monitor]}
$  unset assArray2[Monitor]
$ echo ${assArray2[Monitor]}
Output:
The following output will appear after running the commands.

Finding missing index from Associative Array:

Missing index or key of an array can be found by using a conditional statement.
The following script will check the array key, “Monitor” exists or not. The
value of this key is removed in the previous example. So, the `if` condition
will return false and “Not Found” message will be printed.
$ if [ ${assArray2[Monitor]+_} ]; then echo "Found"; else echo "Not found"; fi
Output:
The following output will appear after running the script.

Removing Associative Array:

Any associative array can be removed by using `unset` command. The following
first command will print all values of the array named assArray1 in a single
line if the array exists. The second command will remove the array. The third
command is used to check the array exists or removed. If the array is removed,
then no output will appear.
$ echo "${assArray1[@]}"
$ unset assArray1
$ echo "${assArray1[@]}"
Output:
The following output will appear after running the commands.

Conclusion

When it is required to store multiple data of key-value pair in bash, then it
is better to use the associative array for storing the data. How the coder can
declare and initialize the associative array, parse array keys or values or
both, add and delete array elements and remove array are shown in this tutorial
by using various scripts. Hope, the reader will able to use associative array
in bash properly after reading this tutorial.


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
