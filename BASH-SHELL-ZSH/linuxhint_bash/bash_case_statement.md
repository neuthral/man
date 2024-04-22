





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use the Bash Case Statement

3 weeks ago
by Karim_Buzdar
The case statement is generally used in Bash when you have multiple choices to
select from. Using it instead of nested if-else statements helps keep your Bash
scripts easier to read and maintain.
The Bash case statement has been designed similar to the case statement from
JavaScript and C. Unlike the switch statement from C, the Bash case statement
stops searching for other matches as soon as it finds one and completes the
statements that are written for the pattern.
In this guide, we will explain how you can use the Bash case statement using
two examples and some scenarios in Ubuntu 22.04.

Syntax of the Case Statement

If you want to understand how to use the case statement, you need to understand
the syntax. It looks like this:
case $variable in
pattern1)
commands
;;
pattern2)
commands
;;
patternN)
commands
;;
*)
commands
;;
esac
Let’s break it down:

* It’s imperative that you open up the statement with the “case” keyword and
  close it out with the “esac” keyword.
* We use the closing bracket “)” to terminate a pattern.
* Patterns containing commands are known as clauses and they end with “;;”.
* You can use an “*” (asterisk) to define a default case.
* When the case command matches the input variable with the defined patterns,
  upon a match, the corresponding set of commands code are executed up to the
  double semicolons.
* If you want the same command to be executed for multiple patterns, you can
  use the pipe operator to put the patterns together as such:

case $variable in
     pattern1| pattern2)
      commands
      ;;
     pattern3| pattern4)
      commands
       ;;
Now, let’s take a look at a couple of examples to understand this syntax
better.

Holidays in a Month

For our first example, let’s write a script that takes a month as input from
the user and responds with an international holiday that falls in the month.
The “shopt -s nocasematch” command allows your script to ignore the case of the
input and match it with the cases irrespective of that.
#!/bin/bash

#code to ignore case restrictions
shopt -s nocasematch

#case statement
echo "Please enter the name of a month"
read month
case $month in
January)
echo " 18th January is the National Thesaurus Day"
;;
February)
echo " 20th February is the World Social Justice Day"
;;
March)
echo "29th March is Little Red Wagon Day."
;;
April)
echo "1st April is International Pillow Fight Day"
;;
*)
echo "Couldn’t find any holiday in your specified month”
esac
In this script, we take the name of a month from the user and store it in a
variable named “month”. Then, using the case statement, we compare the input
with some pre-selected months and then display the respective holiday. You can
see that if the code doesn’t find any match in the defined cases, it then have
an echo outside the cases to display another message. And after that, we close
the case code structure with the “esac” keyword.
Save the script file and exit out of the nano editor. Run the script using the
following command:
$bash month.sh
You can see that the code responded with the relevant holiday for the input
that was catered to with cases, and responded with unknown when the input was
out of range from the programmed cases.

The Official Language of a Country

Let’s write a script that utilizes the composite cases. For this example, let’s
write a script that takes a country and prints the official language of that
country.
#!/bin/bash

#code to ignore case restrictions
shopt -s nocasematch

#case statement
echo "Enter a country: "
read country
echo "The official language of $COUNTRY is "
case $COUNTRY in
  America | London)
   echo "English"
    ;;
  Brazil | Portugal | Mexico)
    echo "Spanish"
    ;;
  China | Singapore | Taiwan)
    echo "Mandarin"
    ;;
  *)
    echo "unknown"
    ;;
esac

Case Statement with Integers

You can also create the cases where you have to match the input with integers
as well. Let’s create a script that takes the input from the users in the range
of 1-10, and then displays if the number is even or odd.
#!/bin/bash

#case statement
echo "Enter a number from 1 to 10: "
read num
case $num in
“1” | “3” | “5” | “7” | “9”)
echo “Your input is an odd number”
;;
“2” | “4” | “6” | “8” | “10”)
echo “Your input is an even number”
;;
*)
echo “Your input is outside the required range”
;;
esac
Running this script gives you the following output:
You can test with the other numbers as well.

Case Statement with For Loop

You can use the case statement within the for-loops if you want to check
multiple input values against your set cases. Let’s illustrate this case by
writing a script that goes through all of the files in the current directory
and display their file type.
#!/bin/bash

#for every file in the current directory
for File in $(ls)
do
    #extract the file extension
    Extension=${File##*.}
case “$Extension” in
sh)
echo “Bash Script File: $File”
;;
png)
echo “PNG Image File: $File”
;;
txt)
echo “Text File: $File”
;;
*)
echo “Unknown File”
;;
Esac
done
Running this script goes through every file in the current active directory and
displays it along with its file type (only the cases we specified). As you can
see, when running this script that we only have one file in the current
directory, it displays that along with the extension.

Conclusion

Going back to your older code and figuring out what line does can be a very
cumbersome task, especially if it was written by somebody else. Adding to it is
even harder. Using the case statement in your Bash scripts can make it very
easy for you to keep it readable through the easy syntax.
As demonstrated with the examples, you can use it with strings, multiple
strings, integers, and for loops, among many others. You can even handle the
exit codes for your program with case statements. It’s very versatile.
If you face any issues using the case statement, feel free to engage us and
we’ll gladly help you out.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
