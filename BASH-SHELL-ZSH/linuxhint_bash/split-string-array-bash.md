





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Split String into Array

1 year ago
by Omar_Farooq
You may find yourself in many situations where you have to split string values
into arrays or other data structures while working on a bash script in a Linux
system. Here, you have to clear that bash doesn’t provide us with the built-in
split function to split any string. But there is always an alternative to such
problems. Hence, we will be using the delimiters to convert or split some
strings into an array. Let’s start looking at some examples within Ubuntu
20.04. Open the shell terminal first using the “Ctrl+Alt+T” on the desktop.

Example 01

We have declared an “str” variable in the shell with a string value in it.
Here, we used the “IFS” variable as a delimiter to split a string “str”. The
delimiter “IFS” contains “space” as its value. This means the string will split
into an array using the space between its values. Now, the “for” loop is used
here to iterate the string “str”. Within the “do” clause, each element of an
“str” variable will be displayed as an array. After the loop ends, the terminal
displays the string in an array form as per the image below.

Example 02

Let’s have another example to get a little different output. You can see
clearly that the string contains “,” character after every word in it. This
special character will be used as a delimiter. So, we have declared “,” as a
value to the “IFS” variable.
]The “for” loop has been initialized here again to iterate the string variable
“str”. Within the “do” clause of the “for” loop, the echo statement has been
used to display each word separately with the index number as separated by the
“IFS” variable value. After the loop ends, the program displays each word of
string separately in the form of an array. The character “,” is responsible for
this kind of split between string values. As a result, we have got 5 values in
the form of an array from a single string variable “str”.

Example 03

Let’s have another example of splitting a string to an array within the bash
file. So, you have to create a bash file “test.sh” with a touch query in the
shell, as mentioned below.
$ touch test.sh
Now, open the newly created file in an editor to write a bash script in it. We
have been utilizing the “GNU Nano” editor for this purpose. You can utilize the
vim editor as well.
$ nano test.sh
Within the bash file, we have added the bash extension first to make this code
executable with the bash command in the shell. After that, a variable “str” has
been declared and initialized with a long string value in it. The “IFS”
variable has been declared and assigned with a value “space”. The read
statement has been used here to read the data from a string variable “str” as
an array with the help of the “-ra” flag and saved to the new variable “Arr”.
The echo statement calculates and displays the size of an “Arr” variable, i.e.,
array. The “for” loop is here to iterate the values of array values, i.e.,
“Arr” in a sequence and displayed within the shell using the printf statement.
The program ends here. Save your code with the “Ctrl+S” and quit the editor
using the “Ctrl+X” shortcut.
Run your newly created bash script with the bash command along with the name of
a bash file, i.e., “test.sh”. The execution of the bash script first shows the
size of a string “str” i.e., Array. After that, the terminal displayed the
values of a string variable in the form of an array, i.e., each word separated.
A total of 9 words have been displayed on the shell, as shown below.
$ bash test.sh

Example 04

Let’s make another illustration to split a string into an array. So, open the
same code file and update the string variable “str”. We have added 6 words in
the string separated by a comma. This comma will be used as a delimiter in the
“IFS” variable. The read statement has been reading the words of a string “str”
as an array separately and saving each one of them to a variable “Arr”. The
delimiter works here and separates each word from a string.
The 6 echo statements have been used here to display every value of the “Arr”
variable using the indexes of words. You can see the syntax for taking every
value by index in the shown image.
After running the code in the shell with the help of a bash query, we have got
6 lines of output. Every word of a string is separately saved into the array
variable “Arr” and displayed with the help of indexes.
$ bash test.sh

Example 05

Let’s have our last example of splitting a string value into an array. This
time, we are not using the “IFS” variable as a delimiter to split a string. We
will use the “tr” flag to do so. So, open the file “test.sh” in a Nano editor
to update it. Add the bash extension at the first line.
The string type variable “str” has been initialized.  Another variable, “Arr”
has been using the variable “str” value and splitting it into parts by using
the “tr” flag. The “tr” delimiter contains space as its value. The “for” loop
is iterating the variable “Arr” values with the help of indexes. Every value
will be displayed separately in the form of an array.
After running the bash code, we have got the result in an array form. Every
word in a string “str” is separated and converted into an independent value,
i.e., Array element.
$ bash test.sh

Conclusion

In this article, we have discussed several examples to split a string value
into an array. For this purpose, we have used the delimiter “IFS” variable and
“tr” methods. All the examples are quite easy to understand and can be
implemented without any issue.


About the author


Omar Farooq

Hello Readers, I am Omar and I have been writing technical articles from last
decade. You can check out my writing pieces.
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
