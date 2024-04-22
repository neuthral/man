





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Variable Name Rules: Legal and Illegal

2 years ago
by Aqsa_Yasin
A variable is a storage space having a particular name that holds a certain
value in it. You might have been working with a lot of programming languages
and have a good perspective of variables. However, in the bash programming, it
is slightly different. In this guide, we will learn about the rules invariable
naming and execute some examples to declare a variable in a bash shell and
observe its effect whether, it is valid or invalid, e.g., legal or illegal.

Legal Rules of Naming Variables in Bash


* The variable name must be in the upper case as it is considered good practice
  in bash scripting.
* Insert the dollar sign “$” before the variable name.
* Don’t use spaces after the initialization of the variable name and its value.
* A variable name can have letter/s.
* A variable name can have numbers, underscores, and digits.


Illegal Rules of Name Variables in Bash


* The variable name having lower case letters.
* No dollar sign “$” inserted while printing it.
* Adding spaces after the initialization of the variable name and its value.
* Start the variable name with number, digit, or special symbols.
* The variable name having space in it.
* Use of keywords to name the variables, e.g., if, else, for, while, int,
  float, etc.


Example 01: Lower/Upper Case and Dollar Sign

Open your terminal and create a variable with an upper case. Print this
variable using the statement “echo”, with and without dollar signs. Notice that
with the “$” sign, it will display the value, otherwise, it will only display
the variable name.

Example 02: Spaces after Variable Name and Equal Sign

Open your terminal and create a bash file named “variable.sh” using the touch
command.
Open this file from the Home Directory and write the code as shown below. You
can see that there are spaces after the variable name and equal sign, which is
incorrect. On the other hand, a variable is not printed out without a dollar
sign in the echo statement.
In the terminal, execute the bash command to run the file “variable.sh”. You
will see that there is an error because of the invalid usage of rules.
Let’s correct the same code, with the dollar sign in the echo statement and no
spaces in the variable name. Save and close it.
Again, running the file using the bash command, you can see that we have a
valid output now.
You can also attempt it in a bash shell. Let’s take a variable with spaces
before and after the equal sign. It will display an error, as shown below:
When you remove the spaces before and after the equal sign, it will be executed
successfully. On the other hand, in bash, the variables are syntax sensitive,
so make sure to run the correct variable. As you can see, when we print the
lowercase variable, it will display its value, and on the usage of the
uppercase variable, it will display nothing.

Example 03: Spaces in Variable Name

Let’s take the variable “ROLL NO” with spaces in between. It will display an
error, as shown below. This means that the variable’s name cannot contain
spaces.
When you remove the space, you can see it works correctly while using the echo
statement and displays the value.

Example 04: Digits/Numbers in Variable Name

Let’s take a variable starting with some digit or number. As observed, it will
display an error. This means that the variable name cannot have a number at the
start. When you add a number in the middle or at the end of the variable, it
will work correctly, as shown below. While using an echo statement, it will
display the value of a variable name containing a number.
Take another example of using digit and number together. Declare a variable in
the file “variable.sh” and print it out in the echo statement.
The bash command implies running the code. We will get an error due to the
usage of digits and numbers at the start.
While correcting the variable, add the digit and number at the end of it and
print it in an echo statement.
After doing so, it will work successfully and print the value of a variable.

Example 05: Special Characters in Variable Name

None of the special characters can be used in naming variables, e.g., asterisk,
question mark, greater than, less than, hash, exclamation marks, etc. Let’s
take an asterisk as an example. Even though we put it before, after, or in the
middle of the name of a variable, it will cause an error generation. This means
that no special character can be used in the variable name before, after, and
in between.

Example 06: Underscore in Variable Name

The underscore can be used in naming variables before, after, and in between.
Let’s have an example. While trying it before, after, and between the name of a
variable, it will cause an error generation. This means that no special
character can be used in the variable name before, after, and in between
In the bash file, we have declared a variable with an underscore in between the
variable name. The echo statement has been used to print the variable.
Run the bash file using the bash command. You can see that the value has been
printed out in the terminal correctly.

Example 07: Concatenate Variable with String

Let’s have an example of concatenating the variable with the string in the echo
statement using the curly braces. Open the “variable.sh” and write the appended
code in it. You can see that we have defined two variables. There is a new
variable “WORK”. In the echo statement, we have a string text and a variable
“WORK” within the curly brackets, then combined it with the text “ing”. Save
and close it.
When you use the bash command to execute the “variable.sh” file in the command
shell, we can see that the variable and string text has been concatenated
successfully, and it displays: “The best job is Teaching”.

Conclusion

We have learned most of the variable naming rules for Bash scripting.
Hopefully, you will be able to deal with naming variables within the rules.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
