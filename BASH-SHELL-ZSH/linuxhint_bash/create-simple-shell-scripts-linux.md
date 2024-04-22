





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Create Simple Shell Scripts in Linux Using Vim

2 years ago
by Sam_U
Shell Scripting executes commands to perform some useful functions and is
designed to run in the shell. Shell scripts are quite handy to perform
operations like file manipulation, automating tasks to avoid time consumption;
you can even create your commands.
Shell is an interface between the user and operating system that lets users
interact with the operating system and perform various tasks using commands.
Shell takes input from the user through the terminal, interacts with the
kernel, processes it, and gives the output.

How to create a shell script using Vim

Shell Scripts usually created using any text editor. Nano and Vim editors are
well-known text editors to create bash scripting files.  For this example, we
are using “Vim”. If you do not have Vim, then install it using the command:
$ sudo apt install vim
Open text editor using:
$ vim
Create a new file:
$ vi testscript.sh
Type the script. “#! /bin/bash” operator, shell directed to bourne shell: r
#! /bin/bash

echo “Hello World”
And save the file, press the “Esc” key to switch the mode, and then press “:w”
to save it. If it gives a “Read-only” error file, then use “:w!”, the file will
be saved:
Now to execute the file, type:
bash test script. sh

How to add comments in a shell script

To add a comment, use the “#” operator; the syntax is given below:
#! /bin/bash

#This is my first shell script

echo “Hello World”

How to use variables in a shell script

For any programming, language variables are essential. Variables are used to
store a value, whether it is an integer, character, or text string. Let’s
understand it with an example:
#! /bin/bash

myvariable=“This is my first script”

echo $myvariable
The above script will give variable value as output:
Let’s check how to get value in a variable from user value from user:
#! /bin/bash

echo “Enter your name”

read name_varable

echo "Enter your age"

read age_variable

echo “$name_varibale is $ age_variable old”
The following image is showing the output:

Conclusion

Shell scripting is very important to create your own command or run multiple
commands with one script file to perform various functions. In this guide, we
grasp the basic idea of shell scripting. We learned how to script and a shell
script file, save it and then execute it. Moreover, we understood the usage of
variables in shell scripting. Shell scripting is very handy to accomplish
different useful tasks, and there is a lot to uncover.


About the author


Sam U

I am a professional graphics designer with over 6 years of experience.
Currently doing research in virtual reality, augmented reality and mixed
reality.
I hardly watch movies but love to read tech related books and articles.
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
