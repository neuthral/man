





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash PS1 customization examples

1 year ago
by Fahmida_Yesmin
The special shell variable is used to control the bash prompt. These shell
variables are PS1, PS2, PS3, and PS4. Each variable is used for specific
purposes. The value of these variables is executed as a command before
displaying the primary prompt. The PS1 variable contains the value of the
default prompt. It is used to change the looks and environment of the shell
command prompt. Different examples of using the PS1 variable have been shown in
this tutorial.

Commonly used escape sequences:

The primary command prompt PS1 displays when the interactive shell executes.
The prompt string can be customized by using different types of backslash-
escaped special characters. The most commonly used backslash-escaped characters
are given below.

backlash-escaped Character Purpose
\u                         It is used to display the current username.
\h                         It is used to the name of the computer name.
\H                         It is used to the name of the hostname.
\d                         It is used to display the date with weekday name,
                           month name, and date.
\w                         It is used to display the full path of the current
                           working directory.
\W                         It is used to display the last fragment of the
                           current working directory.
\t                         It is used to display the current time in 24-hour
                           format.
\T                         It is used to display the current time in 12-hour
                           format.
\@                         It is used to display the current time in 12-hour
                           format with AM/PM.
\n                         JIt is used to add the new line.
\e                         It is used to add an ASCII escape character.
\v                         It is used to display the version of the bash.
Jill                       Smith
\V                         It is used to display the version of the bash with
                           patch level.


Check the default value of PS1

The default value of PS1 contains three information. The username, hostname,
and the full path of the current working directory. Run the following command
to display the default values of the PS1.
$ echo $PS1

Output:


Example-1: Display the date and time

You can add the date and time values with the command by using \d and \t
escaped characters. Run the following command to set the PS1 values to display
the username, date, and time values into the command prompt. Here, the export
keyword is used to change the current command prompt temporarily.
$ export PS1="[ \[email protected]\d \t ] $ "

Output:

If you re-open the terminal, then the default command prompt will appear. To
save the PS1 value permanently, open the ~/.bashrc file by using any text
editor. Here, nano editor has been used.
$ sudo nano ~/.bashrc
Add the following line at the end of the file, save the file and quit from the
editor.
PS1="[ \[email protected]\d \t ] $ "
Run the following command update the current command prompt for adding the line
in the ~/.bashrc file.
$ source ~/.bashrc

Output:

Run the following command to display the command prompt into multiple lines
using the ‘\n’ escaped character. It is useful for long command prompt.
$ export PS1="[\d]\n\[email protected]\h: $ "

Example-2: Change the background and foreground color

Different color values can be used to set different colors for the background
and foreground of the command prompt. The list of the background and the
foreground color names with values is given below.

Background Colors Foreground Colors
Black = 40        Black = 30
Red = 41          Red = 31
Green = 42        Green = 32
Yellow = 43       Yellow = 33
Blue = 44         Blue = 34
Purple = 45       Purple = 35
Cyan = 46         Cyan = 36
White = 47        White = 37

Run the following command to change the background color of the command prompt
to purple. Here, ‘\e’ escaped character with color value 45 has been used to
set the purple background. The ‘m’ character has been used to set the sequence.
$ export PS1="\e[45m\[email protected]\h :\w$ \e[m"

Output:

Run the following command to change the foreground color of the command prompt
to white. Here, ‘\e’ escaped character with color value 37 has been used to set
the white foreground. Like the previous command, the ‘m’ character has been
used to set the sequence.
$ export PS1="\e[0;37m\[email protected]\h :\w$ \e[m"

Output:


Example-3: Display emoji in the command prompt using the script

The emoji can be added to the command prompt in different ways. The bytes value
of the emoji character has used in this example. Run the following command from
the terminal to display the emoji in the command prompt based on the exit
status value.
$ export PS1='\u ( $(if [[ $? == 1 ]]; then printf "\xF0\x9F\x99\x8D"; else
printf "\xF0\x9F\x99\x8E"; fi) )\[\e[0m\] :\w $ '

Output:


Example-4: Display emoji in the command prompt using the script

The way to generate emoji is by executing a bash file, as shown in this
example. Create a bash file with the following script. The script will check
the type of the currently logged-in user. If the current user is the normal
user, it will display an emoji with a start face and if the current user is the
root user, it will display an emoji with a sunglass face.

user.sh

#!/bin/bash
#Check the user
if [ $UID = 0 ]; then
    #Set emoji for root
    export PS1='😎️~:$'
else
    #Set emoji for general user
    export PS1='🤩️~:$'
fi
Run the following command to execute the above script to change the command
prompt of the current shell.
$ source user.sh
Next, run the following commands to log in as a root user and go to the folder
location of the script.
$ sudo -i
$ cd home/fahmida/bash
Run the following command again to execute the script as a root user.
$ source user.sh

Output:

According to the output, the first emoji has appeared for the normal user and
the second emoji appeared for the root user.

Conclusion:

The ways to change the default command prompt in different ways by modifying
the value of PS1 have been shown in this tutorial. Some commonly used escaped
characters have been used in the examples of this tutorial to help the readers
to know the use of PS1 for changing the current command prompt temporarily or
permanently.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
