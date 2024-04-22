





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Variables in Bash?

1 year ago
by Omar_Farooq
Variables in any programming language act as temporary storage spaces for
keeping different types of data in them for processing. A variable generally
has two different entities associated with it, i.e., its data type and its
value. The data type is the actual type of data stored in a variable, whereas
the value refers to the actual data stored in the variable. However, in Bash
programming, you do not need to state the data type while declaring a variable
explicitly. It is so because this programming language itself detects the data
type. For example, whenever you assign a number to a variable in Bash, it will
automatically be treated as an integer.
A Bash script can be used to perform certain operations on your computer
system. However, a simple Bash script can also be written without using any
variables, i.e., printing a message on the terminal or using a built-in command
like “date”, etc. But whenever you need to temporarily hold some values for
manipulating them later on, you must use the variables in Bash. By now, you
must have realized that today’s discussion will revolve around the variables
and their usage in the Bash programming language.

How to Declare a Variable in Bash?

A variable in Bash can be declared with any name of your choice followed by the
equality (=) symbol and any value of your choice assigned to it. Some examples
of simple Bash variables are shown below:
This example refers to a String variable in Bash. We have opened the terminal
and declared the variable as presented in the below-attached snapshot.
$ _name=Linuxhint
To get the output using the “Echo” keyword as:
$ echo $_name
To an Integer variable in Bash. We have opened the terminal and declared the
variable as presented in the below-attached snapshot.
$ _number=22
Now to get the output use the “Echo” keyword as:
$ echo $_number
This example refers to a character variable in Bash. We have opened the
terminal and declared the variable as presented in the below-attached snapshot.
$ _alphabet=a
Now to get the output using the “Echo” keyword as:
$ echo $_alphabet

Variable Scope

Like any other programming language, the scope of a Bash variable can either be
Local or Global. However, in Bash, the default scope of all the variables is
global, no matter where they have been declared in your Bash script. It means
that even if a variable is declared somewhere in the middle of a Bash script,
it can still be used inside any function within that Bash script. In other
words, we can say that to make the scope of a variable global in Bash; you do
not necessarily need to declare that variable at the top of a Bash script.
However, if you want the scope of a Bash variable to be local to any specific
function, i.e., you do not want that variable to be accessed by any other
function in that script or anywhere outside the function in which it has been
declared, then you will have to explicitly use the “local” keyword while
declaring that variable. In this way, the scope of that variable will only be
limited to the function inside which it has been declared.

Variable Types

The best thing about the Bash programming language is that you do not need to
state the data types while declaring variables explicitly. In other words,
there are no specific data types in Bash. Rather the data type will depend on
the exact value you will assign to a particular variable in Bash.
However, if we take the variable type in terms of the purpose according to
which that variable is used, then there are four different types of variables
in Bash, which are as follows:
Global and Local Variables:A variable whose scope is global and can be used all
across a Bash script. A variable whose scope is limited to a particular
function in a Bash script and can only be used inside that function. Now to
explain global and local variables in bash, utilize the following stated
example. One global variable, “a” and two local variables, “a” and “b” are
utilized in the given script. The mentioned value of the local variable “a” is
used for computation when the function addition() is executed, while there is
no effect on the global variable “a”.
Environment Variables:These variables are required to set up the Bash
environment in a certain way for certain programs to work properly. Now to
display the environment variable on the terminal, follow the subsequent
command.
$ env | less
The output will look the same as presented in the attached image.
Shell Variables:These variables are an essential component of Shell that
enables it to work properly.

Variable Naming Convention

Bash follows a very simple naming convention for its variables. The runtime
variables should be named in Caps, e.g., RUNTIME, whereas all other variables
should be named in small letters, ideally, starting with an underscore (_),
e.g., _my_variable. However, the general rule of keeping meaningful names for
all the variables must be kept in mind all the time, even while creating
variables in Bash.

Variable Substitution

Bash programming also allows you to substitute the value of a variable with the
output of a command. In other words, you can execute a built-in command within
a Bash script and store its output in a variable within that Bash script. For
example, _today=$(date). This statement will store the current system date and
time to the _today variable.

Special Variables

As the name implies, a special variable in Bash is there to perform a special
operation. In other words, you can say that these are built-in Bash variables
that control the flow of execution of your program in a certain way. Some of
the most frequently used special variables in Bash are listed below:

* $$:This special variable is used to access the process ID (PID) of your
  current Bash script.
* $0:This special variable is used to store the title of your Bash script.
* $USER:This special variable stores the user’s name who is executing the
  current Bash script.
* $HOSTNAME:This special variable stores the system’s hostname that is
  executing the current Bash script.
* $RANDOM:This special variable returns a random number.

To get a basic understanding of all mentioned special variables, we have used
them in this example script. Initially, the “special.sh” file was created using
the “touch” query.
$ touch special.sh
You can view it in the working directory, i.e., the home directory. The script
shows the usage of all special characters. You can modify it as well.
To get output to execute the command with keyword “bash”.
$ bash special.sh
The output can be seen in the attached snapshot.
Other than the ones mentioned above, there are other special variables in Bash
too that serve different purposes within a Bash script.

Conclusion

In this tutorial, we walked you through the different concepts associated with
the variables in Bash. By going through these concepts before getting started
with variables in Bash, you will understand using these variables effectively
while programming.


About the author


Omar Farooq

Hello Readers, I am Omar and I have been writing technical articles from last
decade. You can check out my writing pieces.
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
