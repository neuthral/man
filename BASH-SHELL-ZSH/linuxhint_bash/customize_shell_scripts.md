





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Shell scripts – What can you change

3 years ago
by Mats_Tage_Axelsson
In most, if not all, shells, you have a script that starts your shell. Learn
how to change it and you can have your own environment in the terminal. These
settings most obvious use is changing the looks and the prompt you are shown
when the shell starts. On a more functional note, you can set aliases,
environment variables and daemons that change your prompt depending on the
directory you are in. If you use the command line rarely and only with a few
odd commands, you might not be interested. However, you will loose out on the
power of the command line. With a little bit of scripting skills, you can
enhance your experience and make many tasks much easier. Above all, you can
become faster with some administrative tasks. The graphical choice is usual for
a very special case, as soon as you know scripting, you can do exactly what you
want. It is also more fun than most people think to have written any code, even
just a few lines and you get it to do what you intended.


What are they for?

The start script is there to change behaviour, add colour, set your prompt and
much more. One serious consideration is environment variables. Many
applications, and to a higher degree, libraries use these to control their
behaviour. When you install development packages, they set the environment so
that they can find the correct libraries, compilers and binary utilities. A
smart shell script can set your prompt to be dynamic for the directory you are
in. An excellent example of a great git_prompt which is made by Olivier
Verdier. when you have this active, you will see the status of your git repo on
the prompt.
Some common aliases to make things easier:
alias PreL='emacs –with-profile prelude &' alias egrep='egrep –color=auto'
alias l='ls -CF' alias la='ls -A' alias ll='ls -alF' alias ls='ls –color=auto'
alias pbcopy='xclip -selection clipboard' alias pbpaste='xclip -selection
clipboard -o'
In the list above, you can see that the user likes Emacs. The top alias sets
the Prelude distribution to start with the short command PreL. Excellent when
you want to try several Emacs distributions. Next down, you make sure egrep
will always use colour. The ls aliases makes it easier to handle files. You can
create your own easily just by writing it at the command prompt, then trying it
out. When you are pleased, just add it to your favourite shells initialisation
file.
To make sure applications use the correct directories and values, the system
uses environment variables. The main environment variables are :

* PATH

The path is where your shell looks for executable files. Inside, you will find
/bin, /usr/bin and so on depending on your needs and distribution. When you
start developing software, the install scripts will change this so you use the
correct binaries and libraries.

* SHELL

This variable shows which shell you are running. This is used by scripts to
make sure that you have the features of the shell script. Most commonly, bash
is the shell but if you use bash features in another shell, the script will
fail. If you check this variable, you can stop the script or use POSIX
compliant methods.

* USER

This is your username.

* TERM

This is set by the terminal you are using, so the script knows if colour can be
used.

* LSCOLORS

This one sets the colours for the ls command.

* LC*

This ones are important because they set what language you use. Which keyboard
you use is set with these. Get it wrong and you may have a problem finding ‘/’
and ‘\’. They move around depending on your keyboard settings.
Shell variables control options for the shell itself. They are more direct for
the shell, not the entire system or applications.

* BASHOPTS

Here, you can check the options used when you start your shell. This is a
second way to make sure your scripts run smoothly.

* BASHVERSION

The version of bash.

* COLUMNS

The width of your shell in columns.
You can set many of these while you are using the shell but nothing stays until
you put it in your initialisation scripts.

Where are they?

Each shell has their own files to help you customise the user experience. This
all depends on if you programming, administering or just use the command line
for your daily tasks.
The different shells have different places for their files but as a rule, there
is at least one file in /etc and another in your home directory. When you set
things up, make sure to use the user directory settings unless it absolutely
certain it is required by your setup. The most common default shell on Linux is
bash. Many scripts need to work in any shell, for this purpose, the POSIX
standard exists. The standard declares what code you can put in, bash has many
other features, a POSIX compliant shell is ‘sh’. This should be available on
all distributions.

How do you change, and test your own changes?

The best way to test your changes is to set them with a script that you run
manually and then test. When you have gone through enough iterations, you put
the values in your configuration files.

Conclusion

You can change many things with your shell that makes it prettier and that
helps you run programs in the command line. To make it better, start with
aliases and then move on to more advanced scripts. There are many scripts
available that may help you with your specific tasks. Look for them and if they
are lacking something, read through the scripts and make your own changes.
Remember to ask for help and compete and cooperate about the scripts you write.


About the author


Mats Tage Axelsson

I am a freelance writer for Linux magazines. I enjoy finding out what is
possible under Linux and how we can all chip in to improve it. I also cover
renewable energy and the new way the grid operates. You can find more of my
writing on my blog.
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
