





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash How to Write a Variable to a File

2 years ago
by Karim_Buzdar
Apart from being a command-line interpreter, Bash is a very interesting
programming language as well. It has so many different aspects that can be
explored for mastering oneself in Bash programming. In this article, we will
learn the method of writing a variable to a file in Bash using Ubuntu 20.04.

Method of Writing a Variable to a File in Ubuntu 20.04

For demonstrating the method of writing a variable to a file, we would like to
show you the scenario in which the terminal asks the user about his Biodata
such as name, age, date of birth, etc. and stores each of these entities in a
separate variable. All of these variables are then written on a text file. For
doing this, you will have to proceed as follows:
First of all, we will be writing a Bash program that is capable of taking user
input and saving it in a text file. For that, we need to go to the File Manager
as highlighted in the image shown below:
The File Manager will directly take us to the Home directory where we will
create our Bash file so that it is easily accessible. For creating a Bash file
over there, simply right-click in the Home directory and create a document with
the Empty Document option. Now rename that document according to your choice.
For this particular case, we have named it as VarFile.sh as shown in the
following image:
Now open this file by double-clicking on it and write the mandatory first line
i.e. “#!/bin/bash” to depict that it is a Bash script.
After doing this, type the code or script shown in the image below in your
newly created Bash file. This script is asking the user about his details one
by one. It takes the name, place of birth, date of birth, age, and occupation
of the user as an input. The echo command in this script is used to display
messages on the terminal whereas the read command is used to store the input
provided by the user in the respective variables. Once the user has provided
all the inputs, this script stores the values of all these variables to a text
file named BioData.txt. When the echo command followed by a variable is used
with “>>” symbol followed by a file name, then it aims to store the value of
that variable in the specified file. So, basically what we are trying to do is
to save all the values that were provided by the user in a single text file by
writing their respective variables to that file. Also, we have enclosed the
variables in double quotes so that they are treated exactly as variables. When
a variable is written within single quotes, then it is treated as a string.
Moreover, whenever you want to access the value of a variable, you must type
the “$” sign before it, otherwise, you will not be able to access its value.
Once you have typed this script in your Bash file, you need to save it and
close it. After closing the file, launch the terminal in Ubuntu 20.04 and type
the following command in it to execute the Bash script that you have just
created:
bash VarFile.sh
Here, you can replace VarFile with whatever name you have given to your Bash
file.
As soon as this script will execute, you will be asked to type your name as
shown in the following image:
After entering your name, you will be asked to enter your place of birth.
Then the script will ask you to provide your date of birth.
Once you have provided your date of birth, you will be asked to enter your age.
Lastly, you will be asked to enter your occupation. This flow of inputs is
right according to the script that we have just created.
Once you have provided all the inputs, you will notice that a new text file
named BioData.txt has been created in your Home folder. You can verify it by
taking a look at the image shown below:
Now you can either verify its contents by double-clicking on it or you can even
view it via the terminal. Just type the following command in your terminal to
do this:
cat BioData.txt
This command will display all the values stored in the specified file i.e. the
variables that we have written to this text file with the help of the Bash
script.
You can easily see from the image shown below that all of our variables have
been written to the specified text file:

Conclusion

By performing the steps described in this article, you can easily write as many
variables to a file as you want and hence you can use the values of these
variables later on as well.


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
