





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Functions Tutorial

3 months ago
by Saeed_Raza
A Bash function is a collection of commands that can be executed repeatedly.
The goal of the function is to make the Bash scripts easier to read and prevent
you from typing the same script often. Bash functions are considerably
constrained in comparison to those of the majority of programming languages.
For step-by-step execution, this file contains various commands. Although these
commands can be entered simply into the command line, it is more convenient to
save all interconnected commands for a given operation in a single file from a
reusability perspective. We can utilize that file to run the specified set of
commands, a single time or multiple times, depending on our needs. We will go
through the fundamentals of Bash functions in this lesson and demonstrate how
to use them in shell scripts.

Example 1

A function is a section of code that can be called several times to carry out
specific tasks in programming. Code length is decreased, and program modularity
is provided. The most basic illustration of a function’s application in Bash
scripting is shown in the following:
In the previous script, we have defined the function “BashFunction”. Inside it,
we have an echo statement. Then, we called the function “BashFunction” to
print.
The output of the Bash basic function is printed on the terminal:

Example 2

We can pass arguments and process data with Bash functions like in other
programming languages. Similar to passing command line parameters to a Bash
script, we can input data into the function. We must add the parameters
immediately following the function name to provide any number of arguments to
the Bash function. When calling the function, we can pass the arguments
directly and use the values $1, $2,… $n to access them inside the function.
In the previous script, we have created the function “multiply_two_numbers”. In
the function, we have created the variable “product” and assigned the equation
of the product to be computed. The echo command is then used to print the
outcome of the calculation for the product of two values. After that, we have
provided the two arguments, 5 and 2, assigned to the function
“multiply_two_numbers”.
The terminal shell after the script execution is shown in the following image:

Example 3

Most programming languages support the idea of functions returning a value. It
implies that the function must return the data to the place from which it is
called. Bash functions don’t support returning a value when they are called,
unlike functions in real programming languages. However, they give us the
option to establish a return status, which works similarly to the exit status
used by a program or command to terminate.
The variable “$?” is allocated the word “return”, which can be employed to
describe the return’s current state. The function is ended by the return
statement, which also serves as the exit status for the function.
In the script, first, we have established a function “my_function”. In the
function, we have a return keyword that takes the value “14”. Then, we invoked
the function “my_function”, which has an echo statement that will return the
value to “$”.
The Bash script output the value specified to a return command as follows:

Example 4

In a script, a global variable is a variable that may be accessed from any
location and has no restrictions on its scope. Even if a variable is declared
inside a function, it is automatically defined as a global variable. Variables
can also be created locally. Once they have been allocated for the first time,
local variables can be specified inside the function body using the keyword
“local.” Only that function allows you to access them. The same name might be
given to local variables created in other functions.

The Bash script begins with the declaration of the global variable “var1” and
initializes it with the value of a string. Then, we created the function
“Animal_names_fun”. To the function “Animal_names_fun”, we have set the local
variable with the keyword local and one global variable. The local and global
variables have been defined with the names “var2” and “var3,” and we have also
set their values. Then, we echoed the global variable “var1” within the
function and the local variable “var2” within the function. After that, we
called the function “Animal_names_fun” and accessed the global variables “var1”
and “var3”, which usually execute, but as we are trying to access the local
variable “val2” outside the specified function, it will return an empty value.
You can notify the output of accessing the local and global variables in the
bash program as follows:

Example 5

By naming a function the same as the command we want to override, we can choose
to override the Bash commands. For instance, we must write a function called
“echo” if we intend to override the echo command.
This idea of overriding Bash commands may be helpful in some circumstances,
such as when we want to utilize a command with particular options.
Additionally, there are situations when we do not want to repeat the entire
command with options within the script. We can use options to alter the built-
in Bash command in these situations. Let’s use an example to understand better
the idea of overriding commands in Bash Shell Scripting:
In the previous Bash script, we have a function echo. Within the echo function,
we overrode the echo command and inserted the built-in timestamp method as an
argument to the echo command.
The output of the Bash override function is displayed in the following image:

Conclusion

We discussed the Bash function on this topic. A chunk of reusable code
explicitly created for a given task is called a Bash function. Once defined, it
can be used several times in a script. Bash engages with the operating system
to carry out commands received from the shell after reading them. One fantastic
feature of Bash is that it allows you to combine a lot of its commands and
functions into a single executable script, which makes it easier to organize
your work.


About the author


Saeed Raza

Hello geeks! I am here to guide you about your tech-related issues. My
expertise revolves around Linux, Databases & Programming. Additionally, I am
practicing law in Pakistan. Cheers to all of you.
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
