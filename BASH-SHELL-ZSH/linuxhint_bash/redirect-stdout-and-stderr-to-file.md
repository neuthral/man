





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Redirect stdout and stderr to File

1 year ago
by Talha_Saif_Malik
When you redirect any command output to a file, you will notice that the error
messages are printed on the terminal window. Any command executed in any Linux
shell, such as bash, utilizes three regular I/O streams. A numeric file
descriptor is used to represent each stream.

* The standard input stream (stdin): 0
* The standard output stream (stdout): 1
* The standard error stream (stderr): 2

In this post, we will grasp the information that comes under redirecting stdout
and stderr to file.

Standard_output (stdout):

Each operating system based on Linux has a conviction of a default place for
the executed command.  Everyone refers to this notion as “stdout” or “standard
output” to make it sound easier. Your Bash or Zsh shell is constantly looking
for the default output location.  When the shell detects new output, it
displays it on the terminal screen for you to see it. Otherwise, it will send
the output to its default location.

Standard error (stderr):

Standard error or stderr is similar to standard input and output, but it is
utilized for storing error messages. The standard error can be redirected to
the command line or a file using a terminal. If you want to record or store
messages in a separate log file or hide the error messages, redirecting stderr
will help you. Now let’s head towards the practical side of stdout and stderr
redirection.

Redirecting stdout and stderr to a file:

As redirection is a method of capturing a program output and sending it as an
input to another command or file.  The I/O streams can be redirected by putting
the n> operator in use, where n is the file descriptor number. For redirecting
stdout, we use “1>” and for stderr, “2>” is added as an operator.
We have created a file named “sample.txt” to store the redirected output in our
current directory.
The (command > file) is considered as the classic redirection operator that
only redirects the standard output with the standard error shown in the
terminal. We will demonstrate different options to redirect stderr as well.

Redirecting stderr and stdout to separate files:

Below is the command syntax for redirecting stdout and stderr to separate
files.
command > out 2>error
The below-given command will redirect the output to the “out” file and error
messages to the “error” file.
$ cat sample.txt > out 2>error

Redirecting stderr to stdout:

It is a common practice to redirect the stderr with the standard output of a
program to store everything in a single file. Here is the command syntax for
redirecting stderr to stdout:
command >out 2>&1
$ ls > samplefile.txt 2>&1

$ cat samplefile.txt
> out redirects redirect the stdout to samplefile.txt, and 2>&1 will redirect
the stderr to the current location of stdout.
If stderr is redirected to stdout first, use the below-given command to
redirect the stdout to a file.
command 2>&1 > file
$ ls -al 2>&1 > samplefile.txt

$ cat samplefile.txt

“&>” is also used for the same functionality which“2>&1” performs.
command &> file
$ ls &> samplefile.txt

$ cat samplefile.txt

Redirecting stdout and stderr to a single file:

All of the shells do not support this form redirection, but bash and Zsh
support it. Stdout and stderr can be redirected by utilizing the following
syntax.
command &> out
$ cat sample.txt &> out
In the upcoming section of the article, we will check out the separate example
for stdout and stderr redirection.

Redirecting stdout to a file:

The standard output is represented by the “1” in the list of file descriptor
numbers. For redirect command without any file descriptor number, the terminal
set its value to “1”. The syntax for redirecting the stdout to a file is given
as follow:
command > file
We are using the “sample.file” for storing the standard output of the “ls -al”
command
$ ls -al > sample.txt

$ cat sample.txt

command 1> file
$ ls 1> sample.txt

$ cat sample.txt

Redirecting stderr to a file:

Use the “2>” operator for redirecting the stderr to a file.
command 2> file
$ ls -al 2> sample.txt

We can combine the execution for stderr and stdout in a single redirection
command.
command 2> error.txt 1> output.txt
In the below-given example, the error messages will be stored in “error.txt,”
where “output.txt” will have its standard output of “ls command.”
$ ls 2> error.txt 1> output.txt

$ cat output.txt

Conclusion:

Having the concept of redirection and file descriptors for I/O streams is very
valuable while working in a Linux terminal. In this post, we have talked about
the regular I/O streams, including stdout and stderr. The first section of this
post brings you detailed information about the redirection, I/O streams, and
the numeric file descriptor. Next, you have seen the practical example for
various forms of stdout and stderr redirection.


About the author


Talha Saif Malik

Talha is a contributor at Linux Hint with a vision to bring value and do useful
things for the world. He loves to read, write and speak about Linux, Data,
Computers and Technology.
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
