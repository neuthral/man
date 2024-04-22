





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Create a Bash Function that Returns an Array

2 years ago
by Aqsa_Yasin
It may appear at first glimpse that returning an array from a Bash function is
not realistic. Considering all the benefits, it can be useful to call multiple
methods to construct arrays to split up the process of gathering all the
appropriate parameters for a YAD call.
There are many reasons why one might want to restore a BASH array:

* Managing the lifespan of arrays is simpler because they are assigned locally.
* For just-in-time attainment, obtaining arrays from methods may help.
* To support log algorithm techniques, the names of methods that return arrays
  may be cast off.

You may believe that Bash loses the capability to return function arrays.
However, that is not exactly correct. It is possible to move the resultant
array to a method by reference, taking cues from C/C++ developers. Such a
strategy allows the method to continue to be free from references towards a
global variable. The following article shows clear instances of this case.

Example 1: Returning an Array

Log into your Linux system and open the command terminal to proceed. We will
create a Bash file named “script.sh” using the touch command to return the
array using the Bash function. The script is as follows:
$ touch script.sh
You can view the newly created file in the Home directory. Open this file and
write down the appended code into it as-is. Here, we are attempting to create
an associative array through an argument in a method from either a list pass.
Initially, we have created the function foo().
Inside this program, we have removed the “declare” term, which is a Bash pre-
configured command that allows us to change or customize the attributes, the
methods of the shell smeared to the variables, and demonstrate the values of
these attributes inside the span of our shell command terminal. Moreover, it
can be used to define a lengthy variable. Lastly, it is used to define the
variables.
We have added the “fooval” value to the “arr” array.
The keyword “–A “is used to create the NAMEs associative array if supported. We
must use the list/array as a global variable, which implies that only a method,
not a script, can perform this action.
We have also created another array, named “myarr,” for use as a reference. Bash
allows the name of a relative variable arr to be dissimilar to the name of the
relative variable myarr.
After that, in the eighth line, we have passed the “myarr” array to the Bash
foo() function as a reference.
In the past, we used the “for” loop to print both the “arr” and “myarr” arrays
to the foo() function.
We will now check the result of this code. Execute the Bash command to run the
above code. You can see that the array has been returned to the function and
then printed.
$ bash script.sh

Example 2: Returning another Array

Let us look at another example of returning arrays to a function. Open your
command terminal and create a new file named “openvpn.log” using the touch
command, as follows:
$ touch openvpn.log
Now, open the “openvpn.log” file, and write the following text into this file,
as shown. Save this file and close it.
Again, open the command shell and create another file named “script.sh,” using
the touch command to add the Bash script to the file.
$ touch script.sh
Next, open the “script.sh” file and append the following code into this file
as-is. Save and close this file. This script will use a method that reads
values/strings from a document and returns an array:

* Declaring the array: clients
* Allocate the returned array of the method to array clients
* Show array: clients

Let us now have a detailed look at the working of this script.

* We have declared a global array of “clients” using the “declare” keyword,
  followed by “-A.”
* The readArray() function has been defined. In this function, we have declared
  some local variables. The local variable “array” is empty, but “i” and “j”
  have been defined with the 0 value to be used as iterators.
* Using the read mode, we will read the text from the file using iterators to
  increment the indexes.
* The line “clients[$((i++))]+=${LINE};” is used to append the text lines to
  the globally defined “clients” array variable.
* After that, “j++” is jumping on the next index.
* The variable “$1” is used to save and return the array that was just created
  from the “openvpn.log” text file.
* On the outside of the function, the string has been declared as “$string” and
  has been given a file path as a value.
* This string has been passed to the readArray function as a reference to read
  text from this file.
* After that, the “clients” array has been printed, and the entire text within
  it has been displayed in one line.
* Now, we will display a message that the array is no longer empty.
* The “for” loop has been used to convert the contents of the “clients” array
  into the array type and declare an index for the contents using the statement
  “echo “$i: ${clients[$i]}.”
* Finally, we displayed a message and printed some converted array values
  separately as a single indexed position of an array.

Let us now check the output of this Bash script. Run the Bash command to
execute the “script.sh” file. As you can see, the first echo statement will
print all the text from the “openvpn.log” file, which has been saved in the
“clients” array as one line. The second echo statement will display the string
message. The third echo statement will display the “clients” array in indexed
form, as it has just been converted. The fourth one will display a message
again. The final one will display the contents of the “clients” array
individually.

Conclusion

This article showed you how to return arrays (especially associative arrays) to
a function using the “declare” built-in command with two examples. I hope that
this article helped you to better understand this topic.


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
