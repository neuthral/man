





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


What is the difference: .bashrc and bash_profile?

2 years ago
by Sam_U
If you spend most of your time on the terminal, you might think to personalize
its appearance by changing the configuration files. If you notice that there
are two configuration files of bash shell in Linux, one is “.bashrc,” and the
second one is “bash_profile” or “.profile.”
These files are hidden and cannot be displayed using “ls” only; therefore, use
“ls -a” in the terminal to view these files.
$ ls -a
In Ubuntu, there is a “.profile” file instead of “.bash_profile,” you can use
the “.profile” file, or you can create a “.bash_profile.” Once you create the
“.bash_profile” file, the “.profile” will no longer be read by the shell.
This post’s main point is to explore these two files and clear the doubts about
them. So, let’s dig through and learn the key differences between these files.
But before discussing the configuration files, first, we must understand the
distinction of various shell interfaces because, at a time, two or more shell
interfaces can be opened.

What is the difference between Interactive and Non-interactive shells?

An interactive shell expects some interactivity from the user, for instance,
getting commands from the keyboard, while a non-interactive shell does not
expect any input from the user. Next comes the “interactive login” shell and
“interactive non-login” shells. When we open the terminal, we get an
“interactive login shell,” and it looks through the startup files. However,
when we open a shell from an already opened shell, that shell would be called
an “interactive-non-login” shell, and it reads only the “.bashrc” file.

What are bash startup files?

When we launch the “interactive login” terminal, the first file it searches for
is “/etc/profile,” the file read order is given in the following image:
After that, it searches for other files displayed in the above image and
executes the command from the file it finds first. The “/etc/profile” file sets
up the environment for all users, then it looks through “.bash_profile” and
sets up the current shell’s environment. If “bash_profile” is not present, then
it will look for “bash_login” or “.profile” files. Upon launching the
“interactive non-login” terminal, the only file it reads is “.bashrc.”

What is the difference between the “.bash_profile” and “.bashrc” files:

The “.bash_profile” file is responsible for setting up the environment using
environment variables that store information about text editor, layout
settings, etc. It executes only once when you log in to your machine. Whereas
“.bashrc” contains commands, aliases, bash functions and runs when you open the
terminal to an already logged-in system.
Most of the distributions have “.profile” in the place of “.bash_profile”; all
shells read the former while the latter only bash.

Conclusion:

Shell requires basic configuration upon launching into setting up the
environment. The “.bash_profile” will be executed when you log in to your
machine to configure your shell environment, whereas “.bashrc” will be executed
when you open the terminal and also executes when you open a new instance of
the terminal. In this post, we learned the key differences and importance of
these two configuration files.


About the author


Sam U

I am a professional graphics designer with over 6 years of experience.
Currently doing research in virtual reality, augmented reality and mixed
reality.
I hardly watch movies but love to read tech related books and articles.
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
