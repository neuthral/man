





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Programming Best Practices

1 year ago
by Sidratul_Muntaha
Bash is one of the most popular shells available on Linux. It’s simple, fast,
and lightweight. Besides interpreting and executing commands, bash can work
with scripts to automate a particular set of tasks.
This guide elaborates on some of the common practices in bash programming.

Bash scripting

Bash is a shell program that’s responsible for interpreting and executing
commands. Besides executing manual commands, bash also supports scripting.
These scripts are a set of commands declared in a text file. Bash scripting is
a simple and accessible programming language to learn on Linux. It’s a
requirement if you’re interested in system administration jobs.
Like any other skill, persistence and repetition will help you improve. While
there are no fixed set of rules, here are some of the habits that can
considerably enhance your script quality.
Proper indentation
Indentation is a big part of coding. Proper indentation is paramount to have a
readable and maintainable code.
Proper indentation can be a lifesaver if you’re working with multiple levels of
logic. Indentation makes it easy to recognize the logic layers.
Here’s an example multi-logic script with proper indentation.
#!/bin/bash
read -p "Enter a value " var_x
if [ $((var_x%2)) -eq 0 ]; then
        exit 0
else
        exit 1
fi
Here’s how the code will look like without proper indentation.
#!/bin/bash
read -p "Enter a value " var_x
if [ $((var_x%2)) -eq 0 ]; then
exit 0
else
exit 1
fi
Commenting
Commenting is one of the most important things when it comes to making sense of
codes. Comments should explain various parts of the code, especially when it’s
a complex one. It’s effortless to get confused about multiple parts of the
code, even your own codes. If it’s a big project and others will probably work
on the same code in the future.
For example, here’s a sample script with and without comments.
username=$1

# check username existence
grep ^$username: /etc/passwd
if [ $? != 0 ]; then
    echo "No such user: $username"
    exit 1
fi
user=$1

grep ^$username: /etc/passwd
if [ $? != 0 ]; then
    echo "$username not found"
    exit 1
fi
Return code if anything goes wrong
When something goes wrong, returning a non-zero value is always a good idea. A
code can run awry at any point, especially with conditionals. Having a return
code to work with can save a ton of hassle. It makes debugging more effective.
In this example, we’ll determine whether a number is odd or even. Instead of
printing output, the exit code will signal what the result was.
#!/bin/bash
read -p "Enter a value " var_x
if [ $((var_x%2)) -eq 0 ]; then
    exit 0
else
    exit 1
fi
The script exists upon error
In many situations, bash will continue executing the script even when a
specific part fails, impacting the rest of the script badly.
To ensure that the script exists upon facing some fatal error, it’s recommended
to have the following lines at the start.
$ set -o errexit
At times, bash may also try using an undeclared variable, causing a logical
error. Using the following command will ensure that bash will stop executing
the script if it uses an undeclared variable.
$ set -o nounset
Command substitution
In situations, you may need to work with the output of a particular command. We
can do it using the command substitution.
Command substation has different ways of implementation.
$ echo 'echo “hello world”'
$ echo $(echo “hello world)
It’s always recommended to use the second option
Meaningful variable name
Variables are an integral part of a complex bash script. Every variable should
have a proper name that signifies its usage.
Often name patterns may also time; people will avoid typing a few extra
characters in exchange for short-term time gain. However, such a practice is a
recipe for disaster. When it comes to the long-term maintenance of such code,
it can be complicated to make a sense of purpose of a variable.
It would be best if you also were consistent in naming variables. Random
variable name patterns may also lead to confusion in the future.
Look at the two sample codes, both doing the same task. Which code is better to
understand and work with?
#!/bin/bash
read -p "Enter length:" x
read -p "Enter width:" y
z = $[$x*$y]
echo "Area: $z"
#!/bin/bash
read -p "Enter length:" length
read -p "Enter width:" width
area = $[$length*$width]
echo "Area: $area"
In bash, all the environment variables are named with uppercase letters. It’s
recommended to use lowercase letters for script variables to avoid conflicts.
Using functions
In bash programming, a function is a way to group commands that can be executed
later. It helps reducing code repetition. Functions also make the code more
readable and maintainable.
Now, there are specific scenarios where functions make sense. If you’re using a
handful of focused commands, setting up a function can save you a lot of
trouble. If you’re using only one command, then having a function has no impact
on efficiency.
Same as variables, the function names should be meaningful.
function fn_odd(){
        local var_x

        read -p "Enter number" var_x
        read var_x

        if [ $((var_x % 2)) -eq 0 ]; then
                echo "even"
        else
                echo "odd"
        fi
}
Argument types
In bash, there’s no fixed way of declaring a variable type. It may give rise to
comparing variables of conflicting data types. Ensuring that the variables and
arguments are the same expected type will save you a lot of headaches.
In the following example, the script will print out whether the argument is a
number or not.
if ! [ "$1" -eq "$1" 2> /dev/null ]
then
  echo "ERROR: not number"
  exit 1
fi
Missing arguments or wrong argument order
It’s always a good idea to assume that user input will probably have incorrect
data, no matter what. The probability is higher when the user needs to input
more than one argument.
You need to have error correction mechanisms at the user input points to avoid
catastrophe due to wrong user input. Make the instruction clear on what the
user is supposed to do.
Proper output
When running your scripts, people should know what they need to know. They
shouldn’t have to read your code to understand its purpose or what it’s doing.
There should be feedback on the screen explaining what’s going on behind the
scenes at every step. For example, what would the user experience be if the
package manager didn’t print any meaningful output at various stages of its
operation?
Debugging
After writing the script, bash can check the script syntax for errors without
execution. To perform a syntax check, use the following bash command.
$ bash -n <script>
Alternatively, the shebang can enable the syntax to debug mode.
#!/bin/bash -n
To run bash on debug mode, use the “-x” flag.
$ bash -x <script>
It can also be a part of the shebang.
#!/bin/bash -x

Final thoughts

These are only a handful of bash programming practices. These are simple yet
powerful habits to develop. These tricks will ensure that your bash scripts are
optimized, readable, and reliable. You want your shell scripts to be simple and
straightforward—no need to squeeze out as much as possible using very exotic
syntax or shell commands.
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
