





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Bash && Operator in Linux

10 months ago
by Taimoor_Mohsin
The Bash logical (&&) operator is one of the most useful commands that can be
used in multiple ways, like you can use in the conditional statement or execute
multiple commands simultaneously. Generally speaking, the logical operator is
the one that is used to connect more than one expression and then provides the
output based on their combined result.
Similarly, bash shell is designed to handle one task at a time. As a result, if
you’re working on a large project, then waiting for the first command to
execute before typing the next one is a stressful process. But the Bash &&
operator can solve this and make it possible to run multiple commands
simultaneously. In that way, you can make your large project more concise,
easily readable, and time-efficient using this command that will be discussed
in this article.

How to use Bash && (AND) logical operator with conditional statements

Let’s take an example and create a bash script with “bashifcondition.sh” and
use the logical operator “&&” (AND) with the conditional statements. For that,
we will create a program where we will take any number from the user and then
check if the number is even or odd and if it is divisible by ten or not. So
first, we will create a bash script and then write a code as shown below
$ nano bashifcondition.sh

!/bin/bash

    echo "Enter a number"

read num

if [ $((num % 2)) == 0 ] && [ $((num % 10)) == 0 ];

then

    echo "$num is even and also divisible by 10"

else

    echo "$num is odd and not divisible by 10"

fi
After that we will run this bash script and see its output by typing:
$ bash bashifcondition.sh
For code verification, we have taken two different numbers which are 20 and 13,
respectively, and try to see the code behavior for these numbers. So when we
enter ’20’, you can see that it is divisible by 2 and 10, making it an even
number. On the other hand, when we enter 13, it is not divisible by 2 and 10,
making it an odd number, so the output in both cases is correct.

Logical operator && (AND) truth table: You can also follow the truth table for
the logical && operator to see its functionality

Condition 1 Condition 2 Output
True        True        True
True        False       False
False       True        False
False       False       False


How to use && (AND) operator to run multiple commands

You can also use the logical bash operator && (AND) to run multiple commands
simultaneously. For example, let’s create a new bash script by typing:
$ nano testbash.sh
After that, you need to write the same command discussed earlier by typing.
#!/bin/bash

sudo apt update && sudo apt upgrade
Later you need to save this bash script by pressing “CTRL+O” and then exit by
pressing “CTRL+X“. Now, after that, you need to run the bash script in the
terminal that will give you the same output as before by typing
$ bash testbash.sh
Now let’s take another example of a bash script in which we will take input
from the user to create a file name using the “read” command and then display
the directory where this file has been created using the “pwd” command. So the
code for this description is mentioned below
#! /bin/bash

echo "Enter the text file name:"

read fileName

touch $fileName && echo "File has been created in" && pwd
After running this bash script, you will get its output, as shown below:

Conclusion

Bash && command is a logical operator that can be used in various ways, such as
you can use this command in conditions, or it can be used to run multiple
commands simultaneously, so you don’t need to run them individually. This is
super useful, primarily if you work on large projects, making your code more
concise and clear. So in this article, we have provided some examples of the
Bash && operator as to how you can utilize it in your everyday bash scripting.


About the author


Taimoor Mohsin

Hi there! I'm an avid writer who loves to help others in finding solutions by
writing high-quality content about technology and gaming. In my spare time, I
enjoy reading books and watching movies.
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
