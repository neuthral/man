





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Echo Newline in Bash

9 months ago
by Sidratul_Muntaha
In Bash, there are multiple ways we can display a text in the console or
terminal. We can use either the echo or printf command to print a text. Each of
these commands has their unique behaviors.
In this guide, we’ll learn how to print a newline in Bash.

Newline in Bash

Before going further, here’s a quick refresh on what a newline is. It’s usually
used to specify the end of a line and to jump to the next line. It’s expressed
with the character “\n” in UNIX/Linux systems. Most text editors will not show
it by default.

Printing Newline in Bash

There are a couple of different ways we can print a newline character. The most
common way is to use the echo command. However, the printf command also works
fine.
Using the backslash character for newline “\n” is the conventional way.
However, it’s also possible to denote newlines using the “$” sign.

Printing Newline Using Echo

The echo command takes a string as input and prints it out on the console
screen. To print any text, we use the echo command in the following manner:
$ echo "The Quick Brown Fox"
As mentioned earlier, the newline character is “\n”, right? How about we try to
include it directly with echo?
$ echo "The\nQuick\nBrown\nFox"
Well, that didn’t go as expected. What happened?
By default, the echo command will print the string provided, character by
character. It doesn’t interpret backslash characters. However, we can fix this
by adding the flag “-e”. It enables backslash character interpretation. Let’s
fix the command and run it again:
$ echo -e "The\nQuick\nBrown\nFox"
Voila! Now it’s working as expected!
This technique also works when using Bash variables. Take a look at the
following example:
$ sentence="The\nQuick\nBrown\nFox"

$ echo -e $sentence

Printing Newline Using $

We can also use the “$” sign with the echo command to specify the newline
character. This method is a bit more complex than the previous one. The
explanation is best done with an example.
Run the following command:
$ echo The$'\n'Quick$'\n'Brown$'\n'Fox
Here,

* The given string isn’t inside double quotations.
* Before each newline character “\n”, we’re using the “$” sign.
* Each newline character “\n” is provided inside single quote.


Printing Newlines with Multiple Echo Statements

In this approach, we’re basically going to run multiple echo commands instead
of one. By default, echo prints the given string and adds a newline character
at the end. By running multiple echo statements at once, we’re taking advantage
of that.
Let’s have a look at the following example.
$ echo The; echo Quick; echo Brown; echo Fox
Here,

* We’re running 4 echo commands.
* Each command is separated by a semicolon (;). It’s the default delimiter in
  Bash.


Printing Newline with Printf

Similar to echo, the printf command also takes a string and prints it on the
console screen. It can be used as an alternative to the echo command.
Have a look at the following example.
$ printf "The\nQuick\nBrown\nFox\n"
As you can see, printf processes backslash characters by default, no need to
add any additional flags. However, it doesn’t add an additional newline
character at the end of the output, so we have to manually add one.

Final Thoughts

In this guide, we’ve successfully demonstrated how to print newlines in Bash.
The newline character is denoted as “\n”. Using both the echo and printf
commands, we can print strings with new lines in them. We can also cheat (well,
technically) by running the same tool multiple times to get the desired result.
For more in-depth info about echo and printf, refer to their respective man
pages.
$ man echo
$ man printf
Interested in Bash programming? Bash is a powerful scripting language that can
perform wonders. Check_out_our_Bash_programming_section. New to Bash
programming? Get started with this simple and comprehensive guide on Bash
scripting_tutorials_for_beginners.
Happy computing!


About the author


Sidratul Muntaha

Student of CSE. I love Linux and playing with tech and gadgets. I use both
Ubuntu and Linux Mint.
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
