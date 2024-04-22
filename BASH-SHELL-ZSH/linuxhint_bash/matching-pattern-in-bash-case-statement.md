





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Matching Pattern in Bash Case Statement

1 year ago
by Sidratul_Muntaha
In bash programming, the case statement helps to simplify complex conditionals
when there are multiple different choices. Instead of using nested if
statements, we can use the case statement instead to make the bash code more
readable and maintainable.
The bash case statement shares similarities with JavaScript and C switch
statement. However, the main difference is, once it matches a pattern, it
doesn’t search for any additional pattern match.
This guide will cover the bash case statement basics with various examples.

Bash case statement

The fundamental structure of the case statement is as follows.
case <expression> in

<pattern_1>)

    statements

    ;;

<pattern_2>)

    statements

    ;;
*)

    statements

    ;;

esac
Here’s a brief breakdown of the structure:

* The case statement will start with the keyword “case” and end with the
  keyword “esac”, similar to how if conditional start with “if” and ends with
  “fi”.
* There can be multiple patterns separated by “|”. The “)” operator marks the
  end of the pattern list.
* Patterns can contain special characters.
* Once a pattern is matched, its associated commands will be executed.
  Together, it’s called a clause. Each clause must end with “;;”. It stops any
  attempt to match for further patterns.
* The wildcard (*) clause is a common practice to define the default case. It
  will always match the condition.
* If no pattern matches, then the case statement returns zero. Otherwise, it’ll
  return the exit value of the executed commands.

Having an understanding of the bash_if-else_statement is beneficial in
understanding and mastering the bash case statement.

Bash case statement examples


Case statement using numeric values

Now that we know the basics, time to check it out in action. Have a look at the
following script.
#!/bin/bash

echo -n "Enter value: "

read VALUE

case $VALUE in

        1)

                echo "one" ;;

        2)

                echo "two" ;;

        3)

                echo "three" ;;

        4 | 5)

                echo "greater than three" ;;

        *)

                echo "unknown value" ;;

esac
Save the script. Mark it as an executable.
$ chmod +x sample.sh
Now, run the script.
$ ./sample.sh
The script will ask to enter a value. If the value matches any of the patterns,
it will execute the matching clause. If no match was found, then it will match
the default clause.

Case statement using strings

In the next example, we’ll use strings to match values.
#!/bin/bash

echo -n "Enter planet: "

read PLANET

case $PLANET in

        Mercury | Venus | Earth | Mars | Jupiter | Saturn | Uranus | Neptune)

                echo "$PLANET is a planet from the solar system"

        ;;

        Pluto)

                echo "$PLANET is a dwarf-planet"

        ;;

        "Planet Nine")

                echo "$PLANET not discovered yet"

        ;;

        *)

                echo "Not from the solar system"

        ;;
esac
The script will run just like the first example. It will ask for a planet name,
check if the input matches any clause, and execute the matching clause.
If you examined carefully, you’ll notice that “Planet Nine” is the only value
wrapped in quotes. It’s because there’s space in it. Using quotes, we’re
telling the shell to treat it as part of a single pattern.

Case sensitivity in case statement

Note that in the last example, the input is case-sensitive. This is the default
bash behavior. However, we can tell shell to run the script in case-insensitive
mode.
To do so, add the following line at the start of the script.
$ shopt -s nocasematch
The script should look like this.

Now, test the script. Enter the value with a different case.
$ ./sample.sh

Final thought

This guide covers the basics of bash case statements. It also demonstrates how
to implement them in bash scripts. You should be comfortable using the case
statement. Bash case statements are often used to pass parameters to shell
scripts from a command line. For example, the init scripts use case statements
to start, stop, and restart services. After reading this guide, you will be
able to implement bash case statement in your scripts.
Happy computing!


About the author


Sidratul Muntaha

Student of CSE. I love Linux and playing with tech and gadgets. I use both
Ubuntu and Linux Mint.
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
