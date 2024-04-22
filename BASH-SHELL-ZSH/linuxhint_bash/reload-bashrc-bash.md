





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Reload bashrc in Bash

9 months ago
by Sidratul_Muntaha
Bash is a UNIX shell and command language that you’ll find on almost all Linux
distros. First released in 1989 by Brian Fox, Bash has been the default shell
for most Linux distros. The name “Bash” is actually an acronym for “Bourne
Again Shell”, an intended pun of the Bourne shell it replaces.
In this guide, we’ll have a quick look at bashrc and how to reload it after
making any changes.

The bashrc Script

The bashrc is a shell script for the Bash shell. Bash will run the commands
within bashrc every time it runs. It’s basically a shell script to initiate a
shell session.
The bashrc file can contain a variety of codes and commands. For example, you
can set_JAVA_HOME (for working with Java apps), use bash aliases to create_your
own_custom_command, manage Bash_environment_variables like PATH, etc. You can
also use_bashrc_to_colorize_your_console_output!
The file is located at the following location.
$ ~/.bashrc
As the location suggests, the bashrc file is unique for each user. Making
changes won’t affect anyone on the system. However, there are other scripts
that Bash loads during startup. For example, bash_profile.
There are various types of bashrc files present throughout the system.

* /etc/skel/.bashrc: This file provides the default copy for every new user in
  the system.
* /home/<username>/.bashrc: This is the user-specific file that will be loaded
  each time the user starts a bash session.
* /root/.bashrc: It’s dedicated to the root user. Whenever root opens the
  shell, it will be used.


Why Reloadbashrc

When a Bash shell session is launched, it reads all the associated
configurations and scripts. After that, Bash doesn’t read them again (unless
commanded to). This is why you’ll be recommended to restart the Bash session to
take the bashrc changes into effect.

Editing bashrc

The bashrc file is a text file containing Bash commands. You can use any text
editor to edit this file. For example, we can use nano or vim for editing on
the console UI.
$ nano ~/.bashrc
$ vim ~/.bashrc

Reloadingbashrc

After you’ve made changes, save the file and close the text editor. As
mentioned earlier, Bash doesn’t check for bashrc changes after the session
starts. Running the following command will tell Bash to reload bashrc:
$ source ~/.bashrc
The key here is the source command. It’s an integral shell instruction. It
tells the shell to load (read and execute, basically) commands from the file
specified. Remember that bashrc is a bash script. With this command, Bash re-
runs the script. All the changes made are applied automatically.
Here’s a more in-depth guide on using_the_Linux_source_command_with_examples.

Final Thoughts

This guide successfully demonstrates reloading the bashrc file. Bash comes with
the source command for this purpose. It loads all the shell commands of the
file specified into the current Bash session. Bash will load the updated bashrc
file automatically next time it starts.
Bash is also a robust scripting language that can automate a lot of tasks in
the Linux environment. Interested in beginning your journey with Bash
scripting? Check out this guide on Bash_programming_syntaxes_and_variables.
Happy computing!


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
