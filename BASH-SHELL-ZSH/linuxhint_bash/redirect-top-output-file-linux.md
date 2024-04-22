





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How Do I Redirect Top Output to a File in Linux?

1 year ago
by Talha_Saif_Malik





When a Linux user types any command into the bash prompt, the terminal usually
prints the output of the invoked command so you can read it straight away.
However, bash also permits you to “redirect” or save any command’s output in
the system.
This article will discuss three different procedures of redirecting the output
of the top command to any file.

Method 1: Single File Output Redirection

For utilizing the redirection of bash, execute any script, then define the  >
or >>  operator followed by the file path to which the output should be
redirected.

* “>>” operator is used for utilizing the command’s output to a file, including
  the output to the file’s current contents.
* “>” operator is used to redirect the command’s output to a single file and
  replace the file’s current content.

We can say that technically, this is a file redirection of “stdout,” which is
the normal display. Now, we will execute the sample example. The “ls” command
displays the content of the current directory’s folders and files after its
execution.
$ ls
ls > /path/to/file
However, this command will save the output to the specified file in the
following example rather than printing it to the terminal.
ls > /home/linuxhint/outputfile
Utilize the given command syntax for checking the content of the file.
cat /path/to/file
Now, write out the below-given command for printing the content of the “output
file” in the terminal.
$ cat /home/linuxhint/outputfile
The operator “>” overwrites the file content with the command execution output.
Instead, you can use the “>>” operator for saving the multiple commands output
in a single file. For instance, the execution of the given command will add the
system information to the specific file.
uname -a >> /path/to/file
$ uname -a >> /home/linuxhint/outputfile

$ cat /home/linuxhint/outputfile

Method 2: Redirecting terminal output to a single file

Didn’t like the idea of using the”>” or “>>” operator for redirecting output?
Don’t worry! The tee command is here to rescue you.
command | tee /path/to/file
$ ls | tee  /home/linuxhint/outputfile
The below-given tee command will overwrite the file content with the command’s
output similar to the “>” operator.
$ uname -a | tee -a  /home/linuxhint/outputfile

Method 3: The top command

System administrators also use the Linux top command to view real-time system
statistics such as load average, system uptime, running tasks, used memory,
specific information about each running process, and a summary of threads or
processes. By utilizing the -b flag, this command helps to get the information
about the currently executing processes in the system. The top command will
permit the top to function in batch mode and the -n flag to determine the
number of iterations the command should take as output.
$ top -b -n 1 > topfile.txt
All of the output resulting from the top command’s execution will be redirected
to the specified file. Now, write out the “less” command for checking the
content of the file.
$ less topfile.txt
The -n flag will send the single snapshot of executed command to the specified
file. To retrieve only the first iteration, specify the “1” after the “-n”
flag.
$ top -b -n 1 > top-iteration.txt
Utilize the “cat” command for viewing the running tasks information.
$ cat top-iteration.txt | grep Tasks

Conclusion:

In Linux, for redirecting output to a file, utilize the
”>” and ”>>” redirection operators or the top command. Redirection allows you
to save or redirect the output of a command in another file on your system. You
can use it to save the outputs and use them later for different purposes.


About the author


Talha Saif Malik

Talha is a contributor at Linux Hint with a vision to bring value and do useful
things for the world. He loves to read, write and speak about Linux, Data,
Computers and Technology.
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
