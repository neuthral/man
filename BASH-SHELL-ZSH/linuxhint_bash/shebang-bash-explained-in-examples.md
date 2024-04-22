





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Shebang Bash: Explained with Examples

2 years ago
by Sidratul_Muntaha
Bash is a command language interpreter. Many operating systems incorporate bash
as the default command interpreter, especially most of the GNU/Linux systems.
Bash scripting is a method of automating a set of commands that would otherwise
be executed interactively one-by-one.
In this guide, check out what shebang bash is and how to use it.

Shebang Bash:

In bash scripting, Shebang is a way to declare what interpreter the operating
system will use to parse the rest of the file. The Shebang is characterized by
the set of characters “#!” (without quotes).
Here’s a quick breakdown of the Shebang interpreter directive.
#!<interpreter> [arguments]
For example, if a script is to be parsed using the Bash shell, then the Shebang
interpreter directive would look like this.
#!/bin/bash
The Shebang interpreter directive has certain properties.

* It must be the first line of the script.
* It must start with a shebang (#!).
* There may or may not be whitespace after the shebang (#!).
* The interpreter will be the full path to a binary file.
* There may or may not be interpreter arguments.

Here’s a shortlist of some of the most common Shebang interpreter directives.

* #!/bin/bash: The script will be parsed using bash.
* #!/usr/bin/python: The script will be parsed using the python binary.
* #!/usr/bin/env perl: The script will be parsed using the perl executable. The
  location of the perl executable will be provided by the env command.


Using Shebang Bash:

Scripts can have no Shebang bash. Any such script will be parsed using the
default interpreter. For example, bash is the default interpreter for bash and
sh for zsh. While most of the UNIX/Linux systems have bash as the default,
users have options to use others. In such a scenario, without declaring the
interpreter, the script may not perform its preferred task.
There are two methods of using the Shebang directive to declare the
interpreter. The first one is to declare the file path to the executable.
#!/bin/bash
Another method is to use the env utility to locate the executable.
#!/usr/bin/env bash
The benefit of using the env utility is, it will look for the executable under
the $PATH environment variable of the current user. In this example, env will
look for the bash. If there is more than one bash executable declared in the
$PATH variable, then the first one will be used.
As mentioned, Shebang bash also supports executable arguments. For example, to
use bash with debug mode, the Shebang interpreter directive would look like
this.
#!/bin/bash -x
When it comes to using env for the Shebang bash, adding an executable argument
requires using the “set” option. For example, the following one will use bash
with debug mode enabled.
#!/usr/bin/env bash
$ set -x

Script Example:

We’ve discussed the basics of Shebang bash. It’s time to put it into practice.
Let’s have a look at the implementation of Shebang bash.
Launch the text editor of your choice and type the following script:
$ #!/bin/sh
$ echo "hello_world_bash"
Save the file. To run the script, it has to be marked as an executable. Run the
following command:
$ chmod +x <script>
Run the script:
$ ./<script>
Not very difficult, right? Now, let’s try using the different Shebang bash
expressions. Try the ones given below:
$ #!/usr/bin/env bash
$ set -x
$ echo "hello_world_bash_debug"

Overriding the Shebang Bash:

While the Shebang bash defines the interpreter to use, in certain situations,
you may want to use a different interpreter. It’s possible to override the
script-defined interpreter by explicitly specifying the interpreter to the
shell.
For example, have a look at the following script:
$ #!/bin/sh
$ echo "hello_world_sh"
By default, it would be run using sh. To run it using bash, use the following
method:
$ <interpreter> <script>
Note that for normal use cases just using the default sh or bash interpreter is
good enough and overriding is not relevant.

Final Thoughts:

Shebang bash is a very simple concept. For bash scripting, it’s very important
to understand and implement it.
Interested more in Bash scripting? Check out this beginner’s_guide_on_how_to
write_a_simple_bash_script.
Happy computing!


About the author


Sidratul Muntaha

Student of CSE. I love Linux and playing with tech and gadgets. I use both
Ubuntu and Linux Mint.
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
