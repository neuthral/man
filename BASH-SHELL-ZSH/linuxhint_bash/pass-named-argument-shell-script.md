





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How do you pass a Named Argument in a Shell Script?

1 year ago
by Aqsa_Yasin
The shell scripts in Linux allow you to write programs with hard-coded values
and programs that can take user inputs at runtime. These user inputs are known
as parameters or arguments. All of us are generally familiar with passing
normal arguments to the shell scripts. However, you might sometimes feel the
need to pass “Named Arguments” to your shell scripts. This article will guide
you more about what exactly are named arguments and their need in shell
scripts. After that, we will share an extensive example of passing the named
arguments to a shell script in Ubuntu 20.04.

Named Arguments in Shell Scripts in Ubuntu 20.04

By now, we clearly understand that we can easily write such shell scripts in
Ubuntu 20.04 that are capable of taking arguments as input from the user while
executing these scripts from the terminal. However, a different type of
arguments known as “Named Arguments” is also commonly used within the shell
scripts. A named argument is the one that is symbolized by a “name-value” pair.
This “name-value” pair is defined within the shell script, and the
corresponding argument is passed in the same manner while executing the script
as you pass the normal arguments.
Then what is the significance of using the named arguments in shell scripts?
Well, at times, you define the arguments in your shell scripts, but while
running those scripts, you might not necessarily need to provide all of those
arguments. The named arguments allow you to skip the values of as many of these
arguments as you want while running your script. In that case, if you had used
the normal arguments, your system would have rendered an error message and
would not have allowed you to proceed with the execution of your script if you
would have skipped any pre-defined arguments within your script.
Moreover, at times, you might also change the order of passing the arguments
while running a shell script, i.e., you pass the arguments in random order
instead of the one that is followed while declaring the variables within your
shell script. The named arguments easily let you do this, whereas on the other
hand, if you would have used the normal arguments in this situation, then
again, an error message would have been generated because of not following the
correct order of arguments. Therefore, you can say that the named arguments
provide more flexibility to the users while providing inputs instead of
restricting them.
Now, when you realize the importance of using the named arguments in shell
scripts, let us see how we can use these arguments within a shell script on a
Ubuntu 20.04 system.

Example of Passing Named Arguments to a Shell Script in Ubuntu 20.04

For passing named arguments to a shell script in Ubuntu 20.04, we have designed
a shell script that is shown in the image below. We will be executing this
shell script with different arguments or input values in this section.
In this shell script, we have used the built-in “getopts” function in the shell
inside a while loop. This function basically takes named parameters as input
from the user. Then, we have defined three different cases, i.e., “n, a, and g”
corresponding to our variables “Name, Age, and Gender” respectively. These
cases are defined against the “flag” variable upon which our case-esac
statement will execute. The case-esac statement in the shell is basically an
equivalent of the Switch statement in C. Then, inside the case-esac block, we
have listed all the three cases that were declared earlier, i.e., n, a, and g.
Against each case, we have declared a variable that equals the argument
provided by the user as an input while executing the script. Each argument
provided by the user will be assigned to the relevant variable every time this
script will be executed. Then, we finally have three “echo” commands that are
there to print the values of the variables name, age, and gender, respectively.
After designing this script, we will first execute it with normally named
arguments in the correct order as follows:
$ bash Named.sh –n Aqsa –a 27 –g Female
Here, Named.sh represents the name of our shell script. Moreover, you can see
from this command that we have listed the flags first, followed by their
respective arguments to be passed. Also, you can clearly notice that we have
passed these arguments in the exact order as they were defined in our shell
script.
Now when this shell script is executed, you will be able to see the values
assigned to all of your named parameters on the terminal, as shown in the image
below:
Once we have executed this script in the normal flow, we can try out a little
experiment by executing this shell script with the same input values but in a
slightly different order, as shown in the following command:
$ bash Named.sh –n Aqsa –g Female –a 27
You can see in this command that we have changed the order of the gender and
age arguments from the one that was defined initially in the shell script. Now,
we will try to find out if these values are correctly assigned to our named
arguments or not.
When this command is executed, you will be able to see from its output that
regardless of the order in which the arguments are passed while executing the
shell script, they will still be assigned to the correct variables as shown in
the image below:
In some situations, a user might not want to reveal his/her age. In that
situation, he/she will execute this shell script in the following manner:
$ bash Named.sh –n Aqsa –g Female
In the output of this shell script, when it is executed with the arguments
shown above, you can clearly see that our system has not generated any error
messages; rather, it has smoothly executed our script with the provided
parameters while leaving the Age variable blank.
In the same manner, you can also try skipping the Gender variable while only
providing the value for the Name variable in the manner shown below:
$ bash Named.sh –n Aqsa
The corresponding output for this command is shown in the following image:
Finally, we will try to execute this script without providing any arguments as
follows:
$ bash Named.sh
Again, you can see from the following output that no error message is
generated; rather, our script has executed successfully even without any
provided arguments.

Conclusion

From the detailed example discussed in this tutorial, we can conclude that it
will still be executed successfully regardless of the order of the named
arguments provided to a shell script. Moreover, even if you will not provide
any arguments to your script, it can still be executed without any errors.
However, the only thing you need to be careful about while passing named
arguments is using the correct flag followed by its corresponding value while
executing your shell script.


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
