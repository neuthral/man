





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Sed Examples

3 years ago
by Nicholas_Shellabarger
Bash allows you to perform pattern replacement using variable expansion like ($
{var/pattern/replacement}). And so, does sed like this (sed -e ‘s/pattern/
replacement/’). However, there is more to sed than replacing patterns in text
files.  Here we will rediscover sed, by example, with equivalent commands and
workflows to aid in day to day tasks.

Setup for sed examples

Here is a quick guide to get set up for the example, which I will try not to
make too overkill.
“words” is a text file containing the numbers 1 through 100. If you are unsure
of the command to create it, see Export function for xargs in Bash_Export
Command. You never know it may be on your next shell scripting interview.
“bar” is a text file containing a single line —.
“old-php” is a text file containing lines of old PHP that will break in php7 or
later. (Hint: ereg)
Note that all the functions described above can be found below in Endnote on
functions for setup.

Sed examples with equivalent commands

In a command line environment, you will find there is more than one solution to
a given task. However, for the most part, you want to go with the path that
yields the least resistance. Here is a list of examples sed commands with
corresponding equivalent commands, where some will be covered in detail below.
1. Print a random line (equivalent to sort -R – | head -1)
sed -n "$(( RANDOM % 100 ))p" -
2.Print the last line in file (equivalent to head -1 -)
sed -n '$p' -
3. Print the first 10 lines in a file (equivalent to head -n 10 -)
sed '10q' -
4. Print the first line in a file (equivalent to tail -1 -)
sed -n '1p' -
5. Delete all instances of a character (equivalent to tr –delete ‘0’ -, where 0
is the character we want to delete)
sed -e 's/0//g' -
6. Convert csv file to tsv (equivalent to tr ‘,’ ‘\t’ -)
sed -e 's/,/\t/g' -
7.Append line to file (equivalent to cat bar -)
sed '$a ---' -
8. Prepend line to file (equivalent to cat – bar)
sed '1i ---' -
9. Print out all lines in file (equivalent to cat -)
sed -n -e 'p' -
10. Print a lines matching a pattern (equivalent to grep -e ‘^1’ -)
sed -n -e '/^1/ p' -
11. Delete lines matching a pattern (equivalent to grep -v -e ‘^1’ -)
sed -e '/^1/ d' -
12. Get the number of lines in a file (equivalent to wc -l -)
sed -n -e '$=' -
13. Write to a file in the background(equivalent command tee)
sed "w ${1}" -

Example using sed to implement the tee command

Right above, there is an example labeled Write to a file in the background.
Kind of sounds like the tee command. Well, it is. Here we will expand on how to
implement a function to replace tee in bash using sed.
Commands
tee ()
{
  test ${#} -eq 1 || return;
  sed "w ${1}" -
}
main ()
{
  seq 10 | tee ten;
  cat ten
}
main
Output
1
2
3
4
5
6
7
8
9
10
1
2
3
4
5
6
7
8
9
10
Here you will see two listings of the integers from 1 to 10. The first is from
the seq command. The second we get from the cat of the file written in tee. I
know it is ridiculous but it works!

Example using sed to print out a random line in a file

Suppose that we want to print out a random line in a file using bash and a
little bit of sed. Can we do it? Yes, we can! Here’s how.
Implement a function that

  1. Gets the number of lines in a file, L
  2. Generates a random number between 1 and L, R
  3. Prints R

The function expects the input to be piped from the outside.
Commands
some-line ()
{
  function lc ()
  {
    sed -n -e '$=' -
  };
  function print-line ()
  {
    sed -n -e "${1}p" -
  };
  temp=$( mktemp );
  cat - > ${temp};
  cat ${temp} | print-line $(( RANDOM % $( cat ${temp} | lc ) + 1 ));
  rm ${temp}
}
Example usage (1)
seq 100 | _
Output (1)
35
Example usage (2)
curl https://linuxhint.com/bash_cut_command/ --silent | strip-tags | some-line
See the example below, using sed to strip HTML tags. Note that the over example
sometimes returns blank for empty lines. As an exercise, it can be improved.

Using sed to print lines in a file

Suppose that you want to implement a function in bash to print out a given line
in a file. Trying to print a single line in a file using a loop in bash, head,
tail, or awk is too much work for printing out lines in a file. Good thing we
have sed. The resulting function using sed would be as follows.
Commands
print-line ()
{
  sed -n "${1}p" -
}
Now let’s see what happens when we use print-line on words.
Commands
words | print-line 50
Output
50
Okay. Looks good but let’s try something that looks a little less trivial.
Commands
declare -xf words
declare -xf print-line
seq 1 10 $( words | wc -l ) | xargs -i  bash -c "words | print-line {}"
Output
1
11
21
31
41
51
61
71
81
91
Okay. Now that is more like it! You see how sed may be used in a bash script to
print out any line in a file.

Sed examples without equivalent commands

In a command-line environment, sometimes the path to a solution yielding the
least resistance is the sed way; otherwise, you end up doing more work than
required in the first place. Some commands may be featured below.
Command all lines in a shell script
sed -e 's/^/#/' -
Delete first line
sed -e '1d' -
Delete last line
sed -e '$ d' -
Insert a line before lines matching a pattern
sed '/0$/i ---' -
Insert a line after lines matching a pattern
sed '/0$/ ---' -
Strip out html tags
sed -e 's/<[^>]*.//g' -
Upgrade ereg in old php code to run in php7 or later
sed 's/ereg(\([^,]*\).\([^)]*\)./strpos(\2,\1)/g'
Check if sed is earlier than a certain version
sed -e 'v 4.5' -

Example sed version branching in bash

Above in the examples, there is a line to Check if sed is earlier than a
certain version that we can use to implement version branching in bash, which I
believe is easier than trying to implement a function to compare version
numbers from sed –version output. That only pitfall is that if there is an
earlier version of sed that doesn’t support the v command, then we are in
trouble.
Commands
test-sed-version-at-most() {
  echo -n | sed "v ${1}" - 2>/dev/null
}
try-version ()
{
  echo -n "Version ${1}. Okay. Do it the ";
  test-sed-version-at-most ${1} && {
    echo -n "old";
    true
  } || {
  echo -n "new"
  };
  echo " way."
}
main ()
{
  local v;
  for v in 4.{4,5};
  do
    try-version ${v};
  done
}
main
Output
Version 4.4. Okay. Do it the old way.
Version 4.5. Okay. Do it the new way.
Note that the version of sed running on my machine as of typing these
characters is 4.4, which would explain the output above. Also, at the same
time, the latest version of gnu sed was 4.7, about 3 years older than the one I
have. My sed is old! In fact, in sed 4.0.6, a parameter was added to the
version command so this strategy works for any said at least v4.0.6, which is
lenient considering that version was released in early 2003. You are good.
I did some extra digging, actually NEWS reading out of the latest source code.
Version 4.6 has a new feature, –debug which dumps the script and annotates
output lines. This would allow you to translate sed scripts generated by
functions in bash to canonical form. Cool! Just don’t forget that you need sed
version branching in bash. That is where this sed example comes into play.

Example bash function using sed to strip HTML tags

In the examples above there is a line to Strip out HTML tags. Let’s throw that
into a bash function and use it to strip out all the HTML tags from the last
article I wrote.
Commands
strip-tags ()
{
  sed -e 's/<[^>]*.//g' -
}
curl https://linuxhint.com/bash_cut_command/ --silent | strip-tags
I can’t say that it’s perfect but at least it’s readable in the terminal.

Sed examples with workflows: Example workflow: safely replace all using find,
grep, and sed

It is safe to say that changes made using sed with the -i option are
irreversible. That is unless you are completely sure what text is to be
replaced, you are likely to end up with one less character than intended. That
is why in this example, we’ll use sed in a workflow to safely replace text in
all files you have selected.
Workflow

  1. find
  2. grep
  3. sed


find

Here you will select the files to be subject to replacement. I suggest using a
command along these lines:
find -type f -name | grep -v –e | xargs -i  ...
For example, you may want to limit the files to replace PHP files excluding git
repository directories as follows.
find -type f -name \*.php | grep -v -e '.git' | xargs -i ...
Read more on the xargs_command_in_bash.

grep

Next, we are going to try and match some_pattern in the files selected as
follows. Note that since we are using the -o option for grep, the output will
only show matched string if any.
find -type f -name \*.php | grep -v -e '.git' |
xargs -i grep -e some_pattern -o
The command above should return a list of string matching some_pattern.

sed

Finally, we want to replace all string matching some_pattern. To do that we
need to convert grep into sed as follows.
find -type f -name \*.php | grep -v -e '.git' |
xargs -i sed -i -e s/some_pattern/replacement/g
The grep command becomes sed -i and the -o option is removed. And there you
have it.
Now you can check what strings are going to be replaced in sed beforehand
instead of testing your luck.

Endnotes on options used in examples

Here is a list of options used in the sed examples discussed briefly.

Option Description
       Edit in place. If the input is a file (not piped in) the result of
-i     expressions will overwrite the contents of the file.
       Sed accepts one
       eg) sed -n …
       -e stands for expression. Its parameter is an expression in the sed
       language.
-e     Sed accepts many
       eg) sed -e ‘expr1′ -e ‘expr2’ …
        
       Hides line not affected by the expression. That is if the expression is
       a print statement in the sed language, then lines not included in the
-n     print statement will not be included in the output.
       eg) sed -n …
        

For more on sed options available, see sed –help

End notes on equivalent commands use in examples

The following command-line utilities are included in the sed examples with
equivalent commands.

* sort
* head
* tail
* grep
* cat
* Tr
* tee


Endnote on the trailing – in example equivalent commands

In case you are wondering what is going on the – character in the example, this
note is for you. I added a – character after most commands in the examples to
hint that we expect the input to be received through a pipe. That is,
cat some-file | sort -R - | head -1
However, when the command on the left hand the pipe is present, we can omit the
hint as follows.
cat some-file | sort -R | head -1
That is what was going on with the – character after commands in the examples.

Endnotes on functions for setup

In case you are looking, here are functions to the setup for the above
examples. The output obtained using declare -f. Read more on the declare
command_in_bash for more usages.
Commands
words ()
{
  seq 100
}
bar ()
{
  echo ---
}
old-php ()
{
  echo 'ereg($UA,"Bottybot")'
}

Bottom line

I enjoyed writing Bash sed examples and even picked up a few extra tricks along
the way. Sed is a powerful command-line utility and expressive language for
manipulating text files. If you liked learning about sed, don’t worry there is
still a lot more yet to be touched. Sed on.


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
