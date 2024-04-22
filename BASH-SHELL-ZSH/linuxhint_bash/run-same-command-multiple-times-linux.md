





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Run the Same Command Multiple Times in Linux

2 years ago
by Aqsa_Yasin
When programming, you may encounter a situation in which you need to perform
the same task multiple times. A simple solution is to manually repeat the
process as many times as it is needed; however, it is not productive to do so.
That is why the concept of loops was introduced to programming. The basic goal
of a loop is to repeat a task several times, depending upon the value provided
for the iterator and the termination condition of the loop. Loops allow
programmers to avoid the hassle of repeating processes manually.
Suppose that there is a command that you wish to run multiple times. There are
several important reasons that you might need to run a command repeatedly, so
you want to be sure that a certain command produces the correct output every
time it is executed. The more you run a command manually, the more certainty
you will gain each time you run the command.
But how do you do this programmatically? Well, there are several methods that
can be used to run the same command multiple times, as well as for verifying
the output of the repeated command. This article shows you how to create a
repeatable command using Linux Mint 20 as the host operating system.

Methods for Reiterating Commands in Linux Mint 20

The following sections show you two methods that you can use to run the same
command multiple times using a Bash script in Linux Mint 20.

Method 1: Reiterating a Command Using the “for” Loop in Bash

The first method of running the same command multiple times using a Bash script
in Linux Mint 20 is implemented using the “for” loop. The sample script is
shown in the following image. You can copy this script into any Bash file of
your choice.
In this script, we have created a simple “for” loop that iterates through a
list containing items from 1 to 5, meaning that the “for” loop will have a
total of five iterations. In these five iterations, our desired command will be
executed with each iteration, or five times.
Here, we specified for the “date” command to run “5” times. This command
displays the current system date and time in the terminal. You can use any
other command of your choice in place of the “date” command.
We also wanted our output to be displayed after every “1” second. To serve this
purpose, we used the “sleep” command with a sleep interval of “1,” though you
may increase the sleep interval according to your preferences. You can even
increase or decrease the number of iterations of the “for” loop, depending upon
the number of times you want to execute the command.
Execute this Bash script with the following command:
$ bash Multiple.sh
The result of the above Bash script is shown in the following image. The output
contains the current system date and time at “5” different intervals, which
means that our “date” command has been successfully executed for the specified
number of iterations.

Method 2: Reiterating a Command Using the “while” Loop in Bash

The second method of reiterating a command multiple times using a Bash script
in Linux Mint 20 is implemented using the “while” loop. The sample script is
shown in the following image. You can copy this script into any Bash file of
your choice.
In this script, the variable “i” is initialized with the value “0.” This
variable will act as the iterator for the “while” loop. Then, the iterating
condition of the “while” loop is that the value of the variable “i” is less
than “5.” Within this loop, we have a “date” command that will serve the same
purpose as the command used in Method 1.
This command is followed by the “sleep” command. This command prints the output
after some specified interval, which is “1” second, in this case. Finally, we
will increment the value of the iterator “i” using the “+1” incrementing
notation.
The result of our Bash script is depicted in the following image. This output
contains the current system date and time at five different intervals, meaning
that the “date” command has been executed successfully for the specified number
of iterations. This time, we have achieved this goal by implementing the
“while” loop instead of the “for” loop.

Conclusion

Today, you learned that instead of manually running a command multiple times,
you can write a Bash script to simplify this task. Using the “for” or “while”
loops in a Bash script, you can easily achieve the functionality of running a
command multiple times. This article showed you how to reiterate commands using
both methods while running the “date” command repetitively. We also used the
“sleep” command in both of our example scripts so that it was easier to
visualize the effect of the repetitive “date” command since the value of
“seconds” will change every time this command is executed.
In the same manner, you can run any command of your choice multiple times using
either of the Bash scripts that we shared with you today while operating in
Linux Mint 20. I hope this guide will help you to run the same command multiple
times in Linux.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
