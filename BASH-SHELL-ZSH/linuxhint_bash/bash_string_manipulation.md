





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash string manipulation

3 years ago
by Nicholas_Shellabarger
In bash, not unlike any other programing language, a program lives to put
things into buckets and name them for later use. These buckets are available to
manipulate throughout the lifetime of the program or until discorded manually
or deemed no longer necessary. The program lives to manipulate buckets.
What is referred to above as buckets is what we call variables in most
programming languages. Furthermore, building onto the basic concept of a
variable, a concept we call typing is introduced.
Typing is a name for expected storage and assignment behavior of a variable.
So, how does this look when we return to buckets?
In the little bucket world, we have created for our programs, buckets have
names. That’s it.
Now suppose that our programs don’t have the luxury of having an infinite
number of Jetson bags at their disposal to use as buckets. Before a bucket is
named and filled with its contents, the program must decide the shape and
constitution of every bucket it touches. I know it seems a little overkill but
it is a necessary evil.  All buckets are bound by their type.


String Manipulation in Bash

How does this look when we return to bash?
Functions, arrays, and strings are stored in variables. Bash uses what we call
attributes to flag changes in behaviors on assignment. Despite there being a
system to modify the behavior of variable assignment, when it all comes down to
it, values are stored in variables as strings.
In bash, a program lives to put strings into variables and name them for later
use. These strings are available to manipulate throughout the lifetime of the
program. The program lives to manipulate strings.
Here we will cover bash string manipulation in breath and as much depth as
possible to be accessible to readers of all makes and shapes. Read on.

What is string manipulation in bash

String manipulation is an operation on a string changing its contents. In bash,
string manipulation comes in two forms: pure bash string manipulation, and
string manipulation via external commands. Here we will touch both types of
string manipulation.
Suppose that we have a variable in bash holding a string we wish to manipulate
named string. In the case that more than one string exists, we name the strings
string, string2, … Also, we may opt to name a string something more meaningful
than string to promote understanding of the string content and intended use.

Concatenate Strings — Listing strings in a string

In bash, the easy way to concatenate strings is to list strings in order. The
resulting string is a new string containing all strings listed.
${string1}${string2}…
Example: String concatenation by listing strings in string
{
string="one";
string2="two";
string3=${string}${string2};
echo ${string3}
}
Output
onetwo

Listing strings in an array

In bash, another way to concatenate strings is to list strings in an array and
use parameter expansion to expand array into the concatenated string. However,
unlike the example above, removing white space separating array elements may
require extra work.
array(${strings} ${strings2} …)
Example: String concatenation by listing strings in an array
{
strings=("one" "two");
echo ${strings[@]}
}
Output
one two

Shorten A String — Shift a string to the left

One way to shorten a string is to shift its contents to the left. String
contents shifted to the left disappear, resulting in a shorter string.
Example: Shift left loop
{
string="abcdefghijklmnopqrstuvwxyz";
for i in $( seq 0 $(( ${#string} - 1 )) );
do
echo ${string:${i}};
done
}
Output
abcdefghijklmnopqrstuvwxyz
bcdefghijklmnopqrstuvwxyz
cdefghijklmnopqrstuvwxyz
defghijklmnopqrstuvwxyz
efghijklmnopqrstuvwxyz
fghijklmnopqrstuvwxyz
ghijklmnopqrstuvwxyz
hijklmnopqrstuvwxyz
ijklmnopqrstuvwxyz
jklmnopqrstuvwxyz
klmnopqrstuvwxyz
lmnopqrstuvwxyz
mnopqrstuvwxyz
nopqrstuvwxyz
opqrstuvwxyz
pqrstuvwxyz
qrstuvwxyz
rstuvwxyz
stuvwxyz
tuvwxyz
uvwxyz
vwxyz
wxyz
xyz
yz
z

Shift a string to the right, get string substring

Another way to shorten a string in bash is to get the substring of a string.
The resulting operation can be used to implement a shift operation to the right
similar to the method above.
Example: Shift right loop
{
string="abcdefghijklmnopqrstuvwxyz";
for i in $( seq 0 $(( ${#string} - 1 )) );
do
echo ${string:0:${#string}-i};
done
}
Output
abcdefghijklmnopqrstuvwxyz
abcdefghijklmnopqrstuvwxy
abcdefghijklmnopqrstuvwx
abcdefghijklmnopqrstuvw
abcdefghijklmnopqrstuv
abcdefghijklmnopqrstu
abcdefghijklmnopqrst
abcdefghijklmnopqrs
abcdefghijklmnopqr
abcdefghijklmnopq
abcdefghijklmnop
abcdefghijklmno
abcdefghijklmn
abcdefghijklm
abcdefghijkl
abcdefghijk
abcdefghij
abcdefghi
abcdefgh
abcdefg
abcdef
abcde
abcd
abc
ab
a

Example: Shift loop pyramid

For fun, let’s combine the two shift loop examples above to draw a step in our
terminal.
Example: Shift loop step
{
string="abcdefghijklmnopqrstuvwxyz";
{
for i in $( seq 0 $(( ${#string} - 1 )) );
do
echo ${string:0:${#string}-i};
done
} | tac;
{
for i in $( seq 0 $(( ${#string} - 1 )) );
do
echo ${string:${i}};
done
}
}
Output
a
ab
abc
abcd
abcde
abcdef
abcdefg
abcdefgh
abcdefghi
abcdefghij
abcdefghijk
abcdefghijkl
abcdefghijklm
abcdefghijklmn
abcdefghijklmno
abcdefghijklmnop
abcdefghijklmnopq
abcdefghijklmnopqr
abcdefghijklmnopqrs
abcdefghijklmnopqrst
abcdefghijklmnopqrstu
abcdefghijklmnopqrstuv
abcdefghijklmnopqrstuvw
abcdefghijklmnopqrstuvwx
abcdefghijklmnopqrstuvwxy
abcdefghijklmnopqrstuvwxyz
abcdefghijklmnopqrstuvwxyz
bcdefghijklmnopqrstuvwxyz
cdefghijklmnopqrstuvwxyz
defghijklmnopqrstuvwxyz
efghijklmnopqrstuvwxyz
fghijklmnopqrstuvwxyz
ghijklmnopqrstuvwxyz
hijklmnopqrstuvwxyz
ijklmnopqrstuvwxyz
jklmnopqrstuvwxyz
klmnopqrstuvwxyz
lmnopqrstuvwxyz
mnopqrstuvwxyz
nopqrstuvwxyz
opqrstuvwxyz
pqrstuvwxyz
qrstuvwxyz
rstuvwxyz
stuvwxyz
tuvwxyz
uvwxyz
vwxyz
wxyz
xyz
yz
z

Capitalize the whole string in Bash

In bash4 or later you can capitalize the printable characters using parameter
expansion as follows.
${string^^}
Suppose that we throw the first 10 words of the output from the Shift loop step
example into a variable called pyramid. Note that unmodified, the expected
behavior of echoing its content is as follows.
Command
echo ${pyramid}
Output
a ab abc abcd abcde abcdef abcdefg abcdefgh abcdefghi abcdefghij
Notice that as you would expect, there are no caps. Let’s blow it up. That is,
we are going to make all of its characters caps.
Command
echo ${pyramid^^}
Output
A AB ABC ABCD ABCDE ABCDEF ABCDEFG ABCDEFGH ABCDEFGHI ABCDEFGHIJ
That was easy!  How about if we want to only convert the first letter in a
string to caps like a sentence?  Yes, we can! All we need to do is try a little
less hard, one character less to be exact.

Capitalize only the first letter in a string

Maybe capitalizing the whole string is not the bash string manipulation
technique you are looking for. What if you only need to capitalize the first
letter like a sentence?
Commands
pyramid="a ab abc abcd abcde abcdef abcdefg abcdefgh abcdefghi abcdefghij"
echo ${pyramid^}
Output
A ab abc abcd abcde abcdef abcdefg abcdefgh abcdefghi abcdefghij
Now suppose that we are more interested in converting strings into lowercase.
Luckily, there is a pure bash way to do this; that is use parameter expansion.

Convert the whole string to lowercase in Bash

Convert a string to all lowercase in bash by using the double-comma ( “,,”)
parameter expansion operator.
Commands
{
pyramid="A AB ABC ABCD ABCDE ABCDEF ABCDEFG ABCDEFGH ABCDEFGHI ABCDEFGHIJ";
echo ${pyramid};
echo ${pyramid,,}
}
Output
A AB ABC ABCD ABCDE ABCDEF ABCDEFG ABCDEFGH ABCDEFGHI ABCDEFGHIJ
a ab abc abcd abcde abcdef abcdefg abcdefgh abcdefghi abcdefghij

Convert only the first letter in a string to lowercase

Convert the first character in a string lowercase in bash by using the single-
comma ( “,”) parameter expansion operator.
Commands
{
pyramid="A AB ABC ABCD ABCDE ABCDEF ABCDEFG ABCDEFGH ABCDEFGHI ABCDEFGHIJ";
echo ${pyramid};
echo ${pyramid,}
}
Output
A AB ABC ABCD ABCDE ABCDEF ABCDEFG ABCDEFGH ABCDEFGHI ABCDEFGHIJ
a AB ABC ABCD ABCDE ABCDEF ABCDEFG ABCDEFGH ABCDEFGHI ABCDEFGHIJ

Assign an empty string a value and return its value

Often you want to set a fallback for an empty string and have its value persist
throughout a bash script such as the case when optionally accepting variables
from the environment. This can be accomplished using parameter expansion.
Commands
{
echo [${str}];
echo [${str:=empty}];
echo [${str}]
}
Output
[]
[empty]
[empty]
Notes
str is assumed to be unassigned

Reverse a string in Bash

One common string manipulation is reversing a string. Although there are ways
to reverse a string using an external command in bash. Here we will do it the
pure bash way using parameter expansion.
Commands
seq ()
{
{
local ubound;
ubound="${1}"
};
local i;
for i in $( eval echo {1..${ubound}} );
do
echo ${i};
done
}
reverse-string ()
{
{
local instr;
instr="${@}"
};
for i in $( seq ${#instr} );
do
echo -n ${instr:$(( ${#instr} - ${i} )):1};
done
}
reverse ()
{
local str;
read -t 1 str;
reverse-string ${str}
}
Source: reverse-string.sh
Example
{
reverse-string LinuxHint.com Rules!;
echo LinuxHint.com Rules! | reverse;
echo LinuxHint.com Rules! | reverse | reverse
}
Output
!seluRmoc.tniHxuniLLinuxHint.comRules!

Bash String Manipulation Exercises


  1. Modify reverse-string.sh so that space between words is preserved
  2. Modify reverse-string.sh to support multibyte characters


Randomize a string, rearrange as an anagram

In the last example, we reversed a string. Here we will do something different.
That is, instead of reversing a string, why not rearrange its letters into an
anagram? We will. Here’s how.
Commands
anagram() { { local instr ; instr="${@}" ; }
local i
for i in $( seq ${#instr} | sort --random-sort )
do
echo -n ${instr:$(( ${#instr} - ${i} )):1}
done
}
Source: anagram.sh
Example
{
for i in {1..10};
do
{
echo "$( anagram abracadabra )";
sleep 1
};
done
}
Output
adraaabrbca
arcbaaaradb
abcraadraab
bcaraadbara
dacraabarab
cadraaabarb
baarabacrda
raabaabcdar
bbdaararaac
cabrdabaraa
Notes:
anagram is identical to reverse-string in the previous example with the
exception that it uses the sort command to rearrange the output of seq in
random order.

Replace a pattern occurring in a string once  in Bash

We have a string sitting in a variable and want to replace the first occurrence
of a substring. Here’s how.
Basic usage
${str/pattern/replacement}
Commands
{
str="0110110001101001011011100111010101111000011010000110100101101110011101000010111
0011000110110111101101101";
echo ${str};
echo ${str/111/000}
}
Output
0110110001101001011011100111010101111000011010000110100101101110011101
0000101110011000110110111101101101

0110110001101001011000000000010100001000011010000110100101100000000001
0000100000011000110110000101101101

Replace all occurrences of a pattern in a string in Bash

We have a string in a variable and want to replace all occurrences of a
substring. Here’s how.
Basic usage
${str//pattern/replacement}
Commands
{
str="011011000110100101101110011101010111100001101000011010010110111001110
10000101110011000110110111101101101";
echo ${str};
echo ${str//111/000}
}
Output
01101100011010010110111001110101011110000110100001101001011011100
111010000101110011000110110111101101101

011011000110100101100000000001010000100001101000011010010110000000
00010000100000011000110110000101101101

How to manipulate strings in bash using external commands

To manipulate strings in bash using an external command, we need to use a
feature that the bash manual calls command substitution. In short, whatever is
inside $( ) or ` ` is treated as a command and substituted in place. Frankly, I
prefer the first way; however, you may use either. The easy way to use command
substitution is to assign the result of command substitution to a variable as
follows.
Commands
result=$( command )
In the case of string manipulation using an external command in bash, we would
need to pipe the echo of a string to the command, unless passing the string to
the command as a parameter is accepted. Here is what the new result should look
like.
Commands
result=$( echo "${result}" | command )
Now, let’s try doing something real. However, reduce a string containing words
to the last word in the string? For this example, let’s use the external
command gawk.
Notes on the following commands. Let’s make everything lowercase and get rid of
periods. The quote is by Linus Torvalds. It is a really popular quote.
Commands
{
quote="Talk is cheap. Show me the code.";
last_word=$( echo "${quote//./}" | gawk '{print $(NF)}' );
echo "${last_word,,}"
}
Output
code

Bottom line on string manipulation in bash

Here we covered how to manipulate strings the pure bash way as well as using
external commands. For pure bash string manipulation techniques, a feature
called parameter expansion was used. On the other hand, for the case of
external commands, command substitution was used.  Admittingly, in writing this
piece, I improved my ability to manipulate strings in bash. Hopefully, you did
as well.
Note that the topic of this discussion was not treated in entirety. However,
exercises are left for those that would like to tinker a little more. For other
string manipulations not contained in this article, you may contact me directly
or contact the editor.
That’s enough string manipulation, for now … Thanks,


About the author


Nicholas Shellabarger

A developer and advocate of shell scripting and vim. His works include
automation tools, static site generators, and web crawlers written in bash. For
work he tools with cloud computing, app development, and chatbots. He codes in
bash, python, or php, but is open to offers.
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
