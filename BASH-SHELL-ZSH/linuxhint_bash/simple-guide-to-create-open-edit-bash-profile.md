





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


A Simple Guide to Create, Open, and Edit bash_profile

2 years ago
by Aqsa_Yasin
The .bash_profile is used for customizing the user configuration settings. This
file is located in the home directory and is mostly hidden. The .bash_profile
files are considered as configuration scripts. They can include variable
specifications, export variables, and login commands such as mail or news
search.

Create the .bash_profile File

Open the command by a shortcut key Ctrl+Alt+T or from the side icon of the
terminal. The command is now opened. First of all, you need to create a
.bash_profile file using a touch command in the terminal shown below:
$ touch .bash_profile
This is the simplest way to create a file in a terminal, and it will not
display any message that a file has been created.

List the .bash_profile File

When you search for the .bash_profile by checking it in File Explorer, you
cannot find the file because it is hidden. On the other hand, you can search
for the newly created .bash_profile file using the list command as:
$ ls –la

Open the .bash_profile File

To open the newly created .bash_profile from the terminal, we need to simply
write the nano keyword command as follows:
$ nano .bash_profile

You will see the .bash_profile file will be opened in a new window. It has
different keys listed at the bottom, with the file name displayed at the top
center of the file window.

Edit the .bash_profile File

Now, if you want to check whether any data or information written in this
profile will be displayed on the terminal upon calling, you can do so. For
that, you have to write some code in the .bash_profile file. Write the echo
statement with the ‘FROM BASH_PROFILE’ in single inverted commas. Save this
file using the Ctrl+S key followed by tapping Y. After that, close this file by
pressing Ctrl+X, and you will be navigated to the terminal again.

Display the .bash_profile Changes

Now, to implement the changes of this file and to check the outcome of the
statement written in the .bash_profile, we need to write the simple source
command in the terminal as:
$ source .bash_profile
You will see the text written in the single inverted commas will be displayed
in the terminal.

To do some extra customization, try some other things as well. So make a new
.bashrc file using the touch command and open it using the nano command as:
$ touch .bashrc
$ nano .bashrc
Scroll down to the bottom and add some echo statement in it with some text in
single inverted commas. Save this file using Ctrl+S followed by tapping the Y
key. You can close this file using the Ctrl+X key.

Now open the .bash_profile again from the terminal using the nano execution
command.
$ nano .bash_profile

Write down the below-shown statements in the .bash_profile file. You can avoid
the hash sign statements because they are usually comments. In the ‘if’
statement, ‘-f’ refers to the existence of this file. This means that if the
.bashrc file exists, then do the following action. On the next line, the dot
followed by the listed filename refers to open this file. Now, save this file
using Ctrl+S followed by the Y key. Close it using CTrl+X.

Try the source command again for the .bash_profile file. This will execute the
.bash_profile file, and will obviously execute the .bashrc file because the
.bashrc file is linked to the .bash_profile file.
$ source .bash_profile
Every time you open the terminal, you will see the text displayed on its top
corner. This text is written in the .bashrc file due to the linkage of files.

Open the .bash_profile file and set the PATH variable in it, as displayed in
the image, and export this variable using the export keyword. Save this file
and exit.

In the command terminal, write the echo statement followed by the PATH
variable. You will see it will display the random different path locations.
These locations are mostly those that are having any script file in them. The
script file means any login script from which you can update your password.
$ echo $PATH

So when you add the password command in the terminal, it will display the text
as ‘ Changing password for Username’. After that, it will ask for your current
user password. So, add your current password. Then, it will ask for your new
password followed by retyping the new password. Through this method, you can
change your login credentials for the current user.
$ passwd

Again, open the .bash_profile file using the nano command.
$ nano .bash_profile
Add some extra echo statements in this file. After that, add another statement
having initials PS1 followed by = sign. In the inverted commas, add backslash
followed by the alphabet W and greater then > sign. This means that when the
.bash_profile file has been executed, it will customize the command terminal by
providing the space for commands. Save and close this file.

When you run this file using the source command, you will be able to see the
text written in the echo statements as output. You will see another change,
which is due to the PS1 statement. This change is ~> sign, which is used for
adding new commands.

Now add the cd command followed by double dots in this newly customized
terminal. It will direct you to the home directory, which is our set PATH.
Again adding a cd command followed by double dots will direct you to the file
system of Linux home. When you try the list command in the terminal, it will
display the list of folders.

Try the cd command followed by the ‘~’ sign, and it will direct you to the main
directory. When you list the directories, it will display the below output.

Conclusion

In this guide, you have learned how the users usually do things like: add some
directory to variable $PATH, export any variable, modify $PS1, set view colors,
add a welcome text message, etc.


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
