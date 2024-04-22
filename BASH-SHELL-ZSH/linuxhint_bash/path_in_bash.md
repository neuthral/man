





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How Does PATH Work in Bash

3 years ago
by Sidratul_Muntaha
When you’re typing a command in the Linux terminal, you’re generally calling a
program to do a certain job, for example, ls, cd, rm, mkdir, etc. All these
programs are located somewhere in the file system, right? How does bash know
where these programs are?
Here come the environment variables into play, especially the PATH variable.
This variable is responsible for telling bash where to look for those programs.
Let’s check out how PATH works and how to view/modify PATH.

Environment variable and $PATH

In the shell terminology, the “environment” is an area that the shell builds
every time it starts a session. To manage the environment, there are
“environment variables” denoting different parts of the environment. The value
of the variable can be string, directory location, value or others.
PATH is such an environment variable that keeps track of certain directories.
By default, the PATH variable contains the following locations.

* /usr/bin
* /usr/sbin
* /usr/local/bin
* /usr/local/sbin
* /bin
* /sbin
* /snap/bin (if Snap is installed)

Want to see what directories are currently registered under PATH? Fire up a
terminal and run the following command.
$ echo $PATH
Here, the $ sign is to denote a variable. The echo command prints the value of
the PATH variable.
Now, why this specific environment variable is so important? It’s because how
shell and the system as a whole treats it. The PATH variable stores where
executables may be found. Whenever any command is run, the shell looks up the
PATH directories for the target executable file and runs it.
For example, let’s test with the echo command. Here, I’m running an echo
command.
$ echo Hello World!
Where’s the executable file of echo? Run the next command to find out.
$ which echo
As we can see, the echo executable is located at /usr/bin/echo. Where’s which
located? Let’s find out.
$ which which
It’s also located at /usr/bin/which. Most of the command tools are located
under the /usr/bin directory. Here, bash is consulting PATH for the locations
to search for the executable(s) of a command.

Modifying PATH

Before we modify the value of PATH, it’s important to understand its structure.
Run the command again to check the value of PATH.
$ echo $PATH
Notice that each of the directories is separated by a “:” sign.

Adding directory to PATH

To add a custom directory to PATH, we’ll be taking the help of the bashrc file.
It’s a special bash script that bash loads every time a new bash session
starts. Note that the bashrc file is unique to every single user in the Linux
system.
Open the bashrc file in a text editor. If the bashrc file isn’t present
already, then the editor will create it automatically.
$ vim ~/.bashrc
Here, it’s the default bashrc that comes with Ubuntu. Go to the last of the
file (if it exists) and add the following line.
$ export PATH="$PATH:/<target_directory>"
Here, the new value of PATH variable will be the old variable along with the
new directory we just added.
Save the file and tell bash to reload it.
$ source ~/.bashrc
Let’s verify whether the new path was successfully added.
$ echo $PATH
Voila! PATH updated successfully! Now, bash will also search the new path for
executable(s). I already have a script demo.sh on desktop. Let’s see if bash
can call it without specifying the exact location.
$ demo.sh
Yup, bash can directly call it without any problem.

Removing directory from PATH

There’s no straightforward way of adding/removing directories from PATH. Let me
explain.
The value of PATH is actually fixed. Then, what about the bashrc trick? Bashrc
is a bash script that bash loads every time it starts a session. In bashrc, we
just declared that the new value of PATH will be its default value and the
user-defined directory. Now, every time bash loads, it sees that bashrc is
telling to assign a new value of PATH and that’s what it does.
Similarly, if we want to remove a directory from PATH, we have to re-assign a
different value of PATH in the bashrc so that every time bash starts, it uses
the modified value.
Let’s have a look at this example. I’m willing to remove the directory “~/
Desktop” from the PATH.
$ echo $PATH | sed -e 's/:\~\/Desktop$//'
If the directory would be /home/wrong/dir, the command would look like this.
$ echo $PATH | sed -e 's/:\/home\/wrong\/dir$//'
Here, the interesting part is the sed tool. Learn more about sed here and here.
Long story short, using sed, we’re modifying the output of the echo command.
Now, we can use this modified output to change the value of PATH.
Open bashrc in a text editor and add the following lines. I’m intentionally
keeping the previous lines to prove that it’s working.
$ export PATH="$(echo $PATH | sed -e 's/:\~\/Desktop$//')"
Alternatively, you can also manually set the value of PATH. It’s a laboring
process but more straightforward and simple.
$ export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:
/usr/games:/usr/local/games:/snap/bin
Here, the value of the command will be assigned to PATH. Save the file and
reload bashrc.
$ source ~/.bashrc
Let’s verify the result.
$ echo $PATH
The PATH value is updated!

Final thoughts

In bash, the PATH variable is an important one. Any program that runs through
the bash session inherits the variable, so it’s important that PATH includes
the necessary directories only. Adding more directory will only add redundancy
to the system.
To see all the environment variables for bash, run this command. The first
command part will return all the environment variables and the second part will
sort the output in ascending order.
$ env | sort
Want to spice up your bash experience? Bash aliases offer a unique way of
speeding and spicing things up. Learn_more_about_bash_aliases.
Enjoy!


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
