





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Shell Expansions: Brace Expansion, Parameter Expansion and more

3 years ago
by Linux_Wolfman
In this article we will cover all the basic features of Bash Shell expansion. 
Some of the most complex and interesting expansions are the Brace Expansion and
Parameter Expansion which have many features and options which are powerful but
only mastered over time by BASH programmers and linux devops folks.  Word
Splitting is also quite interesting and sometime overlooked.  Filename,
Arithmetic Expansion and Variable substitution are well known.  We will cover
numerous topics and show examples of the command and most useful syntaxes for
each syntax.  So let’s get started.

* Environment
* Command_Substitution
* Process_Substitution
* Variable_Substitution
* Brace_Expansion
* Parameter_Expansion
* Positional_Parameters
* Tilde_Expansion
* Arithmetic_Substitution
* Word_Splitting
* Filename_Expansion
* Conclusion


Environment

In order to test all of the bash shell expansions features we need to make sure
we are running a recent version of bash.  Below is the system information for
this article. The tests in this article are running on Ubuntu 19.10 as shown
below.
$ uname -a
Linux instance-1 5.3.0-1014-gcp #15-Ubuntu SMP Tue Mar 3 04:14:57
UTC 2020 x86_64 x86_64 x86_64 GNU/Linux
The bash version for these tests is bash version 5, which is quite recent. 
Older versions of bash are missing a bunch of features.
$ bash --version
GNU bash, version 5.0.3(1)-release (x86_64-pc-linux-gnu)
Copyright (C) 2019 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>

Command Substitution

Command substitution allows the running of one or multiple commands and
capturing outputs and actions from those commands and including them in another
command all in one line or less lines than running all the commands
separately.  Command Substitution has two syntaxes; the more popular syntax is
the backtick syntax where the command to be executed is enclosed in two
backquotes, or backticks.  The other syntax which is equally powerful encloses
commands in $() syntax and the output can be used from that new expansion. 
Let’s look at a number of examples of Command Substitution below.
Simple command substitution using $() syntax to run the date command.
$ echo $(date)
Wed Mar 18 01:42:46 UTC 2020
Simple command substitution using backtick syntax to run the date command.
$ echo `date`
Wed Mar 18 01:43:17 UTC 2020
Using the stdin operator at the beginning of command substitution syntax is a
fancy way to read the text of a file into a variable and use it in a command on
the shell as below.
$ echo "hello world" > mytext
$ echo $(< mytext)
hello world
Read a file into a variable to be used in a command using the cat command and
Command Substitution.
$ echo "hello world" > mytext
$ echo $(cat mytext)
hello world
Same as above, read a file and use it in Command Substitution using backticks
and cat command.
$ echo "hello world" > mytext
$ echo `cat mytext`
hello world
Combine embedded Command Substitution with another Command Substitution using
both $() and backticks together
$ echo `echo $(date) |cut -d " " -f 1` > myfile
$ cat myfile
Wed
Embedded Command Substitution inside another one using two $() syntax
operations
$ echo "today is $(echo $(date) |cut -d " " -f 1)" > myfile
$ cat myfile
today is Wed
Use output from a command as arguments into another command, with the backtick
syntax.  We will get a list of files by running cat which contains one file per
line and then pass that into the rm command which will remove each file
$ touch one; touch two
$ echo one > myfiles; echo two >> myfiles
$ rm `cat myfiles`
Same as above but with $() syntax, pass command output from cat into rm command
to delete files.
$ touch one; touch two
$ echo one > myfiles; echo two >> myfiles
$ rm $(cat myfiles)
Store the output from a cat command into a variable and then loop through the
variable so you can more clearly see what is happening.
$ touch one; touch two
$ echo one > myfiles; echo two >> myfiles
$ MYFILES=$(cat myfiles)
$ for f in $MYFILES; do echo $f; rm $f; done
one
two
Same as above but use backticks syntax to run the cat command and store the
output in a variable and then loop through the files int the variable.
$ touch one; touch two
$ echo one > myfiles; echo two >> myfiles
$ MYFILES=`cat myfiles`
$ for f in $MYFILES; do echo $f; rm $f; done
one
two
Use the Command Substitution with stdin operator to read a file line by line
into a variable and then loop through the variable afterwords
$ touch one; touch two
$ echo one > myfiles; echo two >> myfiles
$ MYFILES=$(< myfiles)
$ for f in $MYFILES; do echo $f; rm $f; done
one
two

Process Substitution

Process Substitution is a documented feature of bash; it’s quite cryptic in my
opinion.  In fact I have not found many good use cases to recommend for it. 
One example is included here for completeness where we use Process Substitution
to get the output of a command and then use it another command.  We will print
the list of files in reverse order with sort command in this example after
fetching files from the ls command.
$ touch one.txt; touch two.txt; touch three.txt
$ sort -r <(ls *txt)
two.txt
three.txt
one.txt

Variable Substitution

Variable Substitution is what you can consider basic usage of variables and
substituting the value of the variable when it is referenced.  Its fairly
intuitive, a few examples are provided below.
Simple variable assignment and usage where we put a string into variable X and
then print it to stdout
$ X=12345
$ echo $X
12345
Check if a variable is assigned something or null, in this case it’s assigned
so we print it to stdout
$ X=12345
$ if [ -z "$X" ]; then echo "X is null"; else echo $X; fi
12345
Check if a variable is assigned something or null, in this case it’s not set so
we print “is null” instead of the value.
$ unset X
$ if [ -z "$X" ]; then echo "X is null"; else echo $X; fi
X is null

Brace Expansion

Brace Expansion is a super powerful feature of bash that allows you to write
more compact scripts and commands.  It has many different features and options
described below.  Within braces your syntax is interpreted into a more verbose
syntax depending when you enter into the curly braces.  Let’s look at a number
of examples for Brace Expansion.
Each version of the items in the list in braces is executed. So we go from one
echo command and print 3 versions of the word below separated by spaces.
$ echo {a,m,p}_warehouse
a_warehouse m_warehouse p_warehouse
Expressions in the expansion causes execution multiple times.  To prove this we
use the date and sleep command to validate that the date command is run once
for each iteration of the pattern in the Brace Expansion.
$echo {a,m,p}_$(date; sleep 1)
a_Sun Mar 22 18:56:45 UTC 2020 m_Sun Mar 22 18:56:46 UTC
2020 p_Sun Mar 22 18:56:47 UTC 2020
Expansions using numbers with .. will cause sequential numbers to be expanded
in a numerical sequence
$ echo {1..8}_warehouse
1_warehouse 2_warehouse 3_warehouse 4_warehouse 5_warehouse 6_warehouse
7_warehouse
8_warehouse
Reverse order brace expansion with sequence of numbers
$ echo {8..1}_warehouse
8_warehouse 7_warehouse 6_warehouse 5_warehouse 4_warehouse 3_warehouse
2_warehouse
1_warehouse
Using an optional increment value to specify the numerical increments of brace
expansion
$ echo {1..9..3}_warehouse
1_warehouse 4_warehouse 7_warehouse
Lexicographical brace expansion will iterate through letters in the alphabet in
the order of the locale
$ echo {a..e}_warehouse
a_warehouse b_warehouse c_warehouse d_warehouse e_warehouse
Reverse order lexicographical brace expansion
$ echo {e..a}_warehouse
e_warehouse d_warehouse c_warehouse b_warehouse a_warehouse
Lexicographical brace expansion with increment specified will iterate through a
list of characters from the begin to the end point but skip characters
according the increment value
$ echo {a..z..5}_warehouse
a_warehouse f_warehouse k_warehouse p_warehouse u_warehouse z_warehouse
Multiplicative brace expansion with 2 brace expansions in one command
$ echo {a..e}{1..5}_warehouse
a1_warehouse a2_warehouse a3_warehouse a4_warehouse a5_warehouse b1_warehouse
 b2_warehouse b3_warehouse b4_warehouse b5_warehouse c1_warehouse c2_warehouse
 c3_warehouse c4_warehouse c5_warehouse d1_warehouse d2_warehouse d3_warehouse
 d4_warehouse d5_warehouse e1_warehouse e2_warehouse e3_warehouse e4_warehouse
 e5_warehouse
Brace expansion to use the same root two times in a command.  This creates a
foo.tgz tar file from a directory under name foo.  Its a handy syntax where you
are using it inside another loop and want to assume that the base of the word
is used multiple times.  This example shows it with tar, but it can also be
used withmv_and_cp_as_per_this_example.
$ mkdir foo
$ touch foo/foo{a..e}
$ tar czvf foo{.tgz,}
foo/
foo/foob
foo/fooc
foo/fooa
foo/food
foo/fooe

Parameter Expansion

Parameter expansion is also a nice compact syntax with many capabilities such
as: allow scripts to set default values for unset variables or options, string
substring operations, search and replace substitutions and other use cases. 
Examples are below.
 
Check for null and use the parameter if not null or the default value.  In this
case X is not null so it will be used
$ X=1
$ echo ${X:-2}
1
Check for null and use the parameter if not null or the default value.  In this
case X is null so the default value will be used
$ unset X
$ echo ${X:-2}
2
Check if the variable is NULL and set and echo it if it is NULL.  X is assigned
2 and printed $X.  This can both set the variable and use it in the command
with the ${:=} syntax.
$ unset X
$ if [ -z "$X" ]; then echo NULL; fi
NULL
$ echo ${X:=2}
2
$ if [ -z "$X" ]; then echo NULL; else echo $X; fi
2
Substring expansion will substitute from an offset point a certain number of
characters in the string
$ X="Hello World"
$ echo ${X:0:7}
Hello W
Change the offset to the second character and print 7 characters of substring
$ X="Hello World"
$ echo ${X:1:7}
ello Wo
Substring from beginning of string but cut off last 2 characters
$ X="Hello World"
$ echo ${X:0:-2}
Hello Wor
Get a string length with this version of parameter expansion
$ X="Hello World"
$ echo ${#X}
11
Search and replace within a variable.  In this example replace the first
lowercase o with uppercase O
$ X="Hello World"
$ echo ${X/o/O}
HellO World
Search and replace within a variable but with all matches replaced because of
the leading slash in the search pattern.
$ X="Hello World"
$ echo ${X//o/O}
HellO WOrld
Patterns starting with #, mean the match must start at the beginning of the
string in order to be substituted
$ X="Hello World"
$ echo ${X/#H/J}
Jello World
Example where searching for match at beginning of string, but failing because
match is later in the string
$ X="Hello World"
$ echo ${X/#W/J}
Hello World
Patterns beginning with % will only match at the end of string like in this
example.
$ X="Hello World"
$ echo ${X/%d/d Today}
Hello World Today
Example for end of string match which fails because the match is in the
beginning of string.
$ X="Hello World"
$ echo ${X/%H/Today}
Hello World
Use shopt with nocasematch to do case insensitive replacement.
$ shopt -s nocasematch
$ X="Hello World"
$ echo ${X/hello/Welcome}
Welcome World
Turn off shopt with nocasematch to do case sensitive replacement.
$ shopt -u nocasematch
$ X="Hello World"
$ echo ${X/hello/Welcome}
Hello World
Search for environment variables that match a pattern.
$ MY_A=1
$ MY_B=2
$ MY_C=3
$ echo ${!MY*}
MY_A MY_B MY_C
Get a list of matching variables and then loop through each variable and print
its value
$ MY_A=1
$ MY_B=2
$ MY_C=3
$ variables=${!MY*}
$ for i in $variables; do echo $i; echo "${!i}"; done
MY_A
1
MY_B
2
MY_C
3
Make a string all uppercase
$ X="Hello World"
$ echo ${X^^}
HELLO WORLD

Make a string all lowercase
$ X="Hello World"
$ echo ${X,,}
hello world
 
Make first character of a string uppercase
$ X="george washington"
$ echo ${X^}
George washington
 
Make first character of a string lowercase
$ X=BOB
$ echo ${X,}
bOB

Positional Parameters

Positional Parameters are normally thought of as command line parameters, how
to use them are shown with examples below.
Parameter $0 is the script name that is running and then $1, $2, $3 etc are
command line parameters passed to a script.
$ cat script.sh
echo $0
echo $1
echo $2
echo $3
$ bash ./script.sh apple banana carrot
./script.sh
apple
banana
carrot
Parameter $* is a single variable with all the command line arguments
concatenated.
$ cat script.sh
echo $1
echo $2
echo $*
$ bash ./script.sh apple banana
apple
banana
apple banana
Parameter $# is a number with the quantity of positional parameters passed to a
script in this case below there are 2 arguments passed.
$ cat script.sh
echo $1
echo $2
echo $*
echo $#
$ bash ./script.sh apple banana
apple
banana
apple banana
2

Tilde Expansion

Tilde expansion is commonly seen with usernames and home directories, examples
are shown below.
Tilde Expansion to get the HOME directory of the current user, using just tilde
without the username.
$ echo $USER
root
$ cd ~/
$ pwd
/root
Refer to a specific user’s home directory, not the current user with Tilde and
the username
$ cd ~linuxhint
$ pwd
/home/linuxhint

Arithmetic Substitution

Arithmetic Substitution allows bash to do mathematical operations in the shell
or in a script.  Examples of common usages are shown below.
Simple Arithmetic Substitution with $ and double parentheses
$ echo $((2 + 3))
5
Post increment operator will update the value by one after the current command,
note there is an equivalent post decrement not shown here.
$ X=2
$ echo $((X++))
2
$ echo $X
3
Pre increment operator will update the value by one just before the current
command, note there is an equivalent pre decrement operator not shown here.
$ X=2
$ echo $((++X))
3
$ echo $X
3
Exponent operator can raise a number to a power exponentially
$ echo $((5**2))
25
Left bitwise shift; in this case shift the bits of the decimal number 8 to the
left which essentially multiplies it by 2
$ echo $((8<<1))
16
Right bitwise shift; in this case shift the bits of the decimal number 8 to the
right which essentially divides the number by 2
$ echo $((8>>1))
4
Bitwise AND Operator will compare the numbers bit by bit and and the result
will be the bits that are all set.
$ echo $((4 & 5))
4
Bitwise OR Operator will compare the numbers bit by bit and the results will be
the bits where either of the inputs has the bit set.
$ echo $((4 | 9))
13
Arithmetic equality operator will test for truth and return 1 or 0
$ echo $((4 == 4))
1
Arithmetic inequality operator will test for non-equality and return 1 or 0
$ echo $((4 != 4))
0
The Conditional Operator will test the first argument if true, replace with the
second argument and if false replace with the third.  In this case 5 equals 4+1
so the first conditional is true and 9 is returned.  5 does not equal 4+2 so in
the second echo 7 is returned.
$ echo $(( 5==4+1 ? 9 : 7 ))
9
$ echo $(( 5==4+2 ? 9 : 7 ))
7
You can use hexadecimal numbers in arithmetic expansions, in this case 0xa is
equivalent to 10 and 10+7 = 17.
$ echo $(( 0xa + 7 ))
17

Word Splitting

Using the IFS environment variable to register a delimiter, and using the read
and readarray commands we can parse strings into an array of tokens and then
count the tokens and operate on them.  Examples are shown below.
 
Use IFS parameter as delimiter, read tokens into an array split by IFS which is
set to a space character, and then print out the tokens one by one
$ text="Hello World"
$ IFS=' '
$ read -a tokens <<< "$text"
$ echo "There are ${#tokens[*]} words in the text."
There are 2 words in the text.
$ for i in "${tokens[@]}"; do echo $i; done
Hello
World
User readarray without IFS and specify delimiter in the readarray command. 
Note this is just an example where we split a directory path based on the slash
delimiter.  In this case the code has included the empty string before the
first slash which would need to be adjusted in a real usage, but we are just
showing how to call readarray to split a string into tokens in an array with a
delimiter.
$ path="/home/linuxhint/usr/local/bin"
$ readarray -d / -t tokens <<< "$path"
echo "There are ${#tokens[*]} words in the text."
There are 6 words in the text.
$ for i in "${tokens[@]}"; do echo $i; done
 
home
linuxhint
usr
local
bin

Filename Expansion

When wanting to refer to a list of files or directories in the filesystem, a
bash command or bash script can use Filename Expansion to generate a list of
files and directories from simple commands.  Examples are shown below.
The * character expands to a wildcard and picks up all matching files with the
rest of the wild card string.  Here we pick up all files ending in .txt and
pass them into the du command for checking disk size.
$ touch a.txt b.txt c.txt
$ echo "Hello World" > content.txt
$ du *.txt
0          a.txt
0          b.txt
0          c.txt
4          content.txt
The ? character will only match a single character not an infinite number of
characters, and therefore in this example will only pickup filenames with a
single character followed by .txt.
$ touch a.txt b.txt c.txt
$ echo "Hello World" > content.txt
$ du ?.txt
0          a.txt
0          b.txt
0          c.txt
Characters in brackets expand to match any of the characters.  In this example
a.txt and c.txt are picked up by the expansion
$ touch a.txt b.txt c.txt
$ echo "Hello World" > content.txt
$ du [ac].txt
0          a.txt
0          c.txt
Characters in brackets can be a range of characters and we see here all files
from a to c range followed by .txt suffix are picked up
$ touch a.txt b.txt c.txt
$ echo "Hello World" > content.txt
$ du [a-c].txt
0          a.txt
0          b.txt
0          c.txt

Conclusion

We have covered many types of shell expansions in this article, and I hope the
simple examples can serve as a cookbook for what is possible in bash to make
you more productive with shell expansions.  As further references I recommend
reading the full Bash_Manual, and also the many good articles on NixCraft
website about bash scripting including Shell Expansions.  We have other
articles that may be of interest to you on LinuxHint including: 30_Bash_Script
Examples, Bash_Lowercase_Uppercase_Strings, Bash_Pattern_Matching, and Bash
Split_String_Examples.  Also we have a popular free 3 hour course on Bash
Programming you can find on YouTube.


About the author


Linux Wolfman

Linux Wolfman is interested in Operating Systems, File Systems, Databases and
Analytics and always watching for new technologies and trends. Reach me by
tweeting to @linuxhint and ask for the Wolfman.
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
