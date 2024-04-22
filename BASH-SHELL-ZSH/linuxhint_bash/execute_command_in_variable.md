





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash How to Execute a Command in a Variable?

2 years ago
by Karim_Buzdar
Bash scripts can be created in a variety of different ways and most of us are
familiar with executing the simple commands within a Bash script. However,
these commands can also be encapsulated within the variables in Bash. This
process is known as command substitution and it is generally used to store the
output of a command in a variable so that you do not have to run that command
explicitly again and again rather you can simply access that variable to get
the output of that command whenever you want. In this article, we will show you
how this can be done.
Note: All the scenarios demonstrated below have been carried out on Ubuntu
20.04. However, they will work exactly in the same way with any other flavor of
Linux as well.

Method of Executing a Command in a Variable in Bash:

For demonstrating the method of executing a command in a variable in Bash, we
will present to you three different scenarios which are as follows:

Executing the “echo” Command Stored in a Variable:

This is the simplest scenario in which our goal is to execute the echo command
which is stored in a variable. For making it to happen, you will have to follow
the series of steps mentioned below:

Step # 1: Creating a Bash Script:

You have to create a Bash Script in your Home folder for which you need to
click on the File Manager icon as you can see from the following image:
Now find any space in your Home folder and right-click on it to launch a menu.
Select the New Document option from this menu and then choose the Empty
Document option from the sub-cascading menu. Doing this will create a new
document in your Home folder. Now rename this newly created document with any
name of your choice followed by the .sh extension. In our case, we have named
it as CommandVar.sh.
For writing a Bash script in this file, double click on it to open it and then
type the script shown in the image below in your Bash file. Here, the first
line of the script i.e. “#!/bin/bash” shows that this file is in fact a Bash
file. Then we have created a variable named “test” and have assigned it the
value “$(echo “Hi there!”)”. Whenever you want to store the command in a
variable, you have to type that command preceded by a “$” symbol. In this case,
we wanted to store the “echo” command in the “test” variable so we have simply
typed the “echo” command followed by a random message and have enclosed it in
round brackets, and placed a “$” symbol before it. So now, if we want to
execute this “echo” command, we will have to access the “test” variable.
Therefore, to verify if the “echo” command stored in the “test” variable can be
successfully executed or not, we have printed the output of the “test” variable
on the terminal by making use of another “echo” command. After typing this
script, you need to save your file and close it.

Step # 2: Executing the Bash Script via the Terminal:

Now you have to execute this script via the terminal. So, open the terminal in
Ubuntu 20.04 and then type the following command in it:
bash CommandVar.sh
When you will press the Enter key to execute this command, you will be able to
see the following output on your terminal. Here, the highlighted portion of the
output is the output of the “echo” command that was stored in the “test”
variable.

Executing the “seq” Command Stored in a Variable:

In this scenario, we will print a sequence of numbers by using the “seq”
command stored in a variable. For causing it to happen, we will modify the Bash
script created above by performing the following steps:

Step # 1: Modifying the Bash Script Created above:

Open the Bash file that you have created in the method above and type the
following script in it. Here, we have created a variable named “sequence”. Our
goal is to print the numbers from 1 to 10 while using the “seq” command. For
doing that, we have assigned the value “$(seq 1 10)” to the “sequence”
variable. You can also specify any other range of numbers of your choice if you
want. The first number after the “seq” command indicates the lower bound of the
sequence whereas the second number refers to the upper bound. After typing this
script, save your file and close it.

Step # 2: Executing the Modified Bash Script via the Terminal:

Now execute your Bash script in the same manner as explained above and you will
be able to see the specified sequence on your terminal as shown in the image
below:

Executing ‘pwd’ Command Stored in a Variable:

You can also print your working directory by making use of the “pwd” command
stored in a variable. To demonstrate this, we will modify the Bash script
created above yet again by following the steps mentioned below:

Step # 1: Modifying the Bash Script Created above:

Open the Bash file that you have just modified and then type the script shown
in the following image in it. In this script, we have created a variable named
“working_directory” and have assigned it the value “$(pwd)”. The “pwd” command
will simply store its output i.e. the current working directory in the
“working_directory” variable. For ensuring whether the “pwd” command has been
correctly executed or not, we have printed the value of the “working_directory”
variable on the terminal by using the “echo” command. Now save this file and
then close it after typing the modified Bash script in it.

Step # 2: Executing the Modified Bash Script via the Terminal:

Now execute this Bash script in the very same manner as explained above. The
output of this Bash script will show you the current working directory. The
highlighted portion of the output is in fact, the output of the “pwd” command.

Conclusion:

This article gives a very good idea of how you can execute a command that is
stored within a variable in Bash and can get the same output as you would have
gotten if you ran the command independently.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
