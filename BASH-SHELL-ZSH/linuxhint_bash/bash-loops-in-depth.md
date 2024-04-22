





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Loops In-Depth

2 years ago
by Chrysanthus_Forcha
A loop consists of one or more commands that execute repeatedly until a
condition is met. In order for this to happen, the commands have to be in a
construct. The construct and its commands form a compound command. A Bash
command exits with zero if there was no problem. On the other hand, it exits
with a number greater than zero if there was an issue or a problem. The exit
status of a compound command is that of its last command.
In order to understand this article, the reader should already know simple Bash
commands. Any non-simple Bash command used in this article is explained. Do not
forget that Bash commands can be written into a text file, and the text file
can run by typing the name of the file (preceded by path) at the terminal, then
pressing Enter. Do not also forget to permit yourself to run the file with
something like:
sudo chmod +x program_name

Article Content


* Bash_Loop_Basics
* Bash_break_and_continue_Commands
* Useful_Loop_Examples
* Conclusion


Bash Loop Basics

Bash until/done Loop
Consider the following code:
    let n=0

    until [ "$n" -eq 5 ]; do
        echo $n
        ((++n))
    done
The output is:
    0
    1
    2
    3
    4
When the program begins, the variable n is declared and zero is assigned to it.
The two commands before “done” are executed 5 times. ((++n)) increments n by 1
for each iteration. Note the positions of the reserved words, “until”, “do”,
and “done”. The two commands are repeated until the condition, [ “$n” -eq 5 ]
is met. In the condition, “-eq” means “equal to”. The condition is that the
value of n is equal to 5. Note that the values echoed begins from 0 to 4. This
is because, for each iteration, the condition of the construct is checked,
before the body (two commands) of the construct is executed. If the condition
is false, the body would not be executed. The reserved word, “done”, should
always be typed in a new line.
The syntax for the until/done loop is:
until test-commands; do consequent-commands; done
The second semicolon is not necessary if the reserved word, “done” is typed in
a new line.
If the condition exits with zero, meaning true, the body of the loop is
executed. If the condition exits with a number greater than zero, meaning
false, the body of the loop is not executed.
Bash while/done Loop
This loop is similar to the until/done loop, except that the condition has to
be rephrased. Both constructs use the “do” reserved word. The following code
produces the same output as before:
    let n=0

    while [ "$n" -lt 5 ]; do
        echo $n
        ((++n));
    done
In the condition in the code, “-lt” means “less than”. The syntax for the
while/done loop is:
while test-commands; do consequent-commands; done
Bash for/done Loop
There are two syntax for the “for” loop, which are:
for (( expr1 ; expr2 ; expr3 )) ; do commands ; done
and
for name [ [in [words …] ] ; ] do commands; done
The following code uses the first syntax to produce the same result, as above:
    for ((n=0; n < 5; ++n)); do
        echo $n
    done
In the ((compound command, the first expression initializes the variable n to
zero. The next expression is the while condition. The last expression in the
double parentheses compound command is the increment expression. Then there is
the body, which may consist of more than one command, and then “done”.
The second syntax is best used with an array – see below.

Bash break and continue Commands

break
All the iterations (repeated execution of the body) intended for a loop must
not necessarily be executed. The break command can be used to stop the
remaining iterations. In the following code, the iterations stop just after n
equals 2.
    for ((n=0; n < 5; ++n)); do
        echo $n
        if ((n == 2)); then
            break
        fi
    done
The output is:
    0
    1
    2
In this loop, three iterations have taken place.
continue
An iteration can be skipped using the continue command. The following code
illustrates this:
    for ((n=0; n < 5; ++n)); do
        if ((n == 2)); then
            continue
        fi
        echo $n
    done
The output is:
    0
    1
    3
    4
The iteration to display 2 has been skipped.
The break and continue commands can also be used in the until/done and while/
done loops.

Useful Loop Examples

until/done Loop Example
The command to create an empty text file is touched. The following script will
create empty text files in the current working directory, until the number of
files created, is 4:
    let i=1
    file="myFile"

    until [ $i -eq 5 ]; do
        filename="$file$i.txt"
        touch $filename
        ((++i))
    done
The names of the files created should be myFile1.txt, myFile2.txt, myFile3.txt,
and myFile4.txt.
The only semicolon in the code can be omitted if “do” is typed in the next
line.
while/done Loop Example
The command to create an empty directory is mkdir. The following script will
create empty directories in the current working directory until the number of
directories created is 4:
    i=1
    dir="myDir"

    while [ $i -lt 5 ]; do
        dirname="$dir$i"
        mkdir $dirname
        ((++i))
    done
The name of the directories created should be myDir1, myDir2, myDir3, and
myDir4.
The only semicolon in the code can be omitted if “do” is typed in the next
line.
for Loop Example
The second syntax for the for-loop mentioned above is:
for name [ [in [words …] ] ; ] do commands; done
This syntax is better used with a list. In simple terms, the syntax is:
for Variable in List; do commands; done
The list can be an array. The following command reads an input line of text
from the terminal into the array arr:
read arr
As the script is running, when it reaches this command, it will pause (with a
flashing cursor) for the user to enter input. If the user types:
one two three
in one line and presses Enter, then the first element of the array would have
the word “one”, the second would have the word “two”, and the third would have
“three”. Note that the input values were separated by spaces.
The following code uses the second for-loop syntax to read and display an input
to the script:
    echo "Type in values and press Enter:"

    read arr

    for var in $arr; do
        echo $var
    done
If the input was:
one two three
Then the output would be:
    one
    two
    three
The only semicolon in the code can be omitted if “do” is typed in the next
line.

Bash select Command

The select command is not really a loop. However, it involves iteration, which
is not coded by the programmer. In simple terms, the select command syntax is:
    select item in [list]
    do
        [commands]
    done
Here, “select”, “in”, “do”, and “done” are reserved words. One use of the
select command is to display the items from the list to the terminal. The
following script illustrates this:
    select item in banana, lemon, orange, pear, pineapple
    do
        break
    done
Note the use of the break command. The output is:
    1) banana,
    2) lemon,
    3) orange,
    4) pear,
    5) pineapple
    #?
The list consists of the values banana, lemon, orange, pear, and pineapple.
These values have been displayed and numbered. The symbol “#?” (and the
flashing cursor next to it) is expecting the user to type in something and
press the Enter key. Type anything, then press the Enter key and finally ends
the execution of the script.
Notice that the list has been displayed as a menu, numbered, for the output.
With this, the user can select an item in the menu by typing the corresponding
number, next to “#?”, then press the Enter key. The following script
illustrates how orange is selected by typing the number 3:
    select item in banana, lemon, orange, pear, pineapple
    do
        echo $REPLY
        break
    done
The output display is:
    #? 3
then
    3

Conclusion

A loop in Bash is a construct; a construct is a compound command. The body of
the construct has at least one command. As of now, Bash has just three loops,
which are until/done, while/done, and for/done. Each loop uses the reserved
word “do”. After the condition has been typed, “do” should be preceded by ‘;’,
or be typed in the next line of the code. Each loop takes a condition. The
until/done and while/done loops are similar. The main difference occurs when
coding the condition.
The select command is a compound command, but it is not really a loop. It
allows the user to select an item from a menu list when the script is running
interactively.
The break and continue commands can be used in a loop. The break command can be
used to stop the iterations. On the other hand, the continue command can be
used to skip an iteration.
That is all there is to Bash loops. The feature remaining to be studied is “How
to Code the Conditions?”. This deserves a whole different article and cannot be
included in this one. See the article on this website, titled “Bash
Conditionals In-Depth”, on how to code conditions.
Chrys


About the author


Chrysanthus Forcha

Discoverer of mathematics Integration from First Principles and related series.
Master’s Degree in Technical Education, specializing in Electronics and
Computer Software. BSc Electronics. I also have knowledge and experience at the
Master’s level in Computing and Telecommunications. Out of 20,000 writers, I
was the 37th best writer at devarticles.com. I have been working in these
fields for more than 10 years.
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
