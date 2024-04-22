





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash declare command

4 years ago
by Nicholas_Shellabarger
Bash doesn’t have a strong type system. To allow type-like behavior, it uses
attributes that can be set by a command. ‘declare’ is a bash built-in command
that allows you to update attributes applied to variables within the scope of
your shell. In addition, it can be used to declare a variable in longhand.
Lastly, it allows you to peek into variables.
Here you will find out that you are blind or using the bash declare command.
At this point you are thinking, what do I need to know to use the declare
command in bash? At the time like these, the man command comes in handy. I’m
just going to paste the part about declare in bash builtins here.
Here are some help commands to see what it looks like in your terminal. Note
that the last one is a failsafe for our friends running Git Bash in Windows.
Help commands for bash declare

* man bash (and find the section about declare
* or bash help declare

Now that you have read the primer, man page for declare in bash, it is time to
get our hands dirty with some examples of bash declare in the wild. Note that
as you scroll down deep into the jungle of bash declare examples, your pay
grade and level of understanding of declare will improve.
First let’s start out by seeing if anyone declared a variable called bar. If no
one has yet, dibs!
declare -p bar
If you see the error bash: declare: bar: not found, then no one has yet. Let’s
just echo $? to be sure.
1, okay good. Otherwise, you should see something like declare -- bar="". If
you haven’t yet, go ahead and declare bar as something, bar= or declare bar=
should do the trick. Note that the latter of the two is the longhand for
variables in bash. If you are wondering what the -- in declare output is, that
is where variable attributes go, and there are none.
Now that assigning variables using declare is out of the picture, let’s start
giving them attributes.


Namerefs

If you are running bash v4.3-alpha or later, this section on the -n option. If
you are not sure, check using the bash --version command. Otherwise, don’t try
this at home.
declare –n foo=bar
Look at that. We just asigned a variable to another by name. Look what happens
here.
bar=x
declare -n foo=bar
echo ${foo} ${bar} #  x x
foo=y
echo ${foo} ${bar} #  y y
true
Now look what happens when when we don’t use declare with the -n option.
bar=x
declare foo=bar
echo ${foo} ${bar} #  x x
foo=y
echo ${foo} ${bar} # y x
true

Exports

Now suppose that we tried to do something odd like this:
echo{,} \${bar} > echo-bar.sh
bash echo-bar.sh
As you may suspect, nothing happened in standard output. Don’t worry about the
voodoo in the first line. Programmers are lazy.  The declare command can make
names export!
declare -x bar # export bar
Now give it a try.
bash echo-bar.sh # x
Note that using the –x option for declare can also be done through the export
command as follows. Be sure to open up a new shell or remove the attribute
using the +x option before trying out the following example.
bar=x
echo{,} \${bar} > echo-bar.sh
bash echo-bar.sh #
export bar
bash echo-bar.sh # x

Integers

In bash, variables may have the integer attribute and the only way to
accomplish this is through declare command.
Suppose that we are dealing with integers and want to make our variables
behavior more responsible. We could give such variables the integer attribute
using the –i option for declare.
declare –i bar # don’t know what’s in bar anymore but now it’s an integer
echo ${bar} # x (maybe)
bar=x
echo ${bar} # 0
bar=1
echo ${bar} # 1
bar=3.14 # ouch
true
Note that now when we try to assign a new value to our variable 3 things
happen: 1) The value is interpreted as 0; 2) The value is interpreted as an
integer; 3) Error.
In addition to modifying the value assignment behavior, variables now behavior
differently in arithmetic expressions as follows.
declare -i bar=1
declare car=1
echo ${bar} # 1
echo ${car} # 1
bar=bar+1
car=car+1
echo ${bar} # 2
echo ${car} # car+1
true
Note that you can still get away with using a variable to store an integer and
carry out arithmetic without setting the integer attribute for a variable but
it is there just in case.

Cases

In bash, variables may have case attributes applied on assignment. Declare
allows conversion to cases lower or upper if –l or –u options are set,
respectfully.
declare -u uppers=
declare -l lowers=
uppers=uppercase
lowers=LOWERCASE
echo ${uppers} # UPPERCASE
echo ${lowers} # lowercase
echo ${uppers,,} # uppercase
echo ${lowers^^} # LOWERCASE
true
These attributes may come in handy if you require single case without having to
do the conversion yourself.

Readonly

In bash, variable may be readonly. To accomplish this there is the -r option
for declare.
declare –r lowers # try to make lowers final
lowers="Yet another lowers"
echo ${lowers} # yet another lowers
declare -rl final_lowers="Yet another lowers"
echo ${final_lowers} # yet another lowers
final_lowers="Yet again another lowers" # assignment block
true
This attribute could come in handy if you know that a variable has no business
being changed after assignment. Note that the +r option does not work; that is
stripping a variable of its readonly attribute is not allowed in bash.

Arrays

In bash, variables may be arrays. To make a variable an associative or indexed
array, the –A and –a options for declare are used, respectfully.
declare -a indexed_array
declare -A associative_array
indexed_array[0]=1
associative_array[0]=1
indexed_array[one]=2 # ?
associative_array[one]=2
echo ${indexed_array[0]} # 2
echo ${associative_array[0]} # 1
echo ${indexed_array[one]} # 2
echo ${associative_array[one]} # 2
declare -p indexed_array
declare -p associative_array
echo ${indexed_array[2one]} # ouch
true
In most programming languages having the ability to use arrays is a powerful
construct. Bash is no exception. It allows this through array attributes which
could come in handy if requiring hash lookup or in implementing object-like
behavior. Note that the index of indexed arrays behaviors like a variable with
the integer attribute, thus is expected to break in the same manner, hence the
last line before true.

Trace

In bash, variable may have the trace attribute applied via the -t option in
declare. Trace variables unlike variables with other attributes applied depend
heavily on the environment of the calling shell.
I have found mixed results using the trace attribute which have led to a review
on traps and applications of trapping the DEBUG and RETURN signal. For those
that tinker, finding a use for declaring a variable with the -t option is extra
credit.

Functions

In bash, one of the most useful uses for the declare command is being able to
display functions. The -f and -F options for declare display definition and
just function names if available, respectfully.
Suppose that you want to have a fallback in case a function is not defined in
your shell. We can use declare to accomplish this task as follows. For
simplicity sakes, let’s use a function called foo.
# if foo is not declared
# declare it
# else use available foo
test ! "$( declare -F foo )” || {
foo() { true ; }
}
For those that tinker, there is an alias using called commands that I cooked up
a while back that uses declare to check if functions are available.

Conclusion

Although most programmers can get away with not having to use it at all, like
most builtins, the declare command in bash is an essential command to really
know your way around the bash shell.


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
