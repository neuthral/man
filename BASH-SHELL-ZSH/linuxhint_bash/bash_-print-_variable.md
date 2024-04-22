





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash How to Print a Variable?

2 years ago
by Karim_Buzdar
Bash scripts are an effective means of increasing efficiency in programming.
They also increase reusability to the fullest since when a Bash script is once
written, can be executed for as many times as the user wants. In this article,
our goal is to learn the method of printing a variable using Bash.

Method of Printing a Variable using Bash:

Note: We will be demonstrating this method using Ubuntu 20.04. However, you can
use any other distribution of Linux as well.
In this method, we will explain to you how you can write a Bash script for
printing a variable. For proceeding with this method, you will need to follow
the steps mentioned below:

Step # 1: Creating a Bash File:

Click on the File Manager icon located on your Ubuntu 20.04 taskbar as
highlighted in the following image:
Once you are there in the Home folder, you will need to create a Bash script
file. For doing that, right-click anywhere on space in your Home folder. Select
the New Document option from the cascading menu that appears and then choose
the Empty Document from the sub-cascading menu. When a new document has been
created in your Home folder, rename it as Print.sh. You can also have any other
name of your choice. Moreover, we have chosen the Home folder for creating this
file just to save ourselves from the inconvenience of giving the path of this
file while executing this script via terminal since the Home folder is
generally the default path of the Linux operating system. However, you can
create your Bash script file anywhere you want. This newly created Bash file is
shown in the image below:

Step # 2: Writing a Print Program in a Bash Script:

Now double click on this file to open it and type “#!/bin/bash” at the top of
this file to indicate that it is a Bash file as shown in the following image:
Type the program shown in the image below in your newly created Bash file. In
this program, we are taking a number as input from the user and saving it in
the variable num. Then we have used the echo command to print the value of this
variable. Moreover, we have also used the printf command to serve the very same
purpose. After typing in this program in your Bash file, you need to save it by
pressing Ctrl +S and then close it.
In this program, the echo command and the printf command is used to print the
output on the console. The read command is used to take input from the user
whereas the gathered input is stored in a variable followed by this command. In
this case, that variable is num. For the sake of your understanding, we would
also like to explicitly state that whenever you want to access or display the
value stored in a variable, you always have to mention the “$” symbol before
that variable as it is also used in this particular program.

Step # 3: Executing the Print Bash Script via the Terminal in Ubuntu 20.04:

Now launch the terminal in Ubuntu 20.04 as shown in the following image:
Type the following command in your terminal and run it to execute your newly
created Bash file:
bash Print.sh
This command can also be seen in the image below:
After executing this command, you will be asked to enter a number of your
choice as shown in the image below:
Type any number that you like as shown in the following image and then press
the Enter key:
As soon as you will provide your input, you will be able to see the same value
twice on your terminal i.e. once because of the echo command and once because
of the printf command. This output is visible in the image shown below:

Conclusion:

Both the echo and the printf commands can be used to print a variable while
using Bash. It entirely depends on your personal preference which of these
commands you choose to use.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
