





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Pad String with Spaces

6 months ago
by Karim_Buzdar
While displaying the text as the output of a program, you might have certain
requirements regarding on how the text should appear, such as its spacing,
alignment, etc. There are certain ways of achieving the desired formatting of
the output in programming. In this article, we will focus more on the method of
padding a string with spaces in Bash in Linux Mint 20.3.

How to Pad a String with Spaces in Bash in Linux Mint 20.3?

We designed the following script to demonstrate the method of padding a string
with spaces in Bash:
Our goal is to generate and print five random numbers in a certain format with
padded spaces. For that, we created a file in our home directory named
“Space.sh” and included Shebang (#!/bin/bash) in this file. Then, we used a
“for” loop to print these five numbers on the console. Within this loop, we
inserted a “do-done” block. Inside this block, we used the “$Random” function
of Bash to generate random numbers. We printed the generated numbers followed
by five spaces and a message display “Number Generated”. Then, we used another
“printf” statement to print all the five random numbers in a separate line.
To run this Bash script, we executed the following command in our terminal:
$ bash Space.sh
The output of this Bash script is shown in the image below:
To exceed the padded spaces, increase the number of spaces in the same Bash
script as shown in the following image:
We want to pad our desired string with 7 spaces in this Bash script.
You can compare the outputs of both Bash scripts in the following image:
Similarly, if you want to pad 10 spaces to your desired string, make use of the
following Bash script:
The following image displays the output of all three Bash scripts in the order
of increasing padded spaces:

Conclusion

You can easily pad your desired strings with the required number of spaces by
following the prescribed method. This way, you can properly format your text or
output. More related articles are available on the website for more tips and
tutorials.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
