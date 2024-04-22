





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash declare an empty array

1 year ago
by Aqsa_Yasin
An array is a container that stores the values of a similar data type. The
storage process deals with entering the values at any index of the array, and
the index of the array accesses that value. Whenever you declare an array, you
have two options. Either assign the values at the time of declaration or enter
the values when they are needed dynamically. In this guide, we have experienced
both approaches. To perform this function in bash, you need to create an
environment of the Linux operating system where you can access the terminal and
other applications of user privileges.
To perform operations on array in bash, you need to install bash on Linux
operating system. By installing the packages, it is already installed in the
system. The version of bash should be greater than 4 to continue this guide
further. If it is less than 4, you need to install the latest bash version or
at least 4. Execute the command on the Linux terminal to check the version.
$ bash --version
From the result, you will see that the bash version is 5.0.17. It means we can
perform operations on an array using bash.

Example 1

To declare an empty array, the simplest method is given here. It contains the
keyword “declare” following a constant “-a” and the array name. The name of the
array is assigned with empty parenthesis. Run this command on the terminal.
$ declare –a array2=()
This is how an empty array is declared using a single command. Mostly the empty
arrays are not considered valuable because they don’t bear any value, just
occupy the space, especially when you define the size of an array during
declaration or dynamically at the run time.

Example 2

After the declaration of an empty array, you can now assure that there is no
item there. Declare the array using the method mentioned in the first example.
$ declare –a arr1
Now you can check the array by taking the print of the array. The print is done
by taking the index number. There is no value. To print all the array values,
we use the ‘@’ or ‘*’ sign instead of the index number.
$ printf ${#arr1[@]}
“#” implies the number of values in the specific index. If you want to display
the value directly, there is no need to use the hash sign with the array’s
name.

Example 3

In this example, we have to use the if-else statement to apply the condition on
the array. Array creation is done first. It is a different method of array
creation.
$ array=()
Unlike the previous examples, we have not used the “declare” keyword to create
and initialize the array. This method is quite easy as the name of an array is
directly assigned to the empty parenthesis. This means no value is assigned.
Now check the array through the if-else statement. Here only the “if” part is
used; you can also use the “else” part of the statement.
$ if ! (( ${#array[@]} > 0)); then echo “array is empty”; fi
The whole statement is written in a single line. It represents that if the
index is on the 0 indexes, an array is empty. So the respective message is
displayed, which is that “array is empty”.

Example 4

Again there is a use of the if-else statement. But this time, we have utilized
both parts in the statement. The ‘if’ part will work only if the array is
empty, but if it is full or has some value, then the part will display it. An
array named “errors”. We have temporarily filled this array to check the
working. Now we will use the statement. Here ‘eq’ is utilized as an equal sign.
$ if [ ${#errors[@]} -eq 0 ];
This statement will determine if the array index is at 0, so it means the array
is empty.
Echo “no errors detected”

Echo “Errors are founded: ${#errors[@]}”
Else part shows the number of elements in the array showing that the array is
not empty. So it is a single element as three words are treated as individual
because of the double-quotes.

Example 5

In the previous example, we have used “printf” to print the elements of the
array. The “echo” command is used instead of the print command. Consider an
array that is declared through the “declare” keyword
$ declare –a array=()
In this example, we have assigned the space to the first index of the array.
$ array[0]= ‘  ’
To check the value at that index in the array, we will echo the value. This
time we don’t want to get the number; we want to check the value only.
$ echo ${array[0]}
This time, the index number is used directly in the command instead of any
variable. Run the respective command. From the output, you will see that a
space is shown. The user may think that the array is empty. But it is not. So
we will check the number of elements present inside the array at the ‘0’ index.
This will be accomplished by using the ‘hash’ sign in the command
$ echo ${#array[0]}
So it is confirmed that the ‘1’ element is present in the array. Similarly,
there is another similar example if the user is not sure that he has filled the
array index or not. He may check it by using the command of echo
$ echo ${array2[1]}
The result is blank space. Every blank time-space does not mean that it is a
space character.
$ echo ${#array2[1]}
The answer is ‘0’, which implies an empty array. Now we perform the same
procedure as discussed above. Assign the array with space and then check the
number; it will show ‘1’.
So it is proved that every time the blank space in the result of a command does
not means it is the ‘space’ character.

Example 6

If you already have a value in the array, either it is full or has elements on
the specific index, and you want to remove all the elements to keep the array
empty. Now fabricate the term ‘unset’. In bash, this will remove all the
elements of the array and will declare the respective array empty.
$ unset array2[@]
After that, you can check the value through the command.

Example 7

In the last example, we will display the way of adding values to the array. Yet
this is not the first time, but it is another way of doing so.
$ array2 +=(item1)

Conclusion

It is considered preferable to declare the array empty at the time of creation
because it helps to reduce redundancy in the future. To keep the values
coherent, you need to fill the array dynamically. This article is a complete
guide to declare the array empty both at the initialization and hereafter,
depending upon the usage.


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
