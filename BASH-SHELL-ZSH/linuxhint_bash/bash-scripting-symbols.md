





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Scripting: Symbols

10 months ago
by Omar_Farooq
On Linux, the terminal is everything, it’s where we pass commands, and it’s
where we pass scripts. Therefore, one of the most important scripting languages
is bash. Bash scripting is used to automate the boring tasks in Linux. In order
to automate tasks, commands are written within the script and given an
extension of .sh. As part of the commands, certain symbols are used as well.
These symbols are unique to bash, and each has its own specific meaning. In
this tutorial, we will review the various symbols encountered during bash
scripting and their specific meaning.

Symbol: <

The symbol < is used for input redirection. Files, for example, can be used as
input.
For example:
#! /bin/bash

cat < file.txt
In this case, the file.txt is taken as the input, and the cat command then cats
it out.
 Untitled_14  Untitled_14

Symbol: >

This symbol, known as the file redirection operator, is typically used to
redirect the contents of a command/file to another by overwriting it.
For example:
#! /bin/bash

echo “hello world’ > file.txt
 Untitled  Untitled
Here, the > symbol is similar to 1>. This is so because the 1 is a file
descriptor for the standard output. Please note that the file descriptors are
as follows:
0 — Standard input, stdin
1 — Standard output, stdout
2 — Standard error, stderr
In the previous scenario, the single forward arrow was equivalent to 1>.
However, we can also write 2> to forward it to the standard error.
For example:
#! /bin/bash

mcat file.txt 2> file2.txt
Here, the 2> means that the error will be dumped into file2.txt.
 Untitled2  Untitled2

Symbol: >>

The symbol >> is used to append and not to replace! The file redirection
operator replaces or overwrites everything while the >> is used to append.
For example:
#! /bin/bash

echo “this is the second line” >> file.txt

echo “this is the third line” >> file.txt
The latter will append the two lines to the file called file.txt. The result of
file.txt will then be as follows:
 Untitled3  Untitled3

Symbol: #

The hashtag is used to add one-line comments into scripts. These comments are
not executed/run.
#! /bin/bash

# this will dump the line into the file

echo “this is a file” > file.txt
 Untitled4  Untitled4
Unlike the #, which is a one-liner, the multi-line comments look more like
this;
#! /bin/bash

: ‘

This is the comments section

This is the first line

This is the second line

‘

echo “hello world”
 Untitled5  Untitled5

Symbol: $#

The symbol $# is used to retrieve the length or the number of arguments passed
via the command line. When the symbol [email protected] or simply $1, $2, etc.,
is used, we ask for command-line input and store their values in a variable.
The symbol $# is used to retrieve the total number of arguments passed.
For example:
bash -c “echo $#” hello world again
The latter should chuck out a value of 2 because there are 3 elements (hello,
world, and again).
 Untitled7  Untitled7

Symbol: &>

This symbol redirects both the standard output and the standard error.
For example;
bash -c ‘ls -la &> file.txt’
In this case, the &> symbol redirects both the standard output and the standard
error to the file called file.txt. Thus, both the output generated and the
error generated is placed in the same file.
 Untitled6  Untitled6

Symbol: \< and \>

You need to compare the string length or character lengths; this can be done
via the symbols \< and \>. These two symbols are used to compare character
lengths.
For example:
#! /bin/bash

a=”cat”

b=”lynx”

if [ a \< b ]

then

echo “a is shorter than b”

else

echo “a is longer than b”

fi
In this case, the word stored in a – or cat – has a character length of 3,
while the word stored in b – or lynx -has a character length of 4. Thus the
answer should be that “a is shorter than b.”
 Untitled8  Untitled8

Symbol: ^^, ^ and ,,

Some symbols function to change the case of the characters.
^^ — to turn all characters to uppercase
^ — to turn the first letter to uppercase
,, — to turn all characters to all lowercase
For example:
#! /bin/bash

a=”cat”

b=”lynx”

c=”DRAGON”

echo ${a^^}

echo ${b^}

echo ${c,,}
 Untitled9  Untitled9

Symbol: [email protected] or $*

The symbol [email protected] is equivalent to $* which is equivalent to $1 $2
$3 $4…
Ex:
#! /bin/bash

echo $1 $2 $3 $4 $5

# the latter is equivalent to echo [email protected]
In this example, the $1, $2, $3, $4, and $5 are inputs from the command line.
Alternatively, we could have written the following:
#! /bin/bash

echo $@
Or
#! /bin/bash

echo $*
 Untitled_10  Untitled_10

Symbol: $?

This particular symbol – $? – is used to get the exit status of the command
previously passed.
Ex:
#! /bin/bash

echo “hello world” > file.txt

echo $?
An exit status of 0 indicates that the process was completed successfully.
 Untitled_11  Untitled_11

Symbol: $$

The symbol $$ stores the PID of the current shell.
For example:
#! /bin/bash

echo $$
In my case, it printed out the value 2443. This is the PID of the shell.
 Untitled_12  Untitled_12

Symbol: 2>&1

The symbol 2>&1 redirects both the standard output and the standard error to
the standard output.
For example:
#! /bin/bash

ls 2>&1 > file.txt
In this case, all the standard output and if any error is generated, the
standard error is both directed into the file called file.txt.
 Untitled_13  Untitled_13
Bash scripting is a key scripting language that can be used to automate tasks.
During bash scripting, we encounter much code, but we also encounter special
characters or symbols that are unique to bash. These symbols each have a
particular role in bash scripting, and they aren’t always obvious. In this
tutorial, we reviewed a few key symbols used while writing bash scripts.
Obviously, there are many symbols out there; however, some are encountered so
frequently that it might be necessary to know them while bash scripting. So go
forth, fearless of the symbol from here onwards!
Happy Coding!


About the author


Omar Farooq

Hello Readers, I am Omar and I have been writing technical articles from last
decade. You can check out my writing pieces.
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
