





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


In Bash, if a Command Fails, Run Another Commands

1 year ago
by John_Otieno
Did you know that every command you run in Linux has an exit code? This is true
even if a command terminates with an error. Exit values are integer values that
range from 0 to 255. A non-zero value, i.e., a value higher than 0, indicates
the command exits with an error.
If a command executes successfully in bash, it has a 0 exit code. For command
not found, the exit code is 127. Therefore, we can use the exit code to perform
a specific action.
This tutorial will give you a few tips and tricks you can use to perform an
action based on the previous command’s exit code.

Using the OR Operator

One way to execute a command if the previous command fails is to use the OR
operator. Since an OR operator requires only one condition to be true, we can
run the following syntax:
$ command1 || commad2
In the above syntax, the second command will execute even if the first command
fails. Note that this is different from using && operator as it requires the
first command to execute successfully.
For example:
$ ping -c lhint || echo "Success";
In the above example, echo will still run despite the error caused by the name
resolution in the ping command.
Here is a screenshot illustrating this:
NOTE: You can tie multiple commands using bash operators to achieve the best
result. For example, you can allow sleep to execute only if ping and echo
execute successfully.
$ ping -c 1 linuxhint.com && echo "Success" || sleep 100;
In the example above, if either ping or echo fails, sleep does not execute.
Doing this can be helpful if the following command relies on the output from
the previous command.

Using Exit Code

Bash allows us to get the exit code of the previously executed command. To view
the exit code, enter the command:
$ echo $?
We get 0 for a command executed correctly and 127 for a command not found in
the example above.
To use the exit code for an action, we do:
#!/bin/bash
if [[$? -eq 0]];
then
        echo "Success"
else:
        echo "Fail"
fi
In the script above, we check if the exit code is equal to 0, indicating the
command executed successfully. If true, execute a command. In this case, echo
“success.” Otherwise, echo “fail.”

Conclusion

In this quick tutorial, we used bash operators and exit codes to execute a
command if the previous command fails or succeeds.


About the author


John Otieno

My name is John and am a fellow geek like you. I am passionate about all things
computers from Hardware, Operating systems to Programming. My dream is to share
my knowledge with the world and help out fellow geeks. Follow my content by
subscribing to LinuxHint mailing list
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
