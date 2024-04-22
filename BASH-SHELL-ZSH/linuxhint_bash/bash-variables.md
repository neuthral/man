





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Variables In-Depth

1 year ago
by Chrysanthus_Forcha
A variable is a place to store an object in the computer’s memory. This article
explains how to declare a variable using the builtin command called to declare.
It then describes the meaning of variable attributes and gives some examples.
After that, some predefined variables are talked about.
The name of a variable is the name given to by the programmer. The following
script gives examples of variable declarations with assignments:
    declare num=2.5

    declare str1=books

    declare str2='the books'

    declare arr=(zero one 2 "three ccc")

    echo $num
    echo $str1
    echo $str2
    echo ${arr[3]}
The output is:
2.5

books

the books

three ccc
A number is assigned without quotes. A word as a value can be assigned without
quotes. More than one word as value is allocated with single or double quotes.
There should be no space on the left or the right of the assignment operator.
To read the value of a variable down in the script, the variable should be
preceded by $. The reading of an array value has a special syntax.
The array declared above is an indexed array. An associative array would be
declared as follows:
declare -A arr=([aa]=zero [bb]=one [cc]=2 [dd]='three ccc')
Here, ‘-A’ is an example of an attribute. It means arr is an associative array
and not an indexed array. ‘A’ in ‘-A’ does not mean attribute. A variable
attribute is a subset of what is called command options.
A variable can be declared and have its value assigned after, as the following
script shows:
    declare num
    declare str1
    declare str2
    declare -A arr

    num=2.5
    str1=books
    str2='the books'
    arr=([aa]=zero [bb]=one [cc]=2 [dd]='three ccc')

    echo $num
    echo $str1
    echo $str2
    echo ${arr[dd]}
The output is:
2.5

books

the books

three ccc
When assigning later, the variable name is not preceded by $.

Article Content


* Variable_Attributes
* read_Command
* Some_Predefined_Variables
* Conclusion


Variable Attributes

A variable attribute, gives more precision for the variable. For example, in:
declare -A arr=([aa]=zero [bb]=one [cc]=2 [dd]='three ccc')
the option ‘-A’ to the declare builtin command, precise that arr is an
associative array. ‘-A’ is an attribute to the variable, arr. ‘-a’ in the
following command, precise that arr is an indexed array:
declare -a arr=(zero one 2 "three ccc")
‘-a’ is optional. Without it, arr would be considered as an indexed array.
Some Variable Attributes
-a
Used for arrays – see above
-A
Used for arrays – see above
-i
The variable is to hold an integer. The following code segment will produce an
error message because 2.5 is not an integer.
declare -i num=2.5

echo $num
The following code segment will output, 2 :
declare -i num=2

echo $num
-l
Allows lowercase characters in lowercase, but converts any uppercase character
to lowercase, as in the following code segment:
declare -l str=abcDEF

echo $str
-u
Allows uppercase characters in uppercase, but converts any lowercase character
to uppercase, as in the following code segment:
declare -u str="abc DEF"

echo $str
The output is: ABC DEF
-r
Makes variable, read-only (constant). A value assigned to the variable cannot
be changed later down in the script. In the following code segment, the first
two lines operate well; but the last line issues an error message because an
attempt is made to change the value of the constant variable:
declare -r num=56

echo $num

num=32
– n
Creates a reference to a memory location. The following code illustrates this:
declare var=56

declare -n ref1=var

declare -n ref2=var

echo $var

echo $ref1

echo $ref2
The output is:
56

56

56
If the value of any of the variables is changed, the rest are changed to that
value; because they refer to the same memory location.

read Command

The read command reads a line of text from the console. Assume that the
following three values are to be read:
one two beta three
Where “one” is one value, “two beta” is the second value, and “three” is the
third value. Note that the second value is two words, separated by a space.
This line of values will have to be typed as follows:
one two\ beta three
That is, the space between “two” and ”beta” has to be escaped with a backslash
for the two words to appear as one value. So, if any value consists of more
than one word, each space in it must be escaped. To read these three values,
the read command should be something like:
read aa bb cc
Where aa, bb, and cc are variables chosen by the programmer.
When the read command is executed, it flashes the cursor for the user to input
a line and press Enter. If the user inputs the above line with the space of
interest escaped, then the effect would be equivalent to:
aa=one

bb="two beta"

cc=three
If there are more values than variables, the remaining values are assigned to
the last variable. If there are more variables than values, the remaining
variables are assigned empty values.
Values can be read into an index array, where each index corresponds to one
value. Again, any space that joins two words must be escaped. The following
code illustrates this:
read -a arr

size=${#arr[*]} #array size

for ((i=0; i < $size; ++i)); do

echo ${arr[i]}

done

If the input was,

one two\ beta three
The output would be,
one

two beta

three

Some Predefined Variables

These variables should be preceded by $ to be used as an argument to the echo
command.
BASH
In the author’s computer,
echo $BASH
gave the output,
/bin/bash
This is the full pathname to the bash interpreter.
BASH_ENV
This is to do with Bash Startup Files. In the author’s computer,
echo $BASH_ENV
gave null for the output
BASHPID
A process is a program or script that is running on the computer. The operating
system identifies a process with a number. In the author’s computer,
echo $BASHPID

gave the output,

3141
Which was the process ID (PID) of the bash script running.
BASH_VERSION
This gives the version number of the current instance (running process) of
Bash; e.g.
4.4.20(1)-release
EPOCH SECONDS
The Unix Epoch is 1st January 1970 00:00:00 UTC. This variable should give the
number of seconds since Unix Epoch.
EUID
This variable gives the effective numeric user ID of the current user,
something like 1000.
GROUPS
The current user can be a member of a list of groups. This gives an array
variable of that list. If used as follows,
echo ${GROUPS[*]}
the result may be something like this:
1000 24 27 30 46 116 126 4
HOME
This is the directory of the current user. It is something like:
/home/smith
Of which the name of the user is Smith.
HOSTNAME
The hostname is the name that precedes the prompt when the prompt is displayed
at the terminal. This variable gives the name of the current host. It is
something like:
smith-PC
HOSTTYPE
This is the type of machine Bash is running on. It can be something like:
x86_64
HOSTFILE
A host file is a plain text file that maps IP addresses to hostnames. This
variable gives the path and filename for the host file, which may be something
like:
/etc/hosts
However, a password may be needed to open the file.
MAIL
This variable can be set to a filename or a directory name. Bash should use it
to inform the user when a mail arrives.
IFS
IFS stands for Internal Field Separator. It is used to separate a string into
various pieces. Consider the following code:
declare -a arr=(" one" " two" " three")

IFS=','

echo "${arr[*]}"
The output is:
one, two, three
IFS has been set with ‘,’. So, the display of the array values has been
separated by ‘,’. The output appears as if a comma and space separated the
values. This is not really the case. It seems so because each value in the
array has been preceded with space.
PPID
It is possible to have a process and a child process. The process is the parent
process. PPID is the process ID of the parent of the shell (Bash). In the
author’s computer.
echo $PPID

outputted

3134
PWD
This is the current working directory.
SHELL
This is similar to the BASH variable – see above
UID
This is the real numeric ID of the current user. In the author’s computer,
echo $UID

outputted,

1000

Conclusion

A variable holds a value. A variable can also reference the location in memory
that has the value. When a variable is set (assigned a value), it is not
preceded by $. When the value of a variable is read, it is preceded by $. With
the declare command, variables can have attributes. A variable attribute is an
option to the command. A variable attribute results in a particular behavior of
the variable. Attributes that the reader is likely to use often are: -a, -A, -
i, -l, -u, -r, and -n. There are predefined variables. The ones the reader is
likely to use often have been given in the previous section.


About the author


Chrysanthus Forcha

Discoverer of mathematics Integration from First Principles and related series.
Master’s Degree in Technical Education, specializing in Electronics and
Computer Software. BSc Electronics. I also have knowledge and experience at the
Master’s level in Computing and Telecommunications. Out of 20,000 writers, I
was the 37th best writer at devarticles.com. I have been working in these
fields for more than 10 years.
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
