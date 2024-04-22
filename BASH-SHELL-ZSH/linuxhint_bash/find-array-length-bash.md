





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Find Array Length in Bash

1 year ago
by Aqsa_Yasin
Arrays are an excellent means of storing a large number of data values that
belong to the same data type. They are used very extensively in all the
programming languages out there. Arrays can have varying sizes depending upon
the needs of the programmer. Moreover, they can either be static or dynamic.
Static arrays are the ones whose sizes are predefined, whereas the sizes of the
dynamic arrays are defined at the runtime. However, there are multiple programs
whose entire logic depends upon finding the size or length of an array.
Therefore, there must be a way through which we can get the exact size or
length of an array so that we can write efficient programs with the help of it.
Just like other programming languages, Bash also allows you to create arrays
and play around with them. Additionally, you can perform all those operations
with arrays in Bash as you can do with any other programming language. In this
tutorial, we wish to teach you the methods of finding the array length in Bash
on a Ubuntu 20.04 system.

Method of Finding the Array Length in Bash in Ubuntu 20.04

To find the array length in Bash, you can make use of different notations.
However, to get a better idea of using those notations, you can take a look at
the following three examples. The first two examples are based on the basic
usage of the two different notations through which you can find the array
length in Bash whereas the third example will make practical use of this array
length in a Bash script.

Example # 1: Finding the Array Length with the $#@ Special Variable in Bash

For using the $#@ notation for finding the array length in Bash, we have
written the Bash script shown in the image below:
In this Bash script, we have declared an array with the name “names” and
assigned to it three string values i.e. Aqsa, Ahmed, and Ayesha. After that, we
have created a variable named “len”. We wanted this variable to hold the length
of the names array. We have assigned the length of our names array to this
variable using the $#@ notation. Then we have an echo command to print a
message on the terminal. Finally, we have another echo command that will print
the value of the “len” variable i.e. the length of our names array.
Now, we will run this Bash script with the following command after saving it:
$ bash Length.sh
In this command, Length.sh is the name of our Bash script file. You can
substitute it with the name of the Bash script file that you will create.
When this script will be executed properly, you will see the array length of
the names array on the terminal as shown in the image below:
It means that the $#@ notation has correctly printed the length of our names
array i.e. 3.

Example # 2: Finding the Array Length with the $#* Special Variable in Bash:

In this example, we have the same script that we used for our first example.
The only difference is that in this script, we have used the $#* notation for
finding the array length in Bash instead of the $#@ notation. The $#* and $#@
notations in Bash are mostly used interchangeably since they both serve the
very same purpose. Our example Bash script for this modification is shown in
the following image:
In the Bash script shown in the image above, we have just replaced “@” with “*”
in line # 3 of our script. The rest of the script is precisely identical to
that of our first example.
Now, we will execute this slightly modified Bash script with the very same
command that we shared with you in our first example. When we executed this
Bash script, our output turned out to be the same as that of our first example.
You can confirm this from the image that we have attached below.
It means that the $#* notation also printed the length of our names array
correctly which in turn implies that the $#@ and $#* notations can be used
interchangeably for serving the same purposes.

Example # 3: Using the Array Length as the For Loop Condition in Bash:

Now, this example is slightly complex than the first two examples. Here, we
would like to mention that you can use any of the two notations from $#@ and
$#* for writing this Bash script. You will have to write a Bash script similar
to the one shown in the following image for executing this example:
In this script, we have simply declared an array of “names” and assigned it
three values i.e. Aqsa, Ahmed, and Ayesha. After that, we have declared a
variable named “len” and assigned to it the length of our names array while
using the $#* notation. Then we have printed the value of the “len” variable on
the terminal i.e. the length of our names array. Until now, this Bash script
looked like the scripts that we have used for our first two examples. But from
here onwards, this script contains some additional pieces of code.
We wanted to print the elements of this array on the terminal. For that, we
have a “for loop” which iterates through the variable “i” and the terminating
condition of this loop depends upon the length of our names array, or in other
words, it depends on the value of the “len” variable which in our case was 3.
It means that our “for loop” will have a total of three iterations. Within this
“for loop,” we have just tried to print the values of all the indexes of our
names array.
After saving this Bash script, we executed it using the same command that we
shared with you in our first example. Upon execution, this script first printed
the value of the “len” variable or the length of our names array i.e. 3. After
that, this script also printed all the elements of the names array on the
terminal as you can see from the image shown below:
This was just basic usage of the length of an array in Bash. However, using
these notations, you can create even more complex examples.

Conclusion

In this article, we shared with you the two different notations with which you
can find out the length of an array in Bash in Ubuntu 20.04 very easily. These
notations were $#@ and $#*. Both of these notations work in the same manner
which is why they can be used interchangeably. After sharing with you the basic
usage of these two notations, we shared with you a relatively complex example
that makes use of the length of an array which was found while making use of
one of these two notations. Now, when you have learned the methods of finding
the length of an array in Bash in Ubuntu 20.04, it will no longer be a problem
for you to write Bash programs that entirely depend upon the lengths or sizes
of the arrays used in those programs.


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
