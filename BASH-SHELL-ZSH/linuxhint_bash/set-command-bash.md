





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Set Command in Bash

10 months ago
by Taimoor_Mohsin
In Bash, the set command allows you to manage certain flags and characteristics
to influence how your bash scripts behave. These controls ensure that your
scripts follow the correct path and that Bash’s peculiar behavior does not
cause difficulties. The set command can be used to change the operating
parameters of the shell environment, allowing it to be customized, which will
be discussed in detail in this article.

How to use set command in Bash

You can take all the help related to the set command by typing.
$ set --help

As you can see in the above images, certain flags can be used with a set
command, and we are going to discuss some of those to see how they function and
their purposes.

How to stop overwriting files using set -C command

In general, you can overwrite an existing file with the same name, but this is
not possible anymore if you use the “-C” flag, as shown below.
$ set -C
In the above image, you can see that we have created a text file with the name
of “testfile.txt” and then we have also verified that file by running the list
(ls) command. After that, we have created the same file again and overwrites it
but you can see that it doesn’t allow you to create the same file again when
you use a “set -C” command. This is an essential command to protect your data
from overwriting by accident.

How to disable file name generation using set -f command

After that, you may want to turn off automatic filename displaying, sometimes
known as “globbing.” Globbing is great for discovering files, but it can also
be problematic if a rogue character shows up in the wrong place in your script.
The ‘-f‘ flag turns it off.
For example, let’s run the list (ls) command by typing
$ ls *
This command is used to show you the directories and their subdirectories, but
to disable this, you can type:
$ set -f
It can be seen in the above image that after running the “set -f” command, it
doesn’t allow you to see the content.

How to debug a bash script using the set x command

Now let’s take another flag, “-x” and try to understand its functionality. You
can also use the set command to observe which command in your script is being
executed and a result. This allows you to debug more precisely by providing you
with a real-time printout of where your script is and what each command’s
output is. For example, we have created a bash file with “testbash.sh” as shown
below and written any code.
Now let’s see its output by typing:
So we ran a basic bash script where we set a value of “var” to 5, and then we
decrement its value till it’s greater than 0 and also use a sleep command for
three seconds that will halt the process for 3 seconds before going into the
next iteration. Let’s see its behavior if we write “set -x” inside the bash
script, as shown below.
Now let’s view the result of this bash script by typing:
$ bash testbash.sh
As you can see from the above image, it shows you the output after each step,
which makes it super useful for troubleshooting and debugging, especially if
you have an extended code. You can also run this command without writing it in
the bash script by typing.
$ bash -x testbash.sh

How to find an unbound variable in a bash script using set -u command

Let’s suppose you have assigned a variable but later you forget to use it in
your bash scripting so it won’t display any error and ignore that variable when
you run the bash script as shown below.

Now when you write the set -u then it will show you an error as “unbound
variable” which means that you have initialized a variable but didn’t use it
later which is not recommended for the programmers.




How to export the variable in Bash script using set -a command

This command is used to export the variables in your bash script file. For
example, we have first executed the set -a command in the terminal and later
initialized two variables as shown below.
After that, we have created a bash script with the name of “testfile.sh” and
initialized those two variables as input by typing.
#! /bin/bash

echo $number1 $number2
When you execute the bash script file, you’ll see that the variable’s values
have been automatically exported, and you can view those values as an output as
shown below.

Conclusion

The set command in Bash allows you to control the behavior of your scripts by
managing specific flags and properties. These safeguards guarantee that your
scripts are on the right track and that Bash’s odd behavior does not cause
problems. The set command can be used to adjust the shell environment’s
operational settings, allowing it to be modified using certain flags that are
discussed in this article.


About the author


Taimoor Mohsin

Hi there! I'm an avid writer who loves to help others in finding solutions by
writing high-quality content about technology and gaming. In my spare time, I
enjoy reading books and watching movies.
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
