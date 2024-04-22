





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Define Multiline String Variable

1 year ago
by John_Otieno
Let’s assume you have encountered a scenario where you need to define a
multiline block of string in your Bash scripting operations. If you try the
default way of defining a variable in Bash, you are bound to encounter an error
or an incomplete part of the variable.
This quick guide will show you methods of defining multiline string variables
using escape characters and Heredoc.

Bash Escape Characters

Bash, like most programming languages, provides the ability to use escape
characters. Escape characters allow us to invoke a new interpretation of
character sequences. Although Bash has various escape characters, we only need
to concern ourselves with \n (new line character).
For example, if we have a multiline string in a script, we can use the \n
character to create a new line where necessary.
An example of such a use case is:
#!/bin/bash
str= “this is a string\n-and another one\n-and another one\n-and the final one”
echo -e $str
Executing the above script prints the strings in a new line where the \n
character exists.

HereDoc

The above method works fine for simple line text. However, if we need to print
a text with other special characters, backlashes, and quotes, it becomes
unnecessarily complex. To solve such an issue, we can use HereDoc.

What is a Heredoc?

A heredoc is a special-purpose code block that tells the shell to read input
from the current source until it encounters a line containing a delimiter.
The syntax for Heredoc in Bash is:
COMMAND << DELIMITER

…

Heredoc Block

…

…

DELIMITER
Delimiters in a Heredoc can be any string. However, the most common strings are
EOF, EOM, or END.
Once the shell encounters the delimiter, it replaces all the variables,
commands, and special characters and then passes the information inside the
Heredoc block to the main command.
You can include special characters, regular strings, variables, and other shell
commands in the Heredoc block.
Ensure to terminate the Heredoc block with the delimiter. Do not add any
whitespace before the delimiter.

Multiline String Using Heredoc

Suppose you have the following string:
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta http-equiv="X-UA-Compatible" content="IE=edge">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Document</title>

</head>

<body>

</body>

</html>
Inside a bash script, we can create a varible and pass the string above to cat
as shown below:
#!/bin/bash

string=$(cat << EOF

<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta http-equiv="X-UA-Compatible" content="IE=edge">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Document</title>

</head>

<body>

</body>

</html>

EOF

)

echo $string
Once you run the above script, you will see an output a:
As you can see, we can print the entire string, including all special
characters.

Conclusion

For this guide, we discussed how to define and use a multiline string in a bash
script. However, there is more to Heredoc than discussed here. Consider the
followingresource_to_learn_more.


About the author


John Otieno

My name is John and am a fellow geek like you. I am passionate about all things
computers from Hardware, Operating systems to Programming. My dream is to share
my knowledge with the world and help out fellow geeks. Follow my content by
subscribing to LinuxHint mailing list
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
