




















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Change Colors on LS in Bash

5 years ago
by Shahriar_Shovon
If you work on the command line interface of Linux most of the time, then
changing the color of ls command might be something that you always wanted.
Perhaps you don’t like the default colors or they are hard to read for your
eyes.
If you’re using a Linux graphical desktop environment such as GNOME 3 or KDE 5
Plasma, you can just change the theme of your Terminal application such as
GNOME Terminal or Konsole. But if you’re using a server operating system like
Ubuntu Server that don’t have any graphical user interface, then changing
themes like you do in a graphical Terminal application is not easy.
In this article, I will show you how to change the colors of ls command. I am
going to use Ubuntu Desktop and Server for the demonstration. But you can use
any Linux distribution of your choice. Let’s get started.





Enable Colors of ls Command

By default, on most Linux distributions these days has ls colors enabled. If
your Linux distribution is an exception to this default setting, then you may
run ls with –color option to enable colored output.

The LS_COLORS Environment Variable

LS_COLORS environment variable is responsible for the colors that you see when
you run the ls command.
You can print the LS_COLORS variable with the following command and see how the
contents of the LS_COLORS environment variable looks like.
$ echo $LS_COLORS
To change the colors, what you usually do is change these key value pairs and
update the LS_COLORS environment variable.

Exporting, Editing and Updating the LS_COLORS Environment Variable

Let’s first see how to export the LS_COLORS variable.
You can run the following command to export LS_COLORS variable to the end of
your ~/.bashrc file:
$ dircolors -b >> .bashrc
Now edit the ~/.bashrc file with any text editor. I am going to use vim text
editor.
$ vim ~/.bashrc
Once the file is opened. Go to the end of the file. You should see something
like the marked section of the screenshot below.
What you want to do is, edit the value of specific key, or add new key value
pair to the end of the LS_COLORS environment variable. Then save the file and
run the following command to apply the new settings.
$ source ~/.bashrc
Don’t worry, your changes will survive reboots.

Basics of Terminal Color Codes

In this section, I will talk about how LS_COLORS color codes are formatted. It
is a must have knowledge to modify LS_COLORS environment variable.
LS_COLORS key value pairs are separated by colon ( : ). The keys are predefined
for the most part. Only the color values change.
The values have 2 or more parts separated by semicolon (;).
For example, di=0;34, here di means the color should be applied to directories.
0 means it’s a normal color, and 34 means the color is green.
If you want bold green font for the directories, the color code should be
di=1;34. Here 1 means bold font.
If you also want to specify a background color, you can append the code for it
as well. For example, if you want yellow normal font on red background, then
the code should be di=1;33;41
List_of_Available_Color_Codes:

31  = red   40  = black  0   = default colour
             background
32  = green 41  = red    1   = bold
             background
33  = orange42  = green  4   = underlined
             background
34  = blue  43  = orange 5   = flashing text
             background
35  = purple44  = blue   7   = reverse field (exchange foreground and background
             background    color)
36  = cyan  45  = purple 8   = concealed (invisible)
             background
37  = grey  46  = cyan   0   = default colour
             background
90  = dark  47  = grey   1   = bold
grey         background
91  = light 100 = dark
red          grey
             background
92  = light 101 = light
green        red
             background
             102 = light
93  = yellowgreen
             background
94  = light 103 = yellow
blue         background
95  = light 104 = light
purple       blue
             background
96  =       105 = light
turquoise    purple
             background
             106 =
97  = white turquoise
             background
             107 = white
             background

List_of_Some_of_the_Available_Keys:

no          Global default
fi          Normal file
di          Directory
ln          Symbolic link.
bd          Block device
cd          Character device
or          Symbolic link to a non-existent file
ex          Executable file
*.extension Example, *.mp3

Take a look at the links in the References section for more information on the
available keys.

Practical Example:

In this section, I will setyellow normal font on red background for directory
color.
I edited ~/.bashrc and set di=1;33;41 and saved the file.
I ran source ~/.bashrccommand.
Take a look at the magic in the screenshot below.
That’s how you customize the colors used in the ls command. Thanks for reading
this article.

References:

[1] https://askubuntu.com/questions/466198/how-do-i-change-the-color-for-
directories-with-ls-in-the-console
[2] http://www.bigsoft.co.uk/blog/2008/04/11/configuring-ls_colors
[3] https://web.archive.org/web/20140807232939/http://www.geekgumbo.com/2011/
11/04/changing-the-directory-color-in-the-bash-shell/


About the author


Shahriar Shovon

Freelancer & Linux System Administrator. Also loves Web API development with
Node.js and JavaScript. I was born in Bangladesh. I am currently studying
Electronics and Communication Engineering at Khulna University of Engineering &
Technology (KUET), one of the demanding public engineering universities of
Bangladesh.
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
