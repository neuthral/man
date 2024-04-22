





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Write Bash If/Else Statements in One Line

2 years ago
by Aqsa_Yasin
Bash is a flexible programming language that allows you to write programs just
the way you like. Before getting into the article, we would first like to share
with you a good programming practice. Whenever you write a program in any
programming language, the readability of the code should always be your
priority. This is because your code is not only used by yourself but there will
be many other programmers who will be using and reading your code. Therefore,
your code should be readable enough to be understood by everyone.
Today’s article introduces you to the concept of one-line programming. Bash
allows you to write components, such as loops or conditional statements, in one
line. You might wonder why we should consider writing these components in one
line when we have just explained to you the concept of readability. To
understand this, consider the following scenario: you have a program spanning a
thousand lines. Such a lengthy code would be difficult to visualize, as well as
to debug. In this situation, if your code contains many different loops and
conditional statements, then it would improve the readability of the code to
write several statements in one line to make your code look more compact.
The following tutorial shows you how to write Bash if/else statements in one
line in Linux Mint 20 by providing several examples of these statements.

Methods for Writing Bash If/Else Statements in One Line

To learn more about writing Bash if/else statements in one line in Linux Mint
20, examine the following example Bash scripts:

Example 1: Comparing Two Strings in One Line

In the first example, we will write a Bash script that will compare two strings
in one line. To achieve this functionality, write the Bash script shown in the
image below in a Bash file:
We will compare two pre-defined strings in the “if” part of the statement, and
a message will be displayed if this part is executed. Then, the “else” part of
the statement will also display a message if it is executed.
To run this Bash script, we will use the following command:
$ bash OneLiner.sh
Since both strings were equal, the “if” statement will be executed. We will
obtain the message shown below upon execution of this script:
Now, we will tweak our Bash script a bit by changing one of the strings, as
shown in the following image:
After making this change, when we execute our Bash script again, the “else”
statement will be executed, and we will get the message shown in the image
below:

Example 2: Comparing a Variable with an Integer in One Line

Now, we will write a Bash script that will compare a variable with an integer
in one line. To achieve this functionality, write the Bash script shown in the
image below in a Bash file:
We will create a variable named “var” and assign it the value “20.” Then, we
will compare the value of this variable with an integer “25” for equality in
the “if” part of the statement. A message will be displayed if this part is
executed. Then, the “else” part of the statement will also display a message if
it is executed.
Since the value of the variable “var” was not equal to “25,” the “else”
statement will be executed. We will obtain the message shown below upon
execution of this script:
Now, we will tweak our Bash script a bit by changing the value of our variable
“var” and setting it to “25,” as shown in the following image:
After making this change, when we execute our Bash script again, the “if”
statement will be executed. We will obtain the following message upon execution
of this script:

Example 3: Comparing Two Variables in One Line

Finally, we will write a Bash script that will compare two integer variables in
one line. To achieve this functionality, write the Bash script shown in the
image below in a Bash file:
We have created the two variables “var1” and “var2” and assigned them the
values “25” and “20,” respectively. Then, the values of these variables will be
compared for equality in the “if” part of the statement, and a message will be
displayed if this part is executed. Then, the “else” part of the statement will
also display a message if it is executed.
Since the value of “var1” was not equal to the value of “var2,” the “else”
statement will be executed. We will obtain the following message upon execution
of this script:
Now, we will tweak our Bash script a bit by changing the value of our “var2” to
“25” so that the values of both the variables become equal, as shown in the
following image:
After making this change, when we execute our Bash script again, the “if”
statement will be executed. We will obtain the following message upon execution
of this script:

Conclusion

This article provided three different examples and their slight variations for
writing if/else statement in Bash in Linux. This tutorial showed you how to use
conditional statements in Bash all contained within a single line, making your
code look more compact and readable.


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
