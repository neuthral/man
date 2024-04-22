





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How Do You Escape a Single Quote in Bash?

1 year ago
by Aqsa_Yasin
We need to quote our sayings or items through single or double quotes whenever
we want to specify something. But using quotes, we eliminate the actual meaning
of the special characters using inside them. Sometimes, it’s necessary to
remove the quotes to elaborate something or a code in a new way. So to do this,
we use some escape characters inside the quoted body. These characters are as
follows:

* This might be a backslash (\). This should not be quoted.
* Another one is a dollar sign ($). This sign is mostly used to declare a
  variable in bash. But to escape the single quotes, we use them differently. A
  dollar sign along with the backslash is mostly used.


Example 1

Moving towards the first example, we will start with the basics of removing the
quotes from the line or the piece of code. Take a variable as “a” is the
variable used here to store a string value like $a. The string is enclosed in
single quotes. The term “echo” is used to take print of the value of that
particular variable. You will see that the single quotes are removed from the
string. If you use single quotes with the variable name and take a print of
that, you will know that only the variable name is displayed and not the value
inside it. Similarly, if you use a backslash “\” before the single quotes, the
string is again coded with the single quotes.
$ a=’C sharp is a good programming language’

$ echo $a

$ echo ‘$a’

$ echo \’$a\’

Example 2

Sometimes while accomplishing any task, such a situation occurs where we feel
the requirement to take print of a single quote inside the string. A single
quote is not used where there is already a quoted string. So you can overcome
this issue by using a backslash following the single quote. Here the backslash
and a quote are used in the “don’t” word. The whole string is accompanied by
the ‘$’ sign at the start of the declaration of the variable.
$ x=$ ‘I like eating but I don\’t like swimming’

$ echo $x
When we print the variable, we will get the value without single quotes.

Example 3

Everything has some cons and pros. One pro of using a single quote is that if
its variable is used inside the quotation, it is not printed as it is assigned
to the variable. For instance, here, “b” is a variable having a single-quoted
string. We take a print of that variable through the echo command. Here the
variable is used inside the double-quoted quotation so that the whole string is
displayed without any quotes.
$ b=’Front end designing’

$ echo “HTML is used for $b”
In other words, a quotation inside the quotation is used here to create a
simple string.

Example 4

Both single and double-quoted strings act similarly when they are used together
in any command. But when you use space between them, then they work as a
separate string. Here we have used three strings in different ways.
Firstly we have used these strings that are double-quoted with space between
them. You will see that these three values are displayed separately in a new
line. Three strings are now used with double quotes and without any space
between them. From the result, you will observe that they appear as a single
string. All three separate strings are combined without any quote.
$ printf ‘%s\n’ “Linux” “Windows” “MacOS”
Now there is some change in this command. One double-quoted string surrounded
by two single-quoted strings is used in the third print. The result of this
command is the same as in the second print.  The single and double quotes are
removed from all three strings, and these strings are printed collectively.
$ printf ‘%s\n’ “Linux”“Windows”“MacOS”

$ printf ‘%s\n’ ‘Linux’“Windows”‘MacOS’

Example 5

Moving towards another example, we need to create a file with an extension of
.sh named “file.sh”. After creation, edit it by using the bash code. As it is
known that the dollar sign is not compatible with the inverted commas. So to
use them collectively, we need a backslash following the dollar sign in the
string that is double-quoted.
a=”In “Biology” I got \$80”
For printing purposes, we will use the “for” loop. This will print all the
words in the string that we have given to the variable.
For word in $a

Do

Echo $word
After writing the code, now save the file with the .sh extension. Go to the
terminal to get the output. Write the given command:
$ bash file.sh
It is displayed that all the elements are displayed without any quote. Because
of the loop, the resultant items are present in a new line.

Example 6

This example is related to the use of double quotes inside the single-quoted
strings. These double quotes have blank space in them. In this example, we have
taken two strings that are separated with double-quotes. This will end with a
plain string without single and double-quotes.
$ printf ‘%s\n’ ‘Linu$ux’””’ubu\ntu’

Example 7

The next example is a sort of taking a risk. But to use any simple sentence
without quotation, we have to use consecutive steps. This is a risk-taking
example because it needs the involvement of the folder’s name. But it is
necessary for the explanation of this current concept of escaping the quotes
from the string. The first step is to enlist all the folders and files of your
system, and this can be done by using the respective command.
$ ls
You will see all folders and files name hereafter this it’s time to introduce
the values of a string to the variable. One thing that should be noted here is
that we will use an asterisk at the start of the string; this will show you the
unquoted string along with all file names and folders. This method is not
similar to those examples that are defined earlier. If you use an asterisk at
the end, then this will show all the file names at the end of the string in the
result.
$ X=’ * I am a good student’

$ printf  ’*%s\n’  ${x}
The output shows that the single quotes are also removed by using the above-
mentioned example. We can also remove the asterisk sign from the string, but it
is the same method as described earlier in the article.

Example 8

This example is related to the concatenation method of combining two strings
just to remove the single quotes from both of them. One string is defined here,
whereas the other one is a constant.
$ a=’The price of this book is:’
Now take print of this variable along with the constant value.
$ printf ‘%s\n’ “$a” ‘$200’
From the output, you can see that both strings are written together without
single quotes.

Conclusion

I hope this guide will be favorable for you regarding the usage of escape
characters, the single and double quotes according to your requirements in
handling bash properties.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
