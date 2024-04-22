





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Creating Bash Infinite Loop by Example Scripts

2 years ago
by Aqsa_Yasin
An infinite loop in Bash or any other programming language refers to a loop
that is continuous i.e., its terminating condition is never met or its
executing condition forever stays true. Such loops in any programming language
are very simple to write. Whether it is a “for” loop or a “while” loop, it can
be made infinite with very slight tweaking in its normal syntax.
In this article, we will be sharing with you the different ways on how you can
conveniently make the “for” and “while” loops infinitely in Bash in Linux Mint
20.

Bash Infinite Loop Example Scripts in Linux Mint 20:

There are different ways of working with infinite loops in Bash, and the
example scripts demonstrating these are described below:
Note: You can access all the Bash scripts discussed in this article in our Home
Directory named InfiniteLoop.sh.

Script # 1: “While” Loop using the “:” Command in Bash in Linux Mint 20:

In this example, we will be creating a never-ending “while” loop by pairing it
up with the “:” command in Bash in Linux Mint 20. Just copy the following
script shown in the image in a Bash file.
As shown in the Bash script above, we have created a “while” loop followed by
the “:” command. This command is an alternative to the “true” command, which
means that no matter what the situation is “while” loop will always execute.
Inside this “while” loop, we have simply printed a sample message that says,
“Keep Running”. Afterward, we have the “sleep” command, it waits for 1 second
before printing every next message on the terminal.
Once this Bash script is written, we will execute it with the command shown
below:
$ bash InfiniteLoop.sh
When the said script is executed, you will notice unending messages saying,
“Keep Running”, being displayed on your terminal, as shown in the following
image. These messages will only stop if you press Ctrl+ C. Otherwise, this loop
will just go on and on.

Script # 2: “While” Loop using the “true” Command in Bash in Linux Mint 20:

In this example, we will be creating a never-ending “while” loop by pairing it
up with the “true” command in Bash in Linux Mint 20. Just simply copy the
script shown in the image in a Bash file. As you can notice, the script is
exactly the same as the one we created in the first scenario. However, the only
difference is that this time, we have replaced the “:” command with the “true”
command. Nonetheless, it will serve the exact same purpose.
We will execute this script with the same “bash” command, and we will notice a
never-ending series of messages on our terminal, which will only terminate once
we press Ctrl+ C, as shown in the image below:

Script # 3: One Liner “While” Loop using the “:” Command in Bash in Linux Mint
20:

You might observe that Script #1 and 3 are unnecessarily lengthy. Well, both of
these scripts can be squeezed into a one-liner command. Just copy the script
shown in the image below:
The script shown in the image above is the exact replication of Script # 1.
However, instead of writing every command in a different line, we simply
separated them using semi-colons.
When we execute this script, we will get the exact same results as we got after
executing Script #1. This can be seen from the image shown below:

Script # 4: One Liner “While” Loop using the “true” Command in Bash in Linux
Mint 20:

Similarly, we can squeeze Script #2 in a one-liner command. Just copy the
script shown in the image below:
It can be observed that the script shown in the image above is the exact
replication of Script #2. Again, the only difference is that instead of writing
every command in a different line, we simply separated them using semi-colons.
When we execute this script, we will get the exact same results as we got after
executing Script #2. This can be seen from the image shown below:

Script # 5: For Loop without any Parameters in Bash in Linux Mint 20:

This example is different from Scripts #1 to 4 because instead of using the
“while” loop, we are going to create an infinite “for” loop. Just copy the
script shown in the image below:
The task that we are going to perform inside the “for” loop is the same as we
did with the scripts discussed above. However, instead of using the “while”
loop, we have used the “for” loop without any conditions or parameters. It is
always executed since its condition is considered “true” by default.
We will execute this script with the same “bash” command, and we will notice a
never-ending series of messages on our terminal, which will only terminate once
we press Ctrl+ C, as shown in the image below:

Conclusion:

In this article, we taught you five different ways of implementing infinite
loops in Bash. These loops will keep on running forever since no terminating
condition is specified, or even if there is, it is never going to meet.
Therefore, if you want to put an end to this unending loop, you will either
have to make use of a “break” statement with a specific condition within this
loop or during the execution of such script, you have to simply press Ctrl+ C
as we have discussed in all of our examples.


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
