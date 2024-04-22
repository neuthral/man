





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Simulate an Array of Arrays in Bash

2 years ago
by Aqsa_Yasin
Bash is indeed an interpreted, interactive language, and how much space to
reserve in advance does not have to be known. It is also possible to make ready
a new array dynamically without declaring it or extending a previously defined
array to include further entries. Still, multidimensional arrays aren’t
supported by bash, and we can’t get array components that are also arrays.
Fortunately, multidimensional arrays can be simulated. This article will
provide some illustrations of the simulation of an array of arrays in a bash
script.

Example 01: Using Simple “For” Loops

We have an example of simulating an array of arrays using the simple method.
Let’s start demonstrating how to load a user-defined m x n table with random
numbers (that aren’t random, because each column will at all times have a
similar number in each run on most of its rows, but that does not apply to the
question), and print it. When we work on either a bash that you do have, bash
version 4, the below script would certainly work efficiently. We should not
solitary declare 0; that is more like a perfect solution to values being
accepted vigorously. We have declared an array with the “-A” keyword.  If we
don’t define the associative array using -A, the code may not work for us. The
read keyword is then used to read the user’s input, which is rows and columns
of a table. Then we have used two “for” loops for the incrementation of rows
and columns of a table. In for loop, we have been making a two-dimensional
array. In the next for loop, all the values of an array have been displayed.
When you run the bash file, it will ask a user to enter rows and columns as “m”
and “n”. After that, for loops will generate a two-dimensional table as below.

Example 02: Using Hashes

Taking the same instance, we can emulate the arrays using hashes. However, we
have to be more careful about leading zeros and several other stuff. The next
explanation is working. However, the way out is very far from ideal. We have
been taking rows and columns manually. For loop is used to make a matrix. Then
we have been using hashes to emulate the two-dimensional array. At last, the
array will be printed out as below.
Execute the file “input.sh” in the bash shell using the bash command. You will
find a table with rows and columns number mentioned.

Example 03: Using Associative Arrays

Let’s have an example of simulation having a somewhat similar effect using the
associative arrays used as an array of arrays as below. After the declaration
of the associative array, we have defined values for arrays separately. After
that, we have made it to print out the values in two dimensional way.
You can see the output as a two-dimensional array while running the file. If we
ignore the “declare -A arr” line, the echo statement may display (2 3) rather
than (0 1), since (0,0), (1,0), and others may have been used as a mathematical
expression and calculated to 0 (the value at the right side of a comma).

Example 04: Using Name-references

In bash, it is a frequent issue with referencing arrays inside arrays that
you’ll have to construct name-references using declare -n. That name afterward
-n serves as a name ref for the value allocated (after =). Currently, we handle
this variable only with attribute name ref to extend as though it was an array
and extend the appropriately cited array as beforehand. Let’s have an example
of name refs. We have successfully declared two arrays. After that, we have
assigned both the arrays to another array as a member. We have used for loop to
make a two-dimensional array. We have made another variable to add the one-by-
one values of the array “group” into it for comparison. Deep down, it will go
to members of inner arrays “bar” and “foo” to take values and compare them
while printing the message.
When we execute the file “input.sh”, you will see the below output. The
variable “lst” has values of inner arrays within the array “groups”.

Example 05:  Using Cut Keyword

Only now, I’ve stumbled into it. There had been a fairly straightforward
approach that worked for everyone. To show a main map for the system, I decided
to use an array containing a device name and a screen location. We have to
concatenate the title of the unit and the corresponding location of a display
into some single string, using only a delimiter, which we assumed will not
occur in either of our values (in my case, I used .). And I used a “cut”
keyword to split the concrete values into their components if necessary. There
may be a clearer and easier approach to do it, though, and this is only to
illustrate that in a sense, in bash, we can build a multidimensional array,
although it does not help it. After that, you have to print both the device
name and its location separately after creating the substring.
Let’s run the bash “input.sh” file. You will see the separated device and its
location in the shell prompt as while execution. The solution works using the
cut command.

Example 06

Let’s take a little longer example to emulate a multidimensional array. In the
load_alpha() function, all the alphabets will be loaded into the array. After
that, the print_Alpha() function is declared and used to print out all the
alphabets in the row-major order as a matrix or two-dimensional format. On the
other hand, we have been using the rotate() function to rotate the array. Let’s
try this example in the bash shell to see results.
While execution, we have found a very beautiful structure of multidimensional
array in the bash shell as below

Conclusion

We have successfully tried some examples for simulating arrays of arrays in
bash. I hope it works!


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
