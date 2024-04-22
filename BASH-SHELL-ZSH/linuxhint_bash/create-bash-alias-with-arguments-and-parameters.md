





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Create Bash Alias With Arguments and Parameters

1 year ago
by Aqsa_Yasin
Bash alias is said to be a technique used within the Linux system as an easy
alternative for bash commands to override difficult ones with fresh ones. In
other words, an alias is used within bash users to get easier hands-on terminal
commands to exchange difficult commands. Many of the bash users among us find
some bash commands difficult to remember that they feel a need for easier ones.
Alias is basically for those users.
Today’s article will discuss different ways to create simple bash alias with
and without arguments and parameters. So, let’s get started with opening the
shell terminal using “Ctrl+Alt+T” after login in from the Ubuntu 20.04 Linux
operating system.

Make Simple Bash Alias

On the daily basis, we use many bash commands in the shell of the Linux system.
One of them is the list command to list all the files and folders within the
home directory as below.

Another command shows the same list but with little more information regarding
files and folders e.g. privileges, date of creation, user, and group to which
it belongs.

For example, you don’t remember the command “ls –l”, so you want to make an
easier one with an alias. Hence, we will be using the below simple alias
commands to create an “ls” alias in exchange for “ls –l”.

When we use the “ls” command, it will show the output for what it shows for “ls
–l”. This means the terminal forgets what “ls” used to show us before making an
alias.

To undo the alias, try the below query.

Now, while running the same “ls” query, it shows the original output as it was
shown before the making of the alias

Bash Alias with Arguments and Parameters

Bash users need to understand that alias cannot take arguments and parameters.
But we can use functions to take arguments and parameters while using alias
commands. Firstly, we need to see what content we have in the files we are
using in our bash code to make an alias. So, we will be using two files e.g.
test.sh and file.sh in the alias code. We will be opening the “test.sh” file
within the terminal to see its contents via the “cat” query as below. You can
have a glance that it contains simple text providing information regarding a
user “aqsayasin”. Quit the file using “Ctrl+X”.

Let’s now open the other file “file.sh” to see its contents using the same
“cat” instruction in the shell as beneath. You can see from the output that the
file is already empty so we need to fill it with some data.

Let’s create an example of a function to see how the alias in bash can be
created using arguments and parameters. As we know that, the alias never
accepts arguments or parameters, hence, we will be using the function to do so.
We will write our commands taking arguments and behaving like an alias within
the function. So within the terminal shell, we have created a function “func()”
and added the commands for “move” and “copy” contents of one argument parameter
to another.
The parameter argument “$1” represents the first file having no contents and
“$2” represents the file having content in it at the time of writing the code.
The “mv” command is behaving like an alias moving the “$1” argument file
“$1.txt” parameter. This means another file will be created having the same
data. The “cp” command is behaving like an alias taking the first argument e.g.
“test.sh” and copy its contents to other arguments which would be an empty file
“file.sh”. In the last, the function has been closed.

Let’s test this functional argument alias within the shell by simply calling
the function with passing two arguments as file names. So, we have used
“file.sh” as a parameter value to the argument “$1”  and “test.sh” as a
parameter value to the argument “$2”. Try out the query below to make the alias
worked as mentioned in the function “func”.
$ func file.sh test.sh

As the “file.sh” has been passed to the argument $1 as a parametric value,
according to the bash code, it must now contain the data of file “test.sh”
which represents the argument $2 as per the “cp” command. Hence, whenever we
checked or displayed the contents of a file “file.sh” via the cat query, it
shows that the file has been filled with the data that was initially a content
of a file “test.sh”. Now, both the bash files have the same data within them as
the output shows.

According to the “mv” statement used in the function “func” behaving like an
alias taking arguments, must now move the “$1” value to the “$1.txt” argument.
In this alias command, “$1” represents “file.sh” and “$1.txt” represents a new
file to be created which will have the same data and name with a different
extension than file.sh.
So, when we have checked up on the newly created file “file.sh.txt”, we have
found that it also contains the same data as the file “file.sh” have via the
alias query “mv”. It simply moves the file.sh to the file.sh.txt completely.
For this purpose, we have tried the query “cat” as below.

Create Alias Within a Function

Here is a simple illustration of making an alias within some function. It will
work the same as it worked for the simple alias creation above. So, we have
created a function “test()” and created 6 alias in exchange for 6 difficult
commands of bash. Try this code in the shell and see how it works.

Firstly, we have listed the files and folders of the home directory to be used
further.

As per the alias created within the function executed above in the terminal,
these queries must work now. First, we are going to see how the previous
difficult queries worked. We have tried the “remove” query to delete file
“one.sh” from the list above. It will confirm your action by asking you to
remove this file. Tap “y” to remove it.

Upon checking the list again, we found that the file has been deleted.

Let’s check the alias command now to remove another file. So, we have tried the
alias “rm” to remove “file.sh”. After checking, we found that the alias worked
the same as the previous query.

Use the alias “mv” to move the file “new.sh” to a “Documents” folder with the
below query.

When we have navigated towards the “Documents” folder and listed its contents,
we have found that the file “new.sh” has been successfully moved here with the
usage of the “mv” alias.

Conclusion

In this guide, we have discussed how to make a simple alias within the shell
and how to make a bash alias with arguments and parameters while using
functions. We have also discussed how to use an alias within a function without
taking arguments or parameters and how to uncover these alias as well. We
believe this article is completely able to help you a lot while you have been
working on bash alias with arguments and parameters.


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
