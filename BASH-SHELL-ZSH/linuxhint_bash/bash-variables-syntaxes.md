





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Begin with Bash Programming: Variables and Syntaxes

1 year ago
by Suparna_Ganguly
Are you about to begin with Bash programming? Then, this article is for you.
Bash, actually, is a Unix shell developed by Brian Fox. In command-line
interface (CLI) programs, commands are processed as lines of text. The
interface itself is called a command-line processor or command-line interpreter
or more popularly, a shell.
If you’re a complete code newbie, this guide might help you understand how code
is written. Initially, you’ll write simple programs to get comfortable with the
programming language and to know the syntaxes and tools available to perform a
certain task. If you’re somehow familiar with Bash, then your learning process
will be easier.
In Bash, you mostly use Linux commands. The syntax is Bash. We’ll discuss Bash,
but before that here’s is a quick overview of the shell.

What Exactly is Shell?

A shell is a program that receives commands and gives them to the OS for
performing tasks. In other words, it interprets the commands given by the
programmer. After results are returned, the shell shows it in the terminal. So,
through the terminal window, you interact with the shell.
Bash is the shortened word of Bourne Again Shell. So, Bash programs can be
called Shell programs. Bash shell was built upon the original Unix shell, sh,
created by Steven Bourne. Apart from Bash, other frequently used shell programs
for Linux systems include csh, zsh, ksh, and tcsh.

About Bash Programming

Bash is for lazy coders. Through Bash, you can issue commands in a simple and
straightforward manner. A Bash program acts as an efficient tool to save your
time and effort while writing programs. You can use simple programs to perform
a long chain of tasks.
Bash can be used in a variety of ways, such as running customizing admin tasks,
performing task automation, running a shell command, executing multiple
commands, and a lot more. Hence, knowing the basics of bash programming is
primary for Linux users.
Like any other programming language, Bash deals with variables, arguments,
arithmetic operators, and various syntaxes used to write programs. We’ll have a
quick overview of each one of them. To make your learning easier and get used
to with Bash programs, we’ll try to explain the concepts using simple code
examples. You can see the output at the end of every program so that you can
try and check the programs with your results when you practice. Also, you’ll
create your first bash program.

Variable Declaration

You can declare your own variables in Bash. This helps track the results of the
commands given. Variable is declared as follows.
variable=value
This is a common practice of declaring variables. You can use both uppercase
and lowercase letters in variable names. Bash is case-sensitive. So, be
consistent with your choice of letters. Also, make sure to choose a variable
name that describes its purpose well.
Remember, you should never put space on the equal sign (=) and either of the
words. Now, let’s see a simple example of variable declaration and its output.
$ #!/bin/bash      
$ firstvar=Hello           
$ secondvar=World                  
$ echo $firstvar $secondvar
$ echo         
$ mydir=/etc                   
$ ls $mydir
In the 2nd and 3rd lines, values are assigned to two variables, firstvar and
secondvar. In the 4th line, echo checks the variable values.
After that, another echo is run with no arguments. This creates a blank line to
get some space out of the code. Then, another variable mydir is created as a
path to a directory.

Passing Arguments

You use the Unix shell to run commands. It allows its users to pass run-time
arguments to those commands. The arguments are known as command line
parameters. This has two usages: flow control and specifying the input for the
command.
There are some predefined variables to represent the arguments. $1 refers to
the first argument, $2 refers to the second argument passed to the script, $3
represents the third argument, and so on. Following is an example. Take a look
at the output for your reference.
$ set the sky is cloudy
$ echo $1 $2
As you can see from the output, $1 and $2 have been assigned to “the” and “sky”
respectively.

Arithmetic Operations in Bash

This section of the article explains arithmetic operators used in Bash.
Arithmetic operations are performed on numeric values and you get the desired
output. In the Bash script, arithmetic operations are simple and easy to
understand.
To perform the basic arithmetic operations in the Bash shell, the double
parentheses technique is used. The method is to use double brackets without or
with a $ in the beginning. The syntax is:
$((expression))
Let’s have a quick look at some of the basic arithmetic operations with the
following example.
#!/bin/bash  
$ x=16
$ y=4
$ echo "x=16, y=4"  
$ echo "Addition of x & y"  
$ echo $(( $x + $y ))  
$ echo "Subtraction of x & y"  
$ echo $(( $x - $y ))  
$ echo "Multiplication of x & y"  
echo $(( $x * $y ))  
echo "Division of x by y"  
echo $(( $x / $y ))  
echo "Exponentiation of x,y"  
echo $(( $x ** $y ))  
echo "Modular Division of x,y"  
echo $(( $x % $y ))

The Conclusion

Today you have learned “how to begin with Bash programming”. In this article,
you have learned about the command-line interface, Bash programming, syntaxes
used in Bash, passing arguments, and how to use variables to perform arithmetic
operations. You have also learned about the shell in brief and why Bash
programs are called Shell programs. Hope after going through this article you
can perform Bash tasks more efficiently.


About the author


Suparna Ganguly

I'm an Engineer by degree and a Writer by choice. I like to learn and explore a
good range of topics including Linux, programming, open-source, games, and
computers. My content write-ups in LinuxHint can be your source of knowledge,
guide, and values.
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
