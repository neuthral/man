





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash text and background printing in different colors

4 years ago
by Fahmida_Yesmin
A terminal is a very important application for any Linux operating system. It
is mainly used to execute different commands for installing or uninstalling an
application, doing input and output operations etc. Terminal has default text
and background color.  The user can make the terminal attractive by changing
the color of text and background. These types of tasks can be done easily by
using some color codes and settings. This article will help you to learn the
ways by which you will be able to change bash front and background colors with
a different look.
Before using this tutorial, you have to know some basic information about color
codes and settings. There are some special shell variables which are used to
control the bash prompt, such as, PS1, PS2, PS3 etc. PS1 is the default
variable to store the primary prompt. By default, the command prompt is set to
[\[email protected]\h \W]\$. Every backslash-escaped character of bash prompt
has the special meaning which are explained below.

* \u indicates the username of the current user.
* @ indicates the current times in 12 hours am/pm format
* \h indicates the hostname.
* \W indicates the current working directory.
* # indicates root user if the UID is 0, otherwise, $ will display.

Run the following command to display the current bash prompt.
$ echo $PS1
You can change the current bash prompt default format, font color and
background color of terminal permanently or temporary. You have to edit the
~/.bashrc file for permanent change or modify the shell variables mentioned
above for a temporary change.
Many color codes are available in bash to change the color of text or
background. Some of them are mentioned below.

Color  Code for making normal color Code for making Bold color
Red    0;31                         1;31
Green  0;32                         1;32
Blue   0;34                         1;34
Black  0;30                         1;30
Yellow 0;33                         1;33

How these color codes can be applied in the bash terminal is shown in this
article by using some simple examples.

Example-1: Changing bash prompt in different format and color

When the user wants to change the bash prompt color by a particular color then
he/she will need to initialize any special shell variable likePS1 with the
color code. The following first command will set the text color of the prompt
to blue and the next command will set the color to red. Here, 34 is the
bluecolor code and 31 is the redcolor code.
$ export PS1='\e[0;34m\[email protected]\h:\W$\e[m'
$ export PS1='\e[0;31m\[email protected]\h:\W$\e[m'
Output:

Example-2: Setting different colors in different parts of the bash prompt

If you want to set multiple colors in different parts of bash prompt then you
have to modify the shell variable like the following command. You can set bash
prompt text according to your choice. The following command will set the
usernamewith blue color, ‘~’ symbol with yellowcolor and ‘$’ symbol with red
color.
$ export PS1='\[\e[0;34m\u\] \[\e[0;32m\W\] \[\e[0;34m\]\[\e[0;31m\]$ \[\e
[1;31m\]'
Output:

Example-3: Changing the text color of the terminal temporary

White color text displays in the terminal by default. You can change the text
color of the terminal according to your choice by using the color code.
Suppose, if you want to print any text in yellow color in the terminal then run
the following command.
$ echo $'\e[1;33m'Welcome to linux hint$'\e[0m'
Output:

Example-4: Using a variable to apply text color

It is easier to remember the variable name rather than the color code. So, if
you declare multiple variables with color codes it will be helpful for the
users to reuse the color multiple times in the script. Run the following
commands from the terminal. Here, the first three commands will declare three
variables named, Red, Green, and Blue. The fourth command will print the text,
“I like chocolate cake” in blue color.
$ Red=$'\e[1;31m'
$ Green=$'\e[1;32m'
$ Blue=$'\e[1;34m'
$ echo "$Blue I like chocolate cake "
Output:

Example-5: Changing text and background color from the terminal menu.

The easiest way to change text and background color of the terminal is using
terminal Edit menu.  Open any new terminal and open Preferences dialog box by
selecting Edit and Preferences menu item.
Click on the Colors tab of the Preferences dialog box. There is an option for
text and background color and that is “Use color from system theme”. This
option is enabled by default. Make it disable to set the custom text and
background color. Select Custom from the drop-down list of Built-in
scheme.Click on Default color button under Background. A new dialog box will
appear.
From this dialog box, you can select or type your desirable color code to set
the terminal background color and click on the Selectbutton.
Next, Click on the Close button of the Preferences dialog box and see the
effect. Now, if you close the terminal and re-open again then you will see the
background color in the terminal. So, the background color is changed
permanently.
Like the previous way, click on Default colorbutton under Textand select your
desired text color from the Choose Terminal Text Color for the terminal. Now if
you type any text in the terminal then the text will be printed in your
selected color.
The preferences dialog box has many other options to change the looks of the
terminal like bold color, cursor color, highlight color etc.

Conclusion

The Linux user can not image to do any task without a terminal. It is not
necessary to change the text or background color of the terminal for doing any
task. But the user changes the colors for mental satisfaction or surprises the
friends and colleagues. Many ways are shown in this article to change text and
background colors. Using the menu of the terminal is the easiest way to do
these types of task. If you are new in this area and want to change the colors
of our terminal then try the examples of this article and apply colors in the
terminal window as you like.


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
