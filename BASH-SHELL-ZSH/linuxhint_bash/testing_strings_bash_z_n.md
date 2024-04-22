





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash “if –z” and “if –n” for Testing Strings

2 years ago
by Aqsa_Yasin
The “if” statement in Bash can be used with different parameters to serve
multiple purposes. Whenever we are working with strings in Bash, it is very
important for us to check if a string is null or not so that it cannot cause
any problem in the execution of our program. Both the “-z” and “-n” flags can
be used with the “if” statement to test the strings, and we will explain to you
how this can be done in today’s article.
Note: Linux Mint 20 is used to test the following examples.

Method of Using Bash “if –z” and “if –n” for Testing Strings

To explain the usage of Bash “if –z” and “if –n” for testing strings, we would
like to share with you the following example scenarios.

Example # 1: Using “if –n” to Show that a String is Null

For showing that a string in Bash is null using the “if –n” statement, we will
perform the following steps:
First, we will create a Bash file in our Home directory named Strings.sh, as
shown in the image below:
After creating this file, we will type the script shown in the following image
in our file. Like every Bash script, the first line, i.e. “#!/bin/bash,” is
mandatory. Then we have declared a null string named “name”. A null string in
Bash can be declared by equalizing a variable to “”. Then we have an “if”
statement followed by the “-n” flag, which returns true if a string is not
null. We have used this flag to test our string “name,” which is null. It means
that the “if” condition will not be executed since the value of the “-n” flag
will be false in this case. Therefore, we also have an “else” part that will be
executed by printing a message on the terminal.
Now it is time to execute this file, which can be done with the command shown
below:
$ bash Strings.sh
Since the string that we declared was null, that is why the “else” part of our
script has been executed, and the corresponding message has been printed on the
terminal as shown in the following image:

Example # 2: Using “if –n” to Show that a String is not Null

For showing that a string in Bash is not null using the “if –n” statement, we
will perform the following steps:
We will type the following script in our Bash file. The only change that we
have made to the script that we created above for this scenario is that this
time, we have assigned the “name” string a valid name. It means that our string
is not null this time, which implies that the “if” part of the script should be
executed.
Now run the script once again, and you will notice that our modified script
works just as we wanted by executing the “if” part of the script this time as
shown in the image below:

Example # 3: Using “if –z” to Show that a String is not Null

For showing that a string in Bash is not null using the “if –z” statement, we
will perform the following steps:
The script for this scenario is almost the same as for the scenario discussed
above. We have only replaced the “-n” flag with the “-z” flag, but this time,
we have also swapped the “if” and “else” parts of the script because the “-z”
flag returns true if the string is null. It means that this time, the “else”
part of the script will be executed because our string was not null.
You can verify this by running the script that you have just modified, and you
will be able to see that your string was not null, as shown in the image below:

Example # 4: Using “if –z” to Show that a String is Null

For showing that a string in Bash is null using the “if –z” statement, we will
perform the following steps:
We have used the same script for this scenario as we did for Example # 3. The
only change that we have made to this script is that we have made our string
null by assigning it the null value, as you can see in the image shown below:
Now when we run this script, the “if” part of the script will be executed
because the string is null, and hence the value of the “-z” flag will be true,
as you can see from the following image:

Example # 5: Taking String User Input and Testing it with “if –z”

For testing the string input provided by the user with the “if –z” statement,
we will perform the following steps:
We will copy the script shown in the image below in our Bash file. Here, we are
asking the user to enter a string, and then we are saving that string in the
“string” variable with the “read” command. Then we are testing this string with
the “if –z” statement, which will be executed if the string is null. If that
will be the case, this script will prompt the user to enter a valid string, and
then it will print that string. However, if the user enters a valid string for
the first time, then the “else” part of the script will be executed.
After running this Bash script, when we were prompted to enter a string, we
intentionally entered a null string, i.e., we simply pressed the Enter key.
That is why our terminal prompted us to enter a valid string, as shown in the
following image:
This time we have entered a valid string “hello,” and hence the terminal
printed the corresponding message as shown in the image below:

Conclusion

This article taught you all the different methods with which you can test your
strings for being null or not while using the “-z” and “-n” flags with the “if”
statement. By using these flags, we can test any strings and hence use them
very efficiently in our scripts.


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
