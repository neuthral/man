





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How do I Exit a Bash Script?

1 year ago
by Omar_Farooq
You may have encountered many situations when you have to quit your bash script
upon some inconvenience. There are many methods to quit the bash script, i.e.,
quit while writing a bash script, while execution, or at run time. One of the
many known methods to exit a bash script while writing is the simple shortcut
key, i.e., “Ctrl+X”. While at run time, you can exit the code using “Ctrl+Z”.
This guide will show how the batch script can be quitted using the different
exit clauses while executing. Let’s get started by logging in from the Ubuntu
20.04 system first and opening the shell using “Ctrl+Alt+T”.

Example 01: Using Exit 0

The first method we have been utilizing in this example is to use the “exit”
statement in the bash script. Create a new file in the shell with the help of a
“touch” command and open it in any editor.
The read statement is widely known to get input from the user. Here it will
take integer values at run time and save them to the variable “x”. The “if”
statement has been checking a condition. If the value of “x” entered by a user
is equaled to 5, it will display that the number is matched via the echo
statement. The “exit 0” clause has been used here. After executing the “echo”
statement, the bash script will be quitted, and no more execution will be
performed due to “exit 0”. Otherwise, if the condition doesn’t satisfy, the
“echo” statement outside of the “if” statement will be executed.
Run your bash file with the help of a bash query in the shell. The user added 4
as input. As 4 is not equal to 5, it doesn’t run the “then” part of the “if”
statement. So, no sudden exit will happen. On the other hand, the echo
statement outside of the “if” statement executed states that “Number doesn’t
match..” and the program ends here.
$ bash bash.sh
Run the same code once again with the bash command. The user added 5 this time.
As 5 satisfies the condition, the “echo” statement inside the “then” clause was
executed. After that, the program stops quickly due to the use of “exit 0”.
$ bash bash.sh

Example 02: Using Exit

Instead of using “exit 0”, you can simply use “exit” in your bash script to
exit the code. So, open the same file and update your code. Only the “exit”
clause has been changed here, i.e., replaced by “exit”. The whole file remained
unchanged. Let’s save the code first using the “Ctrl+S” and quit using “Crl+X”.
Let’s execute it to see if it works the same as the “exit 1” clause does or
not.
Run the bash file “bash.sh” in the terminal by utilizing the command shown in
the attached screenshot. The user entered the value “6” and it didn’t satisfy
the condition. Therefore, the compiler ignores the “then” clause of the “if”
statement and executes the echo clause outside of the “if” statement.
$ bash bash.sh
Run the same file once again. This time the user added 5 as satisfying the
condition. Thus the bash script exits right after executing the “echo” clause
inside the “if” statement.
$ bash bash.sh

Example 03: Using Exit 1

You can also use the “exit” clause to exit the bash script while stating 1 with
it at run time. So, open the same file and update your code as we have done
before. The only change is “exit 1” instead of “exit” or “exit 0”. Save your
code and quit the editor via “Ctrl+S” and “Ctrl+X”.
At first execution, the user added 6 as input. The condition doesn’t satisfy
and commands within the “if” statement won’t be executed. So, no sudden exit
happened.
$ bash bash.sh
On the second attempt, the user added 5 to satisfy the condition. So, the
commands within the “if” statement get executed, and the program exits after
running the “echo” clause.
$ bash bash.sh

Example 04

Let’s make use of the “exit 1” clause in the bash script upon checking
different situations. So, we have updated the code of the same file. After the
bash support, the “if” statement has been initialized to check if the currently
logged-in user, i.e., “Linux” is not the root user. If the condition satisfies,
the echo statement within the “then” clause will be executed, and the program
will exit right here. If the currently logged-in account is a root user, it
will continue to execute the statements outside of the “if” statement. The
program will continue to get two inputs from a user and compute the sum of both
integers. The calculated “sum” will be displayed, and then the program will
exit.
As the “Linux” account is not a root user of our Ubuntu 20.04, the execution of
this code has only executed the “if” statement and clauses between it. The
program quits after this.
$ bash bash.sh

Example 05: Using “set -e” Built-in

The “set –e” built-in is widely known to exit the program upon encountering the
non-zero status. So, we have added 3 twin-named functions with 1 echo statement
and a return status clause in each. The “set +e” is initialized before calling
the first two methods, and “set –e” is used after that, and two functions are
called after that.
Upon execution, both show1 and show2 function’s echo statements will run, and
the program will not quit. While after “set –e” the program quits after the
execution of the show2() method’s echo statement as it encounters “return 1”.
The method show3 will not be called after that.
Upon running this code, we got the output as expected. Upon encountering the
return 1 status, the program stopped without executing the “show3()” method.
$ bash bash.sh

Conclusion

This guide covers all the possible ways to exit any bash script while writing,
executing, or running. Thus, try to implement each example covered in this
article to get a more clear understanding.


About the author


Omar Farooq

Hello Readers, I am Omar and I have been writing technical articles from last
decade. You can check out my writing pieces.
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
