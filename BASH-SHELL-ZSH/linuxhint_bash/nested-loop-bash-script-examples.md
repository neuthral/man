





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Nested Loop in Bash Script Examples

2 years ago
by Sidratul_Muntaha
In programming or scripting, the loop is one of the most basic and powerful
concepts. A loop is performing certain tasks until the specified conditions are
met. Each programming or scripting language has different ways of implementing
the concept.
In this guide, check out the nested loop in bash scripting.

Nested loop

A loop, by definition, is performing certain tasks until the conditions are
met. What if the task includes running a loop? This is the concept of a nested
loop. A loop within a loop.
This is the basic structure of a loop.
while (condition){

        # something

}
Here, the while loop will keep on performing the tasks declared inside the
block as long as the condition is met. In the case of a nested while loop, the
structure would look like this.
# main loop

while (condition){

        # nested loop

        while(condition){

                # something

        }

}
In theory, nested loops can go to infinite depth. In many situations, nested
loops can be the perfect solution.

Loop in bash script

Bash is a powerful scripting language. There are different loop structures in
the bash. The most popular ones are for, while, and until loops. If you’re
familiar with C/C++ programming before, then the syntax will definitely look
quite similar.
For loops
For loop is one of the most common and versatile forms outputs etc. The
structure of loops in bash scripting. The structure also resembles for loop in
C/C++ a lot.
The structure of for loop in bash is as follows.
for ((initialize ; condition ; increment)); do

# something

done
The structure is very self-explanatory. The initialization section isn’t
mandatory. However, the condition and increment are higher priority.
Let’s put it into action. Here’s a very simplistic bash script that implements
for loop.
for ((i = 0 ; i < 5 ; i++)); do

        echo "hello world"

done
It’s also possible to use list/range as the loop condition. It’s especially
useful if working with a list of files, number ranges, arrays, command outputs,
etc. The structure looks something like this.
for item in <list>; do

# something

done
For example, the following script will print “hello world” five times.
for i in {1..5}; do

        echo "hello world"

done
What if we need to work with the contents of a directory? In the following
example, the script will print all the files in /usr/bin directory.
for i in /usr/bin/*; do

        echo $i

done
Now, what do we do to have a nested for loop? It’s just one for loop inside
another. Here’s a nested for loop using the previous example.
for ((i = 0 ; i < 3 ; i++)); do

        for((j = 0 ; j < 2 ; j++)); do

                echo "hello world"

        done

done
The output will be “hello world” 6 times. The outer loop will run three times,
running the inner loop two times.
While loops
The while loop is another popular and intuitive loop available in bash
scripting. The syntax looks like this.
while <condition>; do

# something

done
In the following example, the script will print “hello world” five times.
num=1

while [ $num -le 5 ]; do

        echo "hello world"

        num=$(($num+1))

done
What would it look like to have a nested while loop? Here’s a simple example.
num_a=1

num_b=1

while [ $num_a -le 5 ]; do

                while [  $num_b -le 5 ]; do

                        echo "hello world"

                        num_b=$(($num_b+1))

                done

        num_a=$(($num_a+1))

done
Until loops
If you have a programming background in C/C++, then you are familiar with the
do-while loop. Unfortunately, bash doesn’t have anything like that. However,
until the loop operates in a similar fashion. The syntax also looks quite the
same.
until [ <condition> ]; do

# something

done
The difference between the while and until the loop is the test condition. As
long as the test condition is true, a while loop will keep running. An until
loop, however, will keep running only if the condition is false.
Here’s a quick example of the while loop. It’ll print the multiplication table
of 2.
num_a=1

until [ $num_a -gt 10 ]; do

        echo $(($num_a * 2))

        num_a=$(($num_a+1))

done

Loop break

In certain situations, if certain conditions are met, running the rest of the
loop becomes redundant. Loop breaks are an interesting feature that allows
breaking out of the loop at a given condition. It’s more important for nested
loops as the higher the loops, the more resource consumption and inefficiency.
Here, the following for loop will stop executing as soon as it reaches the
condition.
for ((i=1;i<=100;i++)); do

        echo $i

        if [ $i -eq 10 ]; then

                break

        fi

done

Check out how_to_break_while_loop for in-depth explanation and demonstration of
loop breaks.

Final thoughts

A nested loop is a simple and powerful concept to understand and implement.
Hopefully, this guide was able to describe and demonstrate the concept.
Interested in more bash scripting guides? Check out the following guides.

* Bash_infinite_loop
* Bash_script_user_input
* Bash_function_returning_array

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
