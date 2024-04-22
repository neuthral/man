





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Export Variables in .Bashrc

2 weeks ago
by Prateek_Jangid
In Linux, users can define the local variables in Bash by default. In this
case, a user must export the variables for the child processes. That’s why
Linux supports the export commands that update the current session per the
exported variable’s updates.
Nevertheless, many users do not understand how to use the export command to the
.bashrc file. In this tutorial, we will explain a complete method to export the
variables in .bashrc and use them in scripts.

How to Export Variables in .Bashrc

Let’s start with the simple example of exporting a variable from a shell to the
.bashrc file. First, we create a .bashrc file through the following command:
touch file.bashrc

chmod +x file.bashrc
Now, create a variable and then export it in all shells. For example, set the
value of the variable named example:
example= "variable"
After that, export this variable through the following command:
export example
You can now enter the new shell. Then, check the exported variable through the
following commands:
bash

echo $example
Now, enter the following details in the file.bashrc:
Once you are done, save the file and execute it in the terminal:
./file.bashrc
The file.bashrc script exports the value from the example variable, as shown in
the previous image.

Export Variables in .Bashrc and Use Them in Scripts

First, set the value of the test as the variable. Then, export it in all
sessions:
Now, execute the script in the terminal to print the variable:
./example.bashrc
If you want to use this exported variable in other scripts, create a script
first and then enter the following details:
Finally, run the script. The system will print the exported variable in the
terminal:
./example.sh
The export_command is not limited to the scripts related tasks. It  also
includes various options. For instance, you can use the -p flag to display the
list of variables:
export -p

Conclusion

This is how you can easily export the variables in .bashrc and use them in the
scripts. The export command is easy to use and can help you to export the
variable value from the current session to all. Exporting the variables is
important because the variable value is only available for the current session.
You can use these exported values in different scripts.


About the author


Prateek Jangid

A passionate Linux user for personal and professional reasons, always exploring
what is new in the world of Linux and sharing with my readers.
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
