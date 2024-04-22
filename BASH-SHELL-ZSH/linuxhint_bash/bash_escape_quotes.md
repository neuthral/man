





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash escape quotes

4 years ago
by Fahmida_Yesmin
Quoting is used to disable the special meaning of the special characters. There
are many shell metacharacters which have specific meanings. But when you need
to represent those characters then it will require to remove the special
meaning of those characters and it is done by quoting the character. You can do
this task by using three ways. These are escape characters, single quotes and
double quotes which are explained with examples in this tutorial.


Escape characters:

Bash escape character is defined by non-quoted backslash (\). It preserves the
literal value of the character followed by this symbol. Normally, $ symbol is
used in bash to represent any defined variable. But if you use escape in front
of $ symbol then the meaning of $ will be ignored and it will print the
variable name instead of the value. Run the following commands to show the
effects of escape character (\).

Example#1:

The meaning of `pwd` command is to display the current working directory path.
In the following example, the value of the `pwd` command is stored in a
variable. When \symbol is used in front of $ symbol then the variable name will
print instead of the value.
$ pd=`pwd`
$ echo $pd
$ echo \$pd
Output:

Single quotes:

When you enclose characters or variable with single quote ( ‘ ) then it
represents the literal value of the characters. So, the value of any variable
can’t be read by single quote and a single quote can’t be used within another
single quotes. Some examples of single quote are shown below.

Example#2:

In this example, a string value is stored in the variable $var. `echo` command
prints the value of this variable without any quotation. When the variable is
quoted by single quote then the variable name will print as output. If the
backslash ( \ ) is used before the single quote then the value of the variable
will be printed with single quote.
$ var='Bash Scripting Language'
$ echo $var
$ echo '$var'
$ echo \'$var\'
Output:

Example#3:

Sometimes it is required to print a single quote inside a string. A single
quoted string  can’t contain another single quote inside the string. You can do
this task by adding backslash in the front of single quote. In the following
example, single quote of don’t word is printed by using backslash.
$ var=$'I don\'t like this book'
$ echo $var
Output:

Example#4:

backticks is not supported by single quotes. In this example, calendar value is
stored into a variable, $var. The value of this variable will print properly by
echo command if you don’t use any quotation. But when the variable is quoted by
single quote in echo command then it prints the variable name instead of the
value of the variable.
$ var=`cal`
$ echo $var
$ echo '$var'
Output:
Double quotes
Double quotes ( ” ) is another way to preserve the literal value of the
characters. The dollar sign ( $ ) and backticks ( ` )  characters can able to
keep their special meaning within double quotes. Backslash ( \ ) can also
retain its value when it is used by following backticks, double quote and
backslash. Some examples of double quotes are shown below.

Example#5:

One limitation of the single quote is that it can’t parse the value of the
variable within the quotation. In this example, a string value is assigned to a
variable named, $var and print the value of that variable using double
quotation in echo command.
$ var='server-side scripting language'
$ echo "PHP is a $var"
Output:

Example#6:

Any command output can be printed by using double quotation. In the following
example, date command is enclosed by double quotation and printed by using
double quotation.
$ echo "Today is `date`"
Output:

Example#7:

You can’t use double quotation within another double quotation to assign any
string value. If you want to print double quote in the output then you have to
use the backslash (\) with the string. In a similar way, you can print
backticks (`) and backslash(\) characters in the output by using the backslash
(\) within the double quotation. In this example, the first command will print
“500” with the double quotation, the second command will print `date` with
backticks and the third command will print “\PHP\” with backslash.
$ echo "The price is \"500\""
$ echo "\`date\` command is used for date value"
$ echo "\\PHP\\ is a programming language"
Output:

Example#8:

Double-quoted and single-quoted strings work same when they are used together
without any space in a print command. But if you use any space between the
string values then they will treat as separate value and print separately. In
this example, three double-quoted strings are used in the first printf command.
These strings will combine together and print as a single string when you will
run the command. Two single-quoted and one double-quoted strings are used in
the second print command and it will work like the first print command. Three
double-quoted strings with space are used in the third print command and each
string value will work as a separate string and print each string in a newline.
$ printf '%s\n' "Ubuntu""LinuxMint""Fedora"
$ printf '%s\n' 'Ubuntu'"LinuxMint"'Fedora'
$ printf '%s\n' "Ubuntu" "LinuxMint" "Fedora"
Output:

Example#9:

Create a bash file named escape.sh, and add the following code. In this
example, a text data with double quotes and dollar sign is used. It is shown
earlier that double quote and dollar symbol can’t print within a string
enclosed by double quotation. So, the backslash is added in front of the double
quotes and dollar symbol to print these. Here, a for loop is used to iterate
the string variable, $string and print each word of the text that is stored in
that variable.
#!/bin/bash
#Initialize the variable with special character
string="The price of this \"book\" is \$50"
#Iterate and print each word of the string variable
for word in $string
do
echo $word
done
Run the script.
$ bash escape.sh
Output:

Conclusion

Hope, this tutorial will help you to use escape characters, single quote and
double quote based on the requirements of your script.


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
