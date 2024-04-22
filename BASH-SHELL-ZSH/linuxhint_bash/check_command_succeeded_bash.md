





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Check if a Command Succeeded in Bash

3 years ago
by Sidratul_Muntaha
Whether you’re writing a script or just being curious, it’s useful to know that
the command succeeded without any issue. Personally, bash scripting is the
place where this feature is most needed. When you’re scripting a series of
commands and the previous output impacts the later, it’s better to verify if it
worked.
In this article, I’ll be showcasing a number of ways you can verify if your
bash command was successful. There’ll be script examples that’ll showcase its
usage. However, depending on what command you run, the verification may require
different tactics.

Checking command Succeeded

Whenever a command runs, the return value of the command is stored in a
specific bash variable. For the first example, let’s run the package manager to
update the system. In my case, it’s Ubuntu, so the command would be something
like this.
$ sudo apt update && sudo apt upgrade -y
Here, from the output, we can easily say that the command ran successfully.
Now, every command run in bash shell returns a value that’s stored in the bash
variable “$?”. To get the value, run this command.
$ echo $?
If a command succeeded successfully, the return value will be 0. If the return
value is otherwise, then it didn’t run as it’s supposed to. Let’s test it out.
Run the same update command but this time, interrupt the command by pressing
“Ctrl + C”.
Now, check the value of the bash variable.
$ echo $?
The value is not 0, so there’s definitely an error. Here, we forced the command
to break. How could this be useful in bash scripts? Here’s a quick example of
how to use it on the bash script. Save the script as a text file with .sh as
the file extension.
#!/bin/bash
<command>
if [ $? -eq 0 ]; then
   echo OK
else
   echo FAIL
fi
Make the file executable.
$ chmod +x demo.sh
Now, run the script.
$ ./demo.sh
After running any command, bash will update the value of the variable. In this
case, after running the echo command, we can determine if it ran successfully
or not. Swap the echo command with anything you like and voila!
Here’s another interesting method that can confirm if the command succeeded.
It’s just a one-line command that’s very simple.
$ <command> && echo SUCCESS || echo FAIL
Here, the command is split into two sections by the “||” sign. If the first
command runs successfully, the first echo command must run. Otherwise, the
second echo command will run. Let’s check it out with an example.
$ sudo apt update && echo SUCCESS || echo FAIL
The first part didn’t succeed, so the first echo command was omitted. Instead,
the second echo command ran, indicating that the first part didn’t run
successfully. What if it ran successfully?
The first echo command was activated.
Here’s another example of a bash script.
#!/bin/bash
if <command>; then
     echo “Success”
else
     echo “Failure, exit status: $?”
fi
Run the script.
$ ./demo.sh
If the command didn’t succeed, the output would be different.
Which bash script to use? I strongly recommend the first one where the command
is run first, then the value of “$?” is extracted in a variable and then,
perform whatever you want depending on the value of the variable.

Final thoughts

Bash is a powerful shell with a strong scripting feature. If you want to know
if the previously-run command succeeded, these are some of the most reliable
methods.
Which method to use? It depends on what’s the goal you want to achieve. For
usage in the terminal and command line, using the single command example is the
best way to go. As for the bash scripting, feel free whichever method serves
you the best, especially the first script example I demonstrated.
Want to make your life easier with bash? Learn_more_about_how_to_set_bash
aliases_and_some_popular_and_handy_aliases.
Enjoy!


About the author


Sidratul Muntaha

Student of CSE. I love Linux and playing with tech and gadgets. I use both
Ubuntu and Linux Mint.
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
