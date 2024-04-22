





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Remove a Specific Element from an Array in Bash

2 years ago
by Aqsa_Yasin
Although the entire process is not very simple and might seem like a hack, you
could perhaps remove an element from the existing array. We could be using more
than one method to remove an element. One of the methods is “unset,” which is
used to delete an element from a specific index and afterward replace it with
some other array. Several other sets of elements can be deleted using: also.
You can remove the list element from the end but only the solitary one using
the pop() method. Let’s have some examples for this.

Example 01: Remove Element using Prefixes Matching

Our first method; to remove a specific element from an array is prefixes
matching. Login-in from any distribution of Linux you have been currently using
and open the terminal in it.  Create a file “input.sh”. Open this file from
your home directory and write the below code in it.
Let’s explain this code step by step. To delete a specific element, you have
first to create an array. So, let’s create an array named “array” and assign it
some values, as I have assigned it three values; aqsa, raza, and saeed.
array=(aqsa raza saeed)
Now we have created another variable, “delete,” and assign it a value similar
to the one which is residing in the “array”. In reality, this technique is used
to eliminate the prefixes’ elements resembling $delete, not essentially entire
elements.
delete=saeed
After that, we have been using the echo statement to print the elements of an
array other than that of the same prefixes. Here is the code to do so:
echo ${array[@]/$delete}
When you have been working with strings, then you have to use the same script
with a few changes as below:
array=( “${array[@]/$delete}” )
You will see the output below. It will display all the elements of the array
skipping the value similar to prefixes variable “$delete”.
If somebody wants to remove more than one specific element from the array, they
can easily do it easily. Just write the below code in the file. Let’s explain
this code.
Assign the similar values from the array to the new variable as I have assigned
two values to variable $delete.
delete=(aqsa raza)
Now we will use the “for” loop to match the prefixed values to the array with
the variable $delete. The “for” loop will match the values to $delete and make
another array that wouldn’t have similar values.
for del in ${delete[@]}
do
array=(“${array[@]/$del}”)
done
echo ${array[@]/$delete}
On execution, it will display the remaining value, which is “saeed”.

Example 02: Remove Element Using Unset Command

The other method is “unset,” being used to remove an element from a specific
index and duplicate it to a certain new array. Throughout this scenario, it is
not obligated just to unset. Since unset doesn’t delete an element, it simply
assigns the null string within an array to a specific index. Write the below
code in your file.
Here we have defined a global array with the keyword “declare” followed by “-
a”. We have assigned some string values to it and print out all the values of
an array.
declare –a array=('aqsa' ‘rimsha’ ‘saeed’ ‘raza’ ‘awan’)
echo ${array[@]}
We will unset the value at index 2 from an array and declare another empty
array named “array2”.
unset ‘array[2]’
declare –a array2=()
After that, add an increment variable i=0, using the “for” loop to check the
element in the first array and assign values of the first array to the second
array, which is “array2”.
i=0
for element in ${array[@]}
do
array2[$i]=$element
((++i))
Done
echo ${array[@]}
When you print the old array again, it will not display the unset element but
all other elements. Let’s try some echo statements to check whether the unset
element is at its place or not. The first echo statement will display the
message along with the specific index number value from an “array”. You can see
that as the first value is already there in the array, it is displayed, and the
second value is unsettled; therefore, it doesn’t display.
echo “1<sup>st</sup> value is ${array[1]}, 2<sup>nd</sup> value is ${array[2]}”
Another echo statement has been written out in which we have displayed the
contents of the second array “array2” as:
echo ${array2[@]}
In the last and third echo statement, we have displayed the two specific values
of the second array “array2” as:
echo “1<sup>st</sup> value is ${array2[1]}, 2<sup>nd</sup> value is ${array2
[2]}”
On execution, you will get the below output.

Example 03: Remove an Element Using the Sub Arrays

In this example, we will be making new sub-arrays to remove an element from the
specified array. The description of the below code is given.
Let’s define an array “arr” and assign it some values as below:
arr=( ‘e1’ ‘e2’ ‘e3’ ‘e4’ ‘e5’ ‘e6’)
Now print this array using the echo statement, and we will find the values of
the array as output.
echo ${arr[@]}
The very crucial and important step of this method is to make sub-arrays of the
defined array. So let us make two arrays from the old array using the indexes
as:
arr=( “${arr[@]:0:2}” “${arr[@]:3}” )
In the above code, we used the old array to define the new substring while
setting the indexes. In “:0:2”, the first number after the colon represents the
index value, which will be included in the sub-array, while the second index
number after the colon will be excluded from the sub-array. This means that the
new sub-array will not have the value of index 2 of real array “arr” which is
“e3”. The “()” brackets are used to merge the sub-arrays and make a whole new
array “arr” again. Now when you execute the file, it will display the old and
new array as below.
echo ${arr[@]}

Conclusion

In this tutorial, we have efficiently tried three methods to remove an element
from an array, e.g., using prefixes, unset, and sub-arrays. I hope this guide
will help you understand removing an element from an array in bash.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
