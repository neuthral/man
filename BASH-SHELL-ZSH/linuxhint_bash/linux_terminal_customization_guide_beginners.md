





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Linux Terminal Customization Guide for Beginners

3 years ago
by David_Morelo
The terminal is a mighty tool, but its default appearance can be a bit boring.
In this article, we’ll show you how you can customize it to fit your needs and
preferences and go from this:
To this:
Even though we’re using the Ubuntu Terminal in our examples, most information
in this article isn’t Ubuntu-specific, and you should be able to achieve the
same or similar result regardless of which Linux distribution you use.
Warning: By customizing the terminal, you can make it more visually appealing
and functional, but you can also screw up word wrapping and prevent terminal
applications from displaying correctly, so always back up all configuration
files before you modify them.

Customize Terminal Colors

It doesn’t matter if you love the movie Matrix or just want to ease the strain
on your eyes when using your computer late at night, changing the appearance of
the terminal can be as simple as selecting a new theme.
The good news is that many terminal emulation applications, such as GNOME
Terminal or Konsole, come with a decent selection of themes, and all you need
to do is go to Preferences and pick the one you like the most.
In Ubuntu, you can easily customize text and background color and select a
corresponding color palette:
As you can see, we selected the Solarized dark theme and the Solarized palette,
making the terminal very easy on the eyes without sacrificing readability.
While you’re at it, you can also check the remaining tabs and make any
modifications you desire. We changed the shape of the cursor from Block to
Underline.
If you use a lightweight terminal that doesn’t have an equivalent of the
Preferences window, such as xterm or URxvt, you can change its colors by
modifying the Xresources configuration file, which is typically located in
~/.Xresources.
You can easily generate the desired Xresources configuration file using
terminal.sexy, which is a handy web app that lets you design, edit, and share
custom terminal color schemes and export them to a wide range of terminals.

Set Bash Prompt Variables

Most Linux distributions use Bash as the default shell. Bash has four
customizable prompts, but only the primary prompt (called PS1) is worth
customizing because it’s displayed before each command. The remaining three
command prompts are displayed only on special occasions, such as when a command
needs more input or when debugging bash scripts, so you can safely ignore them.
This is what PS1 displays by default in Ubuntu:
To see the default value of PS1, use the following command:
$ echo "Bash PS1:"  $PS1
You should see something like this:
PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\[email protected]\h\
[\033[00m\]:
\[\033[01;34m\]\w\[\033[00m\]\$ '
This seemingly random sequence of letters, numbers, and special characters
consists of the so-called Bash prompt escape sequences and values used to
specify colors. This is what it means:

\u  �the username of the current user
@      the ‘@’ symbol
\h  �the hostname up to the first ‘.’
:      the ‘:’ symbol
\w  �the current working directory
$      the ‘$’ symbol

Since PS1 is a Bash variable, you can modify it on the fly straight from your
terminal:
That’s how easy it is to make PS1 display only the username. Here are some
other useful Bash prompt escape sequences:

\d the date in “Weekday  Month  Date”  format (e.g., “Tue May 26”)
\e an ASCII escape character (033)
\H the hostname
\j The number of jobs currently managed by the
\l The basename of the shell’s terminal device name
\n newline
\v the version of bash (e.g., 2.00)
\W the basename of the current working directory
\$ if the effective UID is 0, a #, otherwise a $
\\ a backslash

Changing the color of the username, or any other part of the command prompt, is
also pretty straightforward. This is how you can make the username red:
PS1="\[\033[31m\]\u$ "
The color red has the value of 31, and it’s enclosed in the following tag: \
[\033[COLOR]m\]
Here are some other colors and their corresponding values:

Color                    Value Example
Default foreground color 39    echo -e “Default \e[39mDefault”
Black                    30    echo -e “Default \e[30mBlack”
Red                      31    echo -e “Default \e[31mRed”
Green                    32    echo -e “Default \e[32mGreen”
Yellow                   33    echo -e “Default \e[33mYellow”
Blue                     34    echo -e “Default \e[34mBlue”
Magenta                  35    echo -e “Default \e[35mMagenta”
Cyan                     36    echo -e “Default \e[36mCyan”
Light gray               37    echo -e “Default \e[37mLight gray”
Dark gray                90    echo -e “Default \e[90mDark gray”
Light red                91    echo -e “Default \e[91mLight red”
Light green              92    echo -e “Default \e[92mLight green”
Light yellow             93    echo -e “Default \e[93mLight yellow”
Light blue               94    echo -e “Default \e[94mLight blue”
Light magenta            95    echo -e “Default \e[95mLight magenta”
Light cyan               96    echo -e “Default \e[96mLight cyan”
White                    97    echo -e “Default \e[97mWhite”

Now you have all the information you need to recreate the Bash prompt you’ve
seen at the beginning of this article:
PS1="\[\e[93m\]\W\[\e[m\]:/\[\e[34m\]>\[\e[m\]\[\e[37m\]\\$\[\e[m\]"
The only thing left to do is edit the .bashrc file (usually in ~/.bashrc):
There’s no need to edit the else clause because it serves only as a fallback in
case you use a terminal emulator that doesn’t support colors.
If all this seems like too much work to you, you should know that there are
easy-to-use web applications that let you generate a PS1 prompt with a drag and
drop interface, including this_one and this_one.

Conclusion

Equipped with the information provided in this article, you should be able to
customize the appearance of your terminal to fit your personal preferences.
Remember that less is sometimes more, so avoid excessive customization and keep
things simple and functional.


About the author


David Morelo

David Morelo is a professional content writer in the technology niche, covering
everything from consumer products to emerging technologies and their cross-
industry application
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
