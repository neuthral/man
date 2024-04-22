





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How do I compare numbers in bash?

1 year ago
by Aqsa_Yasin
A user may want to write a code to do a certain job in a variety of
circumstances. On the other hand, one might wish to run this computer code
again for some monotonous activities. For example, some numerical numbers must
be compared repeatedly. Here’s when the operators come in useful. When doing a
contrast within a bash script, comparison operators come in handy. The
comparison is typically done within the code’s if-else clause. We’ll be
comparing two integers or numerical values the majority of the time. Hence,
this guide is meant for those who want to explore how different comparison
operators can be utilized for comparisons within numbers in bash language.

Example 01: Equal & Not Equal Operator

Comparing the two or even more integers is among the most popular assessment
methods. We’ll now write a program to compare numeric numbers. Firstly, we’ll
need to understand the factors which are employed to contrast integer data. So
the very first operator to compare two integer type numbers or variables is the
“equal to” operator in bash. After login, you need to open the terminal to
start making bash files and creating code by “Ctrl+Alt+T”. Now the shell is
opened, we need to create a bash file with the help of the instruction below.
$ touch test.sh
Open the file in an editor, e.g., GNU Nano Editor. For that, try out the simple
mentioned command as:
$ nano test.sh
The code below should be written in your bash file. Save it by the “Ctrl+S”
key. First, we have added the bash extension in the file to make it executable.
After that, we have initialized two integer-type variables with different
values. You can take the same or different values as per your choice. Then we
have initialized the “if” statement to contrast the two variables by an
operator “-eq”. This will check whether the two variables are equal or not. If
the two variables are equal, it will show the message displayed within the
first echo phrase. Otherwise, it may print the second echo phrase.
Quit the bash file by “Ctrl+X” to move back towards the shell. Now, to run the
bash script, write the below-stated query in your console and hit Enter. The
two variables, v1 and v2, got different values in the script; hence it executes
the second echo statement saying that “Numbers are not equal”.
$ bash test.sh
Open the same bash script file once more to update the code. This time we have
updated the values of both the variables and make the same. After saving the
code, we had to quit it with “Ctrl+S” and “Ctrl+X” one after another.
When we ran the same updated file, it displays “Numbers are equal” in return
for executing the first echo statement. This is because both the variables are
the same in this case.
$ bash test.sh
This example will be elaborating the functioning of the “not equal” operator
used within the bash script to compare two numbers. To look at that, open the
test.sh bash file in the editor to edit it per our requirement using the query
stated below.
$ nano test.sh
We have updated the file with two different variables of integer types. Within
the “if” statement, we have utilized the “not equal” operator “-ne” to see if
both variables are not equal to each other. If the condition satisfies, it will
print the message “Numbers are not equal” as per the first echo clause. On the
other hand, if the situation is not satisfied, the message “Numbers are equal”
will be displayed per the second echo statement. Now save your bash updated
code and leave the editor.
When you test your code by a bash command stated below, it will display the
message “Numbers are not equal” by satisfying the condition of not equal in the
“if” statement.
$ bash test.sh

Example 02: Greater Than & Less Than Operator

Other than equal to and not equal to operators, we have greater than and less
than operators as well in the bash to compare integer or numbers. To see those,
let’s begin with opening a bash script file in any of the editors.
$ nano test.sh
In the below code, we have declared two variables. Within the “if” statement,
we have used “-gt,” e.g., greater than operator to compare two variables. This
will check if the first variable is greater than the second or not. According
to the condition satisfaction, it will execute the else part of the “if”
clause. Quit this editor after saving the code another time.
When we had executed this bash script, It displays that the variable v2, e.g.,
9 is greater. This compares both values and found that the first variable is
smaller than the second one. Hence, the output was as per the below image.
$ bash test.sh
Let’s update our code to see how it works with the value provided within the
“if” clause. So, we have added 66 to compare it with the variable value v1=15.
As the 15 is less than 66, it must display and execute the second echo
statement. Let’s have a look at the output after saving the code.
The output is as expected. It displayed the second echo clause because the
situation doesn’t meet its requirements.
$ bash test.sh
Let’s update our code with less than an operator to see the working of the bash
script. So, after opening the file with nano instructions, you have to update
your code as below. We have replaced “-gt” with “-lt,” representing the “less
than” operator. Also, you need to update the echo messages as well to meet the
required needs. Make sure to take two different variables this time to see if
they are less or greater than each other. Save the code and execute it.
The execution shows the output as “v2 is less than v1” because 47 is greater
than 37.
$ bash test.sh

Example 03: Greater than or Equal & Less than or Equal Operator

This time we will be using an emerged sort of operator to perform two
operations in one way. Let’s look at the greater than or equal to the operator
first. Replace the “-lt” with “-ge,” which represents the “greater than or
equal to” function here.
The variable v1, e.g. 47 is not greater than or equal to 49, displayed the
second echo statement.
$ bash test.sh
To check if the one variable is less than or equal to the other one, we will be
replacing “-ge” with “-le”. Make sure to update the echo messages as well. This
time it must execute the second echo statement. You have to save your code and
quit the file once again.
Upon execution, it turns out as expected. It displayed the second echo message.
$ bash test.sh

Conclusion:

So, within various shell scripts, the comparison of numbers is very useful and
necessary. We have discussed all the possible operators to be used for
comparisons in bash within this guide. We believe these methods for comparisons
will be useful.


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
