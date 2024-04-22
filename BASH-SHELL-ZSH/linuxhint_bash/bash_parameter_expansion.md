





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Parameter Expansion

3 years ago
by Fahmida_Yesmin
The parameter is used in bash to store data. Different types of data can be
stored in the parameter, such as integer, string, array, etc. by using built-in
declare keyword.  The parameter can be a positional parameter, special
parameter, and variable. Normally, ‘$’ symbol is used to print or assign the
value of a variable, for example, ‘x=$y’. ‘$’ symbol is used for parameter
expansion also that has various types of uses in bash. Parameter expansion can
be used to modify, expand or replace the value of the parameter. The optional
braces are used with the variable when using variable parameter expansion, such
as ‘echo ${myvar}’. How parameter expansion can be used in bash for various
purposes are shown in this tutorial.

Syntax:

Some mostly used bash parameter expansion syntaxes are given below.

Parameter Expansion         Description
${variable:-value}          If the variable is unset or undefined then expand
                            the value.
${variable:=value}          If the variable is unset or undefined then set the
                            valueto the variable.
${variable:+value}          If the variable is set or defined then expand the
                            value.
${variable:start:length}    Substring will retrieve from the start position to
                            length position of the variable.
${variable:start}           Substring will retrieve from start position to the
                            remaining part of the variable.
${#variable}                Count the length of the variable.
${variable/pattern/string}  Replace the part of the variable with string where
                            the pattern match for the first time.
${variable//pattern/string} Replace all occurrences in the variable with string
                            where all pattern matches.
${variable/#pattern/string} If the pattern exists at the beginning of the
                            variable, then replace the occurrence with string.
${variable/%pattern/string} If the pattern exists at the end of the variable,
                            then replace the occurrence with string.
${variable#pattern}         Remove the shortest match from the beginning of the
                            variable where the pattern matches.
${variable##pattern}        Remove the longest match from the beginning of the
                            variable where the pattern matches.
${variable%pattern}         Remove the shortest match from the end of the
                            variable where the pattern matches.
${variable%%pattern}        Remove the longest match from the end of the
                            variable where the pattern matches.

Parameter expansion can be categorized by three groups. These are conditional
parameter expansion, substring parameter expansion, and substitute parameter
expansion. The uses of these parameter expansions are explained with examples
in the next part of this tutorial.

Example-1: Conditional Parameter Expansion

These types of parameter expansions are used to check the variable is set or
unset
The following command will check the variable, $myvar is set or unset. If
$myvar is unset, then the string ‘bash’ will print.
$ echo "${myvar:-bash}"
The following command will print the value of $myvar if it is set.
$ echo $myvar
The following command will set the value, ‘bash’ to $myvar and print ‘bash’ to
the terminal if $myvar is unset.
$ echo "${myvar:=bash}"
Now, check the variable is set or unset by the following command.
$ echo $myvar
The following command will print, ‘python’ to the terminal if $myvar is set
before.
$ echo "${myvar:+python}"
Again, Run the following command to check the current value of $myvar.
$ echo $myvar
Output:
The following output will appear after running the above commands.

Example-2: Substring Parameter Expansion

Substring parameter expansion is used for various purposes, such as cut any
portion of the string, count total characters of the string, etc. The string
value can be cut in various ways. The uses of substring parameter expansions
are shown in the next part of this tutorial.
The following command will assign “Bangladesh” to the variable, $mystr.
$ mystr="Bangladesh"
The following command will cut six characters from $mystr starting from
position 0.
$ echo "${mystr:0:6}"
The following command will cut all characters from $mystr, starting from
position 6.
$ echo "${mystr:6}"
The following command will count and print the total number of characters of
$mystr.
$ echo "${#mystr}"
Output:
The following output will appear after running the above commands.

Example-3: Substitute string using Parameter Expansion

Different types of parameter expansions can be used to substitute string value.
The uses of parameter expansion for substituting the string value are shown in
this part of the tutorial.
The following command will assign the value, “First In First Out” in the
variable, $newstr.
$ newstr="First In First Out"
The following parameter expansion will replace the string, “First” by the
string “Last” of the variable, $newstr. Case-sensitive search will apply for
this replacement.
$ echo "${newstr/Fast/Last}"
The following parameter expansion will replace all occurrences of the string,
“First” by the string “Last” of the variable, $newstr. Case-insensitive search
will apply for this replacement.
$ echo "${newstr//Fast/Last}"
Output:
The following output will appear after running the above commands.
The following command will assign the value, “Eat to live not live to eat” to
the variable, $string.
$ string="Eat to live but not live to eat"
The word, “eat” is appeared two times in the variable, $string.  The following
command will replace the word, “Eat” by “Work” that appears at the beginning of
$string.
$ echo "${string/#Eat/Work}"
The following command will replace the word, “eat” by “work” that appears at
the end of $string.
$ echo "${string/%eat/work}"
Output:                                
The following output will appear after running the above commands.
The following command will store the value “Web Programming Language” to the
variable, $var.
$ var="Web Programming Language"
The following parameter expansion will remove the word, “Web” from the
beginning of the variable, $var.
$ echo "${var/#Web}"
The following parameter expansion will remove the word, “Language” from the end
of the variable, $var.
$ echo "${var/%Language}"
Output:
The following output will appear after running the above commands.

Conclusion:

Bash parameter expansion is a very useful feature of Linux. It helps the Linux
user to perform different types of string related operations very easily
without any built-in function. Different types of string assignment, cutting
string and replacement operations are shown in this tutorial by using bash
parameter expansion. Hope, the reader will be able to perform string related
tasks more efficiently by using parameter expansion after reading this
tutorial.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
