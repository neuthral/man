





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How Do I Run a Bash Script?

1 year ago
by Aqsa_Yasin
Bash is a very popular shell and command language, and it can be used with the
Linux, macOS, and Windows operating systems. This language is extensively used
for task automation and running repetitive tasks with more ease and
convenience. The programs that you write in this language are known as Bash
scripts. This discussion is focused on the different methods of running a Bash
script on an Ubuntu 20.04 machine.

Running a Bash Script in Ubuntu 20.04

Whenever you create a program in Bash, you need to execute or run it to get the
desired results. However, before running a Bash script, there is a certain
protocol that needs to be followed. If that protocol is missing from your Bash
script, then you will simply not be able to execute it. We will learn the
importance of this protocol in the appended section of our article.

Requirements of Running a Bash Script — The Importance of Shebang

In sharing the different methods of running a Bash script in Ubuntu 20.04, we
have created a simple Bash script whose name is Bash.sh that will just print a
“Hello World!” message on the terminal. This script can be seen in the image
shown below:
In this Bash script, we have used the “echo” command to print our desired
message on the terminal. However, we are concerned with the first line of this
Bash script, i.e., #!/bin/bash. This line is called Shebang, and it is also
known as a prerequisite for running a Bash script. The importance of this line
can be realized from the fact that when your Bash script is executed, your
system looks for this particular line to distinguish a Bash script from any
other file type.
Therefore, if this line will be missing from your Bash script, your system will
never know that you are trying to run a Bash script, and unfortunately, your
specified Bash script will never be executed. Thus, whichever Bash script you
are trying to create on any operating system, you must begin with Shebang.

Different Methods of Running a Bash Script

There are four different methods of running a Bash script in Ubuntu 20.04, and
we will discuss the following methods in detail:
Method 01: By Making the File Executable
As the name of this method says, you will first need to make your Bash script
executable which can be done by running the following affixed command:
$ chmod u+x Bash.sh
Alternatively, you can also run the command shown below to make a Bash script
executable:
$ chmod 744 Bash.sh
Running either of the commands, as mentioned above, will not generate any
output on the terminal. Moreover, Bash.sh in both of the commands stated above
represents the name of the Bash file that we want to make executable. You can
replace it with the name of any of the Bash scripts that you want to run after
making them executable.
Now, when we have made our Bash script executable, we can run it any time we
want just with the help of the following affixed command:
$ ./Bash.sh
An important thing to be stated is that making a Bash script executable is a
one-time process. After executing a Bash script, you can run it as many times
as you want without making it executable every time. However, if you make any
changes to your Bash script, then you will have to make it executable again
before running it for your changes to take effect.
The output of our Bash script, i.e., the “Hello World!” message, is shown in
the image below:
Method 2: By Using the “bash” Keyword
You can use this method if you wish to bypass the command of making the Bash
script executable, i.e., if you wish to run your Bash script directly without
having the need to make it executable first. You just have to execute the
following affixed command:
$ bash Bash.sh
Here, “bash” represents the keyword that does the actual magic. This keyword
combines the functionality of making a Bash script executable and running it.
Therefore, once you run the command mentioned above, your Bash script will
immediately run. Hence, displaying the output shown in the image below on your
terminal: 
Method 3: By Using the “sh” Keyword
Again, just like Method # 2, this method can be used if you do not want to make
a Bash script executable before running it. Instead, you want to run it
directly. To achieve this objective, you will have to run the following affixed
command:
$ sh Bash.sh
Here, the “sh” keyword integrates the functionality of making a Bash script
executable and running it. As soon as you run the command, as mentioned above,
your specified Bash script will be executed, which in our case was Bash.sh.
Therefore, we have received the message, “Hello World!” on our terminal, as
shown in the image below:
Method 4: By Using the GUI of Ubuntu 20.04
As computer users, we all understand that not all of us are fond of the famous
command-line interface of Linux-based systems. There are still some users who
prefer to use the convenient graphical user interface (GUI) where everything
seems quite simple and intuitive. They never get lost while performing their
desired tasks on their system. This is exactly why we decided to share the GUI-
based method of running a Bash script on an Ubuntu 20.04 system.
For this method, you first need to locate your Bash script file by going to the
File Manager of your system. If your system is set to its default settings and
you have never changed them before, then you will not have to do anything else
but double-click on your Bash script file. As soon as you do that, you will be
presented with a dialogue box from which you simply need to click on the Run in
Terminal option as highlighted in the following image:
Right after doing that, your selected Bash script will immediately run in the
terminal, and it will display the intended output as shown in the image below:
However, if your default system settings are modified, then you can just go to
the Preferences in your File Manager. After that, you need to switch to the
Behavior tab, from which you need to go to the Executable Text Files section.
Finally, you will have to select the “Ask what to do” option to move forward
with the method that we have just discussed. Once you follow this procedure,
your system will always ask you what you want to do with your executable files
as soon as you double-click on them.

Conclusion

This article shared all the methods to run a Bash script on an Ubuntu 20.04
system. With these methods, you can run your Bash scripts very conveniently.
Moreover, you can choose any of these methods for running your Bash scripts
without any worries because all of these methods will produce the same results.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
