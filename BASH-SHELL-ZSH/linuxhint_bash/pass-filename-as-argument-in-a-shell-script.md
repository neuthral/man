





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How To Pass Filename As Argument In A Shell Script?

1 year ago
by Aqsa_Yasin
Using the shell scripts in Linux is an excellent way of task automation. You
can create shell scripts for tasks with varying complexity levels from
extremely simple to extremely complex. These shell scripts, when executed,
produce the desired results within a matter of seconds. However, at times, you
feel the need of passing the file names as arguments to these shell scripts.
Therefore, we have designed today’s article to teach you the different ways in
which you can easily pass file names as arguments to the shell scripts in
Ubuntu 20.04.

Need Of Passing Filenames As Arguments In A Shell Script In Ubuntu 20.04

Now, you might be thinking that why do we even need to pass file names as
arguments to the shell scripts in the first place. Well, you can have multiple
different requirements for which you need to do so. However, the most common
use case of doing this is using the “passed” file for reading data from it or
writing data to it. For example, you want to create a shell script that
calculates the sum of two numbers and stores this sum in a new file. You can
actually pass the name of this file to be created as an argument to your shell
script while executing this script.
In the same manner, you might want to calculate the total scores of a player in
three different football matches. Assume that all of these scores are stored in
a text file. Therefore, if you will write a shell script to calculate the total
score, then you will first need the data from that text file that you will use
to calculate the total. In that case, you will need to read that file first.
So, you can easily pass the name of the file to be read as an argument to your
shell script while executing it from the terminal.

Methods Of Passing Filenames As Arguments In A Shell Script In Ubuntu 20.04

If you want to pass a file name as an argument to a shell script in Ubuntu
20.04, then depending on your exact need, you can pick any of the following
three methods:
Method 1: Passing A Single Filename As Argument
For explaining this method, we have created the shell script shown in the image
below:
In this script, we have written the “echo” command for printing a message after
the Shebang. Following this command is another “echo” command that is there to
print the value of the special variable or the positional parameter “$1”. It
means that whichever value will be passed to this shell script from the
terminal will be stored in this positional parameter, and as a result of using
the “echo” command, this value can also be printed on the terminal.
For executing this shell script in Ubuntu 20.04, we will execute the following
command in the terminal:
$ bash Filename.sh Hour.sh
In this command, Filename.sh represents the name of that shell script that we
want to execute whereas Hour.sh is the name of the file that we wanted to pass
on to this shell script. You can replace these file names according to the
names of your own shell script files.
When you will run the above-mentioned command, the specified shell script will
be executed, which in turn will display the name of the shell script file in
the output. This will be passed as an argument to this shell script, as shown
in the image below:
Method 2: Passing Multiple Filenames As Arguments
This method is basically an extension of our first method. It means that in
this method, we will try to pass multiple file names as arguments to a shell
script by using the very same technique. For that, the shell script that we
have used is shown in the following image:
In this shell script, we simply wanted to print the values of three different
positional parameters, i.e., $1, $2, and $3 on the terminal. It means that
whichever arguments will be passed on to this shell script from the terminal
will be stored in these three positional parameters and as a result of using
the “echo” command, these values will also be printed on the Ubuntu 20.04
terminal. Moreover, you can use these positional parameters up to $9 if you
wish to pass more than three arguments to your shell script file in Ubuntu
20.04.
Now, to execute this shell script, we will run the command shown below in the
terminal:
$ bash Filename.sh Hour.sh eof.sh EOF.sh
Here, Filename.sh represents the name of the shell script that we wish to
execute; whereas Hour.sh, eof.sh, and EOF.sh refer to the names of the files
that we wanted to pass on to this shell script as arguments. You can replace
these file names according to the names of your own shell script files.
As soon as this script will be executed with the above-mentioned command, it
will display the names of all the arguments passed on to our shell script,
i.e., the names of the three files that we have passed on to our shell script,
as shown in the following image:
Method 3: Passing The Current Filename As Argument
Instead of passing different file names to a shell script in Ubuntu 20.04, you
might just want to use the name of your current file. This file name is already
passed as an argument when you execute your shell script and is also stored in
a special variable or a dedicated positional parameter, i.e., $0. It means that
you do not need to especially pass this filename as an argument, rather, you
only need to access it by referencing the $0 parameter of your shell script.
For doing so, you can take a look at the shell script shown in the image below:
In this shell script, we have simply used an “echo” command to print a message
on the terminal followed by another “echo” command that will print the value of
the $0 special variable on the terminal, i.e., the name of your current file.
To execute this shell script, you will have to run the following command in
your Ubuntu 20.04 terminal:
$ bash Filename.sh
Here, Filename.sh corresponds to the name of our current shell script that we
want to be executed.
Now, since the name of this file was stored in the $0 special variable,
therefore, as a result of executing this shell script, the name of this file
will be printed on the terminal, as shown in the image below:

Conclusion

By using these methods, you can conveniently pass file names as arguments to
your shell scripts in Ubuntu 20.04. You can use the shell positional parameters
ranging from $0 to $9 for achieving this objective. The goal of this tutorial
was just to teach you the different methods of passing the file names as
arguments to the shell scripts in Ubuntu 20.04. However, you can increase the
complexity of the shell scripts shared in this tutorial by using the “passed”
file names for serving different purposes.


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
