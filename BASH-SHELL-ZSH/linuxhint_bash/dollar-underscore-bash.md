





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


What does $_ Mean in Bash

1 year ago
by Aqsa_Yasin
Bash is a very versatile scripting language that is most commonly used with
Linux-based systems. With this language, you can easily automate your daily
routine tasks and also simplify repetitive tasks. This language is a blend of
different entities such as special variables, functions, built-in commands,
etc. Each special variable of this language serves a specific purpose. The
special variable that we will be discussing in this article is “$_” which is
there to print the last argument of the previous command. It is a bit complex
to understand the functionality of this special variable without looking at
relevant examples. Therefore, we have designed this tutorial so that it will
first explain to you the use case of this command, followed by a relevant
example. Let us find out together what this article holds for us.

Use Cases of $_ in Bash in Ubuntu 20.04:

There are different use cases of using the special variable “$_” in Bash in
Ubuntu 20.04; however, below, we will be discussing the three most common use
cases of this special variable.

Use Case # 1: Using “$_” in Ubuntu 20.04 Terminal:

This special variable can be used in the Ubuntu 20.04 terminal. The purpose of
using it within the terminal is to print the last argument of the previous
command executed within the terminal. Consider a scenario in which you executed
a command some time ago and did not execute anything in your terminal after
that, but you still want to know what you did last time. In this situation, you
can use the “$_” special variable in the terminal to know about the last
argument of the previous command that you executed in your terminal. To
understand all this in a better way, you can take a look at the following
example:

Example:

In this example, we intend to print the last argument of the previously
executed command in the Ubuntu 20.04 terminal. For that, we have executed the
command shown below in our terminal:
$ ls *.sh;echo $_
The command mentioned above is basically an integration of two different
commands. The first command, i.e., ls *.sh, lists down all the Bash files
present within the current directory. On the other hand, the second command,
i.e., echo $_ will display the last argument of the “ls” command, i.e.,
whatever will be printed last as a result of executing the “ls” command will be
printed again when the “echo $_” command will be executed. The output of this
command can be seen from the following image:
In this output, you can clearly see that the last argument printed due to
executing the “ls” command is the Bash file whose name is “Suppress.sh”.
Moreover, you can also see that the same file name is printed again because of
using the “$_” variable since this file was, in fact, the last argument of the
previously executed command in the terminal, i.e., the “ls” command.

Use Case # 2: Using “$_” for Displaying the Path of the Bash Script:

The “$_” special variable can even be used for displaying the path of a Bash
script in Ubuntu 20.04. It can do so if you create a simple Bash script and use
the “$_” special variable before writing any other command in your Bash script.
By doing so, you will be able to get the path of your Bash script very easily.
To demonstrate the functionality of this special variable in Bash, we have
designed the example shown below. Just go through this example for once, and
you will be able to immediately know how the “$_” special variable can be used
to display the path of the Bash script.

Example:

In this example, we want to use the “$_” special variable for displaying the
path of a Bash script on the Ubuntu 20.04 terminal. For doing so, we have
created the following sample Bash script and named it “Sample.sh”:
In this Bash script, after writing Shebang, we have simply used the “echo $_”
command so that when we execute this Bash script, it will print the value of
the “$_” special variable on the terminal, i.e., the path of our Bash script
file. You can also extend this script further by adding more commands of your
choice after the “echo $_” command.
To execute this Bash script, you will have to run the command shown below in
your terminal:
$ bash Sample.sh
When you execute this Bash script, its path will be printed on your terminal as
a result of using the “$_” special variable within your Bash script, as shown
in the following image:
The path of the Bash file that we created in our case was /bin/bash, as you can
see from the output shown in the image above.

Use Case # 3: Using “$_” for Displaying the Last Argument of the Previous
Command in a Bash Script:

This use case is somewhat similar to the first use case of our article.
However, in the first use case, we have simply used integration of two commands
within the Ubuntu 20.04 terminal, whereas in this use case, we will create a
Bash script that will serve more or less the same purpose, i.e., in this Bash
script, we will use the “$_” special variable after some commands in a way that
it will print the last argument of the previous command on the terminal. To
grasp this concept in a better way, you need to go through the example that we
have created below:

Example:

In this example, we have created a sample Bash script named “Sample.sh” and
after stating Shebang, we have declared two variables “a” and “b”. We have also
assigned the values of “10” and “12” to these two variables, respectively.
After that, we have used the “echo” command to print the values of these two
variables. Finally, we have used another “echo” command to print the value of
the “$_” special variable, which in this case will be the last argument of the
previously executed “echo” command, i.e., the value of the “b” variable.
After creating this Bash script, you can run it with the help of the following
command:
$ bash Sample.sh
When running this sample Bash script, you will see the value of the variables
“a” and “b” on the terminal. In addition to that, the value of the “b” variable
will also be printed again because of the “$_” special variable as shown in the
image below:

Conclusion:

This tutorial shed light on the three most common use cases of the “$_” special
variable of Bash in Ubuntu 20.04. With these use cases, you can either use the
“$_” special variable within the system’s terminal, or you can even create Bash
scripts for using this special variable. Moreover, you can even increase the
complexity of the Bash scripts that have been shared with you in this article.
The purpose of this article was to give you an overview of the usage of the $_”
special variable in Bash in a Ubuntu 20.04 system.


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
