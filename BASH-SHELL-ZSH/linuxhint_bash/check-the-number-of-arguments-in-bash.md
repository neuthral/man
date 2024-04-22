





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How Do You Check the Number of Arguments in Bash?

1 year ago
by Aqsa_Yasin
You can provide any desired number of command-line arguments to your Bash
scripts in Ubuntu 20.04 while executing them. However, sometimes the scripts
are written in such a dynamic manner that even the programmer does not know
exactly how many arguments will be provided by the user at runtime, but he
might want to use that total number somewhere later in that script.
In this situation, there must be a way through which you can check the total
number of arguments passed to any particular Bash script. For that, Bash has a
special variable, i.e., $#. To figure out how this special variable works, you
will have to go through all the examples shared in this article.

Method of Checking the Number of Arguments in Bash in Ubuntu 20.04:

For explaining to you the method of checking the number of arguments provided
to a Bash script in Ubuntu 20.04, we have designed a few examples that are
discussed below:

Example # 1: Printing the Total Number of Arguments in Bash:

To simply print the total number of arguments passed to a Bash script in Ubuntu
20.04, you can write a Bash script like the one shown in the following image:
The $# special variable always holds the total number of arguments passed to
any specific Bash script.
For testing this script, we have executed it with three arguments or parameters
as follows:
$ bash Arguments.sh 1 2 3
Here, Arguments.sh is the name of our Bash script file, whereas 1, 2, and 3 are
the arguments that we have passed to this Bash script. It means that the total
number of arguments in this test case is “3”. Let us try to find out if this
Bash script has correctly displayed the total number of arguments or not.
When we execute this Bash script, it will display the total number of arguments
passed to it, which can be seen from the image shown below:

Example # 2: Printing the Total Number of Arguments along with the Values of
Arguments with Positional Parameters in Bash:

Now, we will write a Bash script that will print the values of the arguments
passed to a Bash script and their total number. For doing that, the Bash script
is as follows:
In this Bash script, we have first printed the values of the three positional
parameters. It means that whichever arguments will be passed to this Bash
script from the terminal will be stored in these three positional parameters.
After that, we have simply printed the value of the $# special variable.
In our first example, we will execute this script with the same arguments as we
passed on to the Bash script. This time when we will execute our Bash script,
the values of the three passed arguments will also be displayed on the terminal
along with their total number, as you can see from the image shown below:

Example # 3: Printing the Total Number of Arguments along with the Values of
Arguments with the [email protected] Special Variable in Bash:

The goal of this example is the same as that of our second example; however, in
this example, we will be using another special variable, i.e.,
[email protected], for printing the values of the passed arguments. Basically,
the [email protected] special variable can hold all the arguments that are
passed to a Bash script. To understand this, you can take a look at the
following Bash script that we have designed for you:
In this Bash script, we have simply printed the value of the [email protected]
special variable, i.e., all the passed arguments, and the value of the $#
special variable, i.e., the total number of the passed arguments on the
terminal.
To see how this modified Bash script works, we have again executed it with the
same parameters as we did in the two examples above. When this script was
executed, the output turned out to be exactly the same as we had in our second
example.

Example # 4: Printing the Total Number of Arguments along with the Values of
Arguments with the $* Special Variable in Bash:

This is yet another modified version of our second example since, in this
example, we will be using the $* special variable to print the values of the
passed arguments on the terminal. Like the [email protected] special variable,
the $* special variable can also hold the values of all the passed arguments to
any particular Bash script. The modified Bash script is shown in the image
below:
In this Bash script, we have simply printed the value of the $* special
variable, i.e., all the passed arguments, and the value of the $# special
variable, i.e., the total number of the passed arguments on the terminal.
To test this Bash script and visualize its output, we executed it with the same
parameters as we did in our first three examples. This time also when our Bash
script was executed, its output was the same as that of our second and third
examples, as you can see from the following image:

Example # 5: Putting a Limit on the Total Number of Arguments in Bash:

Finally, the $# special variable can also be used to limit the total number of
arguments passed to a Bash script in Ubuntu 20.04. To understand this
phenomenon, you will have to go through the Bash script shown in the image
below:
In this Bash script, we have an “if” statement that is applied to the $#
special variable. We wanted to limit the number of arguments to “3”. If the
arguments will be less than “3” an error message will be printed on the
terminal. Similarly, if the arguments will be greater than “3”, again an error
message will be printed on the terminal. However, if the provided arguments
will be equal to “3” only then the values of these arguments will be printed on
the terminal.
We wanted to test all three conditions of this Bash script. For that, we have
first executed this script with three parameters, and the corresponding output
is shown in the following image:
After that, we executed this Bash script with four arguments, because of which
an error message was printed on the terminal as shown in the image below:
Finally, we executed this Bash script with two arguments, because of which an
error message was printed again on the terminal as shown in the following
image:

Conclusion:

The $# special variable will let you find out the total number of arguments
passed to any Bash script very easily. By checking out the examples shared in
this article, you would have a clear idea about the working of this special
variable. Therefore, you can now write such Bash scripts without any worries
that somehow use the total number of provided arguments to those Bash scripts
at runtime on Ubuntu 20.04.


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
