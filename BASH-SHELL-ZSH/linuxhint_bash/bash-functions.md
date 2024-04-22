





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


The Bash Functions In-Depth

1 year ago
by Chrysanthus_Forcha
In the ordinary execution of commands, one command is executed after another.
The first command is executed, then the next command, then the command after,
and the one following, and so on. Imagine a script with one hundred commands,
with each command in a line. It is possible to have two, three, or more
consecutive commands that repeat in different portions of the script. In other
words, the same segment of commands occurs after different unique commands, as
the script is observed from top to bottom.
It would be better to have the segment of commands as one group when it should
first occur. Then, simply call the group each time the group is needed down in
the script. In order to do that, the group needs to be given a name.
A function is a named group of commands that is called whenever it is needed,
down in the script. The group of commands is not executed when the function is
defined at the top of the script. The group is only executed when the function
is called.

* Function_Examples
* Positional_Parameters
* Function_Returning
* Global_and_Local_Scope
* Recursive_Function
* Conclusion


Function Examples


A Function Without Parameters

Consider the following group of commands:
    mkdir myDir
    cd myDir
    touch myfile.txt
The first command creates the directory, myDir. The second command makes myDir
the current directory. The third command creates the file, myFile.txt, in the
current directory. If this code segment were to be repeated three times in a
long script, then it would be better to put it in a function, giving the
function a name. Putting it into a function is defining the function. The
function should be defined at the top of the script and then called three
different times at different points, down in the script. When you run the
script, the group of commands in the function definition is not executed. They
are executed when the function is called down in the script. That is, when you
run the script, the function definition is established but not executed. The
function is executed, when it is called, down in the script.
This function would be defined and called three times as follows:
    PS1='\w\$ '

    function aFn
    {
        mkdir myDir
        cd myDir
        touch myfile.txt
    }

    aFn

    aFn

    aFn
The first line in the script is not part of the function definition or any
function call. It makes the cd command work more effectively. The function
definition begins with the reserved word, “function”. This is followed by
space, then the name of the function. The name of the function is the
programmer’s choice. The name of the function must be followed by whitespace
before “{“. The first command of the function body must be preceded by
whitespace after the “{“. The last command in the body must be separated from
the delimiting ”}” by a newline or “;” or “&”.
In the script, the function has been called three times after the function
definition, with the name of the function being aFn .
The effect of the script is to create a directory called myDir. Inside myDir,
the file myfile.txt is created. Another myDir and nesting myFile.txt are
created, nested in the first myDir. Yet, another myDir and nesting myFile.txt
are created, nested in the second myDir.

A Function With Parameters

Imagine that there are 3 textbooks and 2 exercise books on a table. The total
number of books is 5. The following script shows how this addition and echoing
of result can be done:
    add ()
    {
        sum=$((${1} + ${2}))
        echo $sum ${3}
    }

    add 3 2 "books"
The function definition begins with the name of the function, “add”, given by
the programmer. This is followed by parentheses, preceded with or without
space. That is followed by a “{“, preceded by a whitespace. The commands
follow; and then a new line or “;”, or “&”; and finally ”}”.
When a function does not take arguments (parameters), its definition should
begin with the reserved word, “function”, then the function name, and no
parentheses. When it takes arguments, its definition should begin with the
function name and followed by parentheses.
The last command in the script, calls the function. Its first argument is 3,
its second argument is 2, and its third argument is “books”. If an argument is
a number, it should be typed without quotes. If it is a string of one or more
words, it should be typed in single or double quotes.
In the function definition, the first argument is obtained with ${1}, the
second argument is obtained with ${2}, and the third argument is obtained with
${3}. If there were a fourth argument, it would be obtained with ${4}; and so
on.
Bash by default, adds only integers. A special construct is needed to add two
float numbers or add an integer and a float number. See the example below:

Positional Parameters

${1}, ${2}, ${3}, etc. as used above, are positional parameters. Normal
counting in programming begins with 0. So, what is the use of ${0}? The ${0}
holds the name which is preceded by the path of the Bash script. The following
code illustrates this:
    add()
    {
        sum=`echo ${1} + ${2} | bc`
        echo The sum is $sum for the script ${0} .
    }

    add 3.5 2.4
The output is:
The sum is 5.9 for the script ./temp.com .
Where “./temp.com” is the path and name of the author’s script. Note the line
and its backticks for adding floating point numbers.

Function Returning

In the above function, note where two integers were added. Instead of echoing
the result, the result could have been returned, with the reserved word
“return” as the following script shows:
    add ()
    {
        sum=$((${1} + ${2}))
        return $sum
    }

    add 3 2

    echo $? books
The output is:
5 books
In the function definition, the return command returns the sum. This returned
value is held in the special variable, “$?”.

Global and Local Scope

Consider the following script:
    var=5

    function fn
    {
        var=6
        echo $var
    }

    echo $var
The output is 5. This is because the function was not called. The var outside
the function is in the global scope, and the var inside the function is in the
local scope. Both variables have the same name and should mean the same thing.
When the function is called, its body sees the global scope variable. The
following script illustrates this:
    var=5

    function fn
    {
        var=6
        echo $var
    }

    fn
    echo $var
The output is:
6

6
The function is called before the global variable is echoed at the last two
commands in the script. When the function was called, it saw the global
variable and changed its value from 5 to 6.
The local variable inside the function body can be independent of the global
variable outside the function definition. This is done by declaring the
variable inside the function as local, with the reserved word, “local”. The
following script illustrates this:
    var=5

    function fn
    {
        local var=6
        echo $var
    }

    fn
    echo $var
The output is:
6

5
Because of the reserved word, “local”, the local variable with the same name is
seen only within the function body. In contrast, the global variable with the
same name is seen only outside the function body, not in the function body.

Recursive Function

A recursive function is a function that calls itself repeatedly until a certain
condition is met. The first script above, where the function was called 3
times, can be turned into a recursive function. The condition to be met is 3
calls. This can be done with a counter variable. The following script
illustrates this:
    PS1='\w\$ '

    counter=0

    function aFn
    {
        mkdir myDir
        cd myDir
        touch myfile.txt

        ((counter=$counter + 1))

        if [ $counter -le 2 ]; then
            aFn
        fi

    }

    aFn
Note how the condition to be met has been coded in the if-construct. In the
zeroth pass of the function after it has been called, the counter is 1. In the
first pass of the function, the counter is 2. In the second pass of the
function, the counter is 3. This is a recursive function.

Conclusion

A function is a group of commands that can be called at least once in the
script. A function must have a name given to it by the programmer. The
positional parameters of a function are ${1}, ${2}, ${3}, etc., according to
the order of the arguments. A number as an argument is written without quotes.
A string argument of one or more words is written in quotes. A function can
return a value. The return value is held in the special variable, “$?”. A
variable inside a function body can override a variable outside the function
body, with the reserved word, “local”. A function in Bash can be recursive.
Meaning, after the first call, it can call itself over and over again. In order
to stop recurring, a condition must be met.


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


* How_to_Take_Input_From_a_User_in_Bash_Script_[Advanced_Techniques]
* 10_Cool_and_Awesome_Bash_Loop_Examples
* How_to_Handle_Command_Line_Arguments_in_Bash?
* What_are_Double_Parentheses_in_Bash
* Floating_Point_Math_in_Bash
* Bash_Continue_Built-In_Statement
* 10_Most_Important_Things_to_Know_About_Bash_Scripting

Linux Hint LLC, [email protected]
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
