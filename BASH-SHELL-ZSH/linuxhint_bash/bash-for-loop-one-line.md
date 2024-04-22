





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash for Loop in One Line

1 year ago
by Sidratul_Muntaha
In any programming or scripting language, the loop is a quintessential feature.
Loops are generally to perform a repetitive task until a certain condition is
met. Bash is a powerful scripting language that supports all the major features
of a scripting language (including loops).
This guide demonstrates one-line for loops in Bash.

Bash for loop

The bash features multiple loop types – for, while, and until. Each type of
loop comes with a different structure. However, the fundamentals remain the
same. For beginners, this guide explains in-depth_about_various_bash_loops and
how to implement them.
As the title of this guide suggests, our focus will be on the loop. While for
loop generally requires multiple lines, we can represent it in a single line if
the loop is simple enough. This process, however, requires an understanding of
the fundamentals_of_bash_for_a_loop.
To run our bash codes, we need a shell script. I already have a dummy script to
run our codes.
$ cat dummy.sh

For loop structure

This is the basic structure of the bash for loop.
for  in [list]
    do
       
done
Here’s a quick for loop example implementing this structure.
for i in {1..5}
do
    echo "number: $i"
done
Bash also supports C-style for loop. If you have programming background in C,
then C-style for loop will be easy to understand.
for ((; ; ))
do
   
done
Let’s put the C-style for loop in action.
for ((i = 1; i <= 5; i++)); do
    echo "number: $i"
done
For loop can also work with files. In the following example, the loop will
search all the partitions under the disk “/dev/sda” and print all of it.
for i in /dev/sda*; do
    echo "$i"
done

One line for loop

With the basics covered, we can now compress for loops into a single line.
Basically, we’ll eliminate the newlines from the entire for loop code. We can
also run these loops directly from the command line.
Let’s compress the first example. If we eliminate all the new lines, the code
will look like this.
$ for i in {1..5}; do echo "number: $i"; done
As you can see, all the new lines are removed. Instead, those newlines are
replaced with semicolons (;).
We can do the same with C-style for loops.
$ for ((i = 1; i <= 5; i++)); do echo "number: $i"; done
Have a look at the following example. All the configuration files inside “/
etc.” will be copied as a backup to the “~/backup” directory.
$ for i in /etc/*.conf; do cp $i /home/viktor/backup; done

For loop with conditionals

In many cases, a loop will contain conditionals to make decisions at various
points of the repetition.
Here, the following for loop will print all the even numbers within a fixed
range.
for i in {1..10}; do
    if [ $((i%2)) -eq 0 ]; then
        echo "$i even"
    fi
done
It’s possible to express this entire loop into a single line. Just like before,
replace all the newline with semicolons (;).
$ for i in {1..10}; do if [ $((i%2)) -eq 0 ]; then echo "$i even"; fi; done
It’s recommended to write down the loop with proper spacing first. Once the
loop is confirmed to work properly, we can safely compress it into a single
line.

Miscellaneous examples

Here’s a handful of one line for loops for reference.
$ for i in 1 2 3 4 5 ; do echo "number: $i"; done
$ for i in cpu motherboard ram psu gpu; do echo "computer part: $i"; done
The next example will be of an infinite loop.
$ for (( ; ; )); do echo "to infinity!"; done

Final thought

This guide demonstrates various effective one-line for loop examples. It’s very
easy to transform a normal for loop into one line. Hopefully, after practicing
these examples, readers will have a good idea of using bash for loop in one
line.
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
