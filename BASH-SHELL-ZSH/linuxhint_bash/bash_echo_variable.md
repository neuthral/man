





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash how to echo a variable

2 years ago
by Karim_Buzdar
While a user is working bash script execution in a Linux system, different sets
of bash commands need to be executed from the terminal window based on the
various requirements. After running bash commands, it shows the output on the
terminal if no error exists otherwise an error message shows on the command-
line window. Sometimes, users want to keep this output for future use. In this
situation, the output of these commands can be stored in a variable.
Variables are an essential feature of bash programming in which we assign a
label or name to refer to other quantities: such as an arithmetic command or a
value. They are used to make the machine programs more readable for humans.
Using the echo command you can display the output of a variable or line of
text. It requires no formatting while implementing this option. The echo
command is useful to display the variable’s output especially when you know the
content of a variable will not cause any issue.
In this article, we will explore how to echo a variable in bash. We have
implemented all bash commands on Ubuntu 20.04. We will discuss some examples
through which you can easily understand the basic concepts.

Basic Syntax

Here, is the basic syntax of how to echo a variable is given below:
echo $var_name
In the above command echo is a command that is used for displaying the value of
variable ‘var_name’. Var_name is the name of a variable.

Launch terminal

Open the terminal by pressing ‘Ctrl + Alt + t’ or launch terminal from the
application search bar. To do that, click on the ‘Activities’ located at the
left corner in Ubuntu 20.04 and the write ‘terminal’ in the search bar as
follows:
Launch the terminal by clicking on the terminal icon.

Echo Single Variable

Using the echo command you can echo the value of a variable. Just you need to
declare and assign value to a variable and then simply echo the value of the
variable. For your good understanding, we will discuss some examples which are
given below:

Example # 01:

Let’s take an example, we want to display the value of a variable named ‘var_a’
that has a value 100. Now, using the echo command we can simply display its
value on the terminal as follows:
$ var_a=100
$ echo $var_a
The following output you will on the terminal:

Example # 02:

Let’s discuss another example, we want to display the text ‘bash programming
echo variable’ on the terminal by using the variable. So, take a variable named
‘var_b’ and store the above text in this variable with double-quotes.
$ var_b=” bash programming echo variable”
$ echo $var_b
You will see the following output on the terminal:
Note:if you will use echo var_b then it will only display the variable name on
the terminal instead of displaying its value.

Echo Multiple Variables

The following example will show you how to echo multiples variables:

Example # 01:

For example, take two variables var_A and var_B.
$ var_A=”hellofriends”
$ var_B=50
$ echo $var_A$var_B
The following output will display on the terminal:

Example # 02:

For example, we want to display the date and hostname of our computer. So, we
will store the date and hostname commands in var1 and var2 respectively. You
can see the implementation as follows:
$ var1=$(date)
$ var2=$(hostname)
$ echo “the date is $var1 @ computer name is $var2”
After running the above command, you will see the following output:

Conclusion

In this article, we have shown how to display a variable value or text output
by using the echo command. We have executed different bash variables examples
on the terminal for better understanding. From the above commands, I hope now
you are familiar with how to echo variables and text in bash programming.
Furthermore, you can use different commands to store inside the variable.
Please, let me know in case of any problem related to this article.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
