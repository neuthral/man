





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How do I know if I have bash or zsh?

1 year ago
by Talha_Saif_Malik
Usually, when you heard about Linux-based programming, it is referred to as
command-line interfaces, shells, and terminals.Bash is considered the most
commonly used shell in this regard. However, there also exist other versions of
shells, such as Z shellor Zsh.
Bash shell was introduced to replace Bourne Shell and to become the default
Linux shell. Bash is capable of performing a wide range of programming
solutions and automated tasks. In Linux, several other shells can perform
similar tasks as bash. Zsh was created after the bash shell. It has various
features that are also present in the Bash shell. However, some features make
it superior to bash, such as Plugin support, Spelling correction, Themes
bundle, CD automation, etc. If you are a Linux user, you do not have to install
Zsh separately since it is included by default in the Bash shell.
Now, coming to the article’s main subject, how will you know that you have bash
or zsh?
The answer is quite simple. Use the “–version” command to confirm the existence
of both shells on your Linux system.

Finding the version of bash and zsh

Write out the below-given command to check the bash version on your system.
Execution of this command will also ensure that bash exists on your system or
not.
$ bash --version
For checking zsh, utilize the below-given command:
zsh --version

Finding current shell

For beginners working in a terminal, sometimes it can be confusing to guess the
shell they are currently working on. So we will assist you too in the process
of finding the current shell.
Execute the below-given command in your shell.
$ echo $0
If you are active in your bash shell, it will show you the “bash” resulting
from the above command execution.
On the other side, for zsh, it will print out “zsh” on the terminal.

Finding the path of bash or zsh shell

To know the path of your zsh or bash shell, execute the below-given command.
$ which bash
which zsh

Switching bash to zsh

To switch from bash shell to zsh. For that, in the terminal, we execute the
“chsh” command in this way:
$ chsh -s $(which zsh)
Now close the terminal, and reboot the system to take the effect of the
changes. After reboot, open up a terminal window. Now, you are all ready to
work in zsh shell.

Switch zsh to bash

To switch zsh to bash, specify “bash” in the “chsh” command and execute it on
the terminal.
% chsh -s $(which bash)
Again, reboot the system after closing the terminal, and after reboot, you will
see that you are switched to the bash shell.

Conclusion

For Linux users, bash and zsh are extremely useful shells. Both shells offer
various beneficial characteristics. Of course, the user can choose the shell he
or she wants to use based on the task’s requirement, but in such case,
confusion arises in the minds of beginners terminal users that whether they are
working in zsh or bash? In this post, we have shown you various methods to know
the question to this question. Employ any of these methods and get to know your
current shell in few seconds.


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
