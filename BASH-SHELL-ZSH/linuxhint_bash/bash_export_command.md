





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Export Command

2 months ago
by Denis_Kariuki
“Bash shell offers the exportcommand, a built-in command that allows exporting
variables in a shell to make them global, such that you can access them from
another shell. With the export command, you export the environmental variables
to other shells as a child process without tampering with the existing
environmental variables. This guide discusses the Bash export command, giving
examples of how you can use it.”

Understanding the Bash Export Command

The export command has only three options.

  1. -n: used to indicate the named variables won’t be exported
  2. -p:used to list all exported variables and functions
  3. -f:used when exporting functions

Let’s have an example to understand when and where the export command comes in
handy. Suppose you are in the current shell and create a local variable named
demo1,as shown below.
If we want to access the variable’s value, we could use the echo command.
$ echo $demo1
However, if we opened another shell using the bashcommand and tried to get the
value of the declared variable in the other shell, we got nothing as an output.
This happens because the variable we created was local to the given shell. If
we want to make it global, we must export it. Let’s return to our previous
shell and export the variable using the below command.
$ exit
$ export demo1
If we go to a new shell and echo the variable, we see that we now get a value,
meaning we have access to the variable.
That’s all possible because we exported it using the export command.

Viewing Exported Variables

If you run the export command with no arguments, it will list all the exported
variables in your system regardless of the shell.
However, if you add the -poption, it will only list the exported variables in
the current shell
Notice that we have the variable we exported at the bottom of the list.

Exporting Functions

You can go beyond variables to export even functions with the export command.
To make the shell recognize that you are exporting a function, use the -fflag.
Let’s create a function, export it in the current shell, then try to access it
in another shell and see if that works.
With our function created, we can verify that it’s unavailable in the new
shell, as shown below, where it returns an error.
So, go back and export it using the -fflag.
Lastly, open a new shell and verify that our function is now global.
Bingo! You managed to export a function.

Setting Values

You can set the value of a variable using the export command. For this, you
need the syntax below.
$ export name[=value]
For instance, if we wanted to change the value of the variable we created, we
could use the below command.
Once updated, echo the variable to check if it reflects the new value.
That’s how you can manipulate other environmental variables, such as setting
the default editor. You only need to grep the currently set editor and set a
new one.
Let’s check the current default editor using the command below.
$ export | grep EDITOR
In this case, we have no currently set default editor. Let’s go ahead and set
one like vimor nanousing the command below.
$ export EDITOR=/usr/bin/nano
If we check again, we see that the variable value was modified.

Conclusion

This article has focused on understanding the bash export command and how to
use it. We’ve given various examples of how to use the export command options
to export variables and functions. Knowing how to use the export command comes
in handy when working with bash scripts. So, don’t stop here. Keep practicing!


About the author


Denis Kariuki

Denis is a Computer Scientist with a passion for Networking and Cyber Security.
I love the terminal, and using Linux is a hobby. I am passionate about sharing
tips and ideas about Linux and computing.
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
