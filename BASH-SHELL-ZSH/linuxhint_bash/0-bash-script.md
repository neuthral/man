





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


What is $0 in a Bash Script?

1 year ago
by Aqsa_Yasin
In this article, we want to extend the discussion on the special variables in
Bash a little further. In this regard, today, we would like to focus on using
the $0 special variable in a Bash script in Ubuntu 20.04. Let us figure out how
this special variable functions when it is placed inside a Bash script.
Moreover, as a bonus, we will also share the usage of this special variable
within the terminal.

Usage of $0 in a Bash Script in Ubuntu 20.04:

$0 belongs to a different category of special variables in Bash, also known as
positional parameters. These parameters range from $0 to $9, and as their name
implies, these variables correspond to different values within a Bash script
depending on their positions. As far as the $0 special variable alone is
concerned, this special variable serves two different purposes i.e. it can
either print the name of a Bash script or refer to the name of your current
shell.
Now you might be wondering how this variable can correspond to two different
values at the same time. Well, the answer to this question is very simple. This
variable does not correspond to two values simultaneously; rather, depending on
where this variable is used, it can refer to either of those two values. If the
$0 special variable is used within a Bash script, it can be used to print its
name and if it is used directly within the terminal, it can be used to display
the name of the current shell.
However, in this article, since our main concern is with using the $0 special
variable within a Bash script in Ubuntu 20.04, therefore, you will have to go
through the following section to check out some relevant examples.

Examples of Using $0 in a Bash Script in Ubuntu 20.04:

In the following examples, we will be using the $0 special variable in a Bash
script at three different places. Our goal is to see if its output differs by
changing its placement or not. To find out, you will have to explore the three
examples discussed below:

Example # 1: Using $0 at the beginning of a Bash Script in Ubuntu 20.04:

For the first example, we have created a very simple Bash script that can be
seen in the following image:
In this Bash script, we have just written an “echo” command to print the $0
special variable value on the terminal below the Shebang (which is mandatory to
identify a Bash script). Since we have used the $0 special variable within a
Bash script, it will certainly refer to the name of our Bash script. To verify
this, we will execute our Bash script with the following command:
$ bash Temp.sh
Here, Temp.sh was the name of the Bash script file that we created. You will
have to replace it with the name of your particular Bash file.
When this particular Bash script is executed, you will be able to see the name
of your Bash script file printed on your Ubuntu 20.04 terminal as shown in the
image below:

Example # 2: Using $0 in the middle of a Bash Script in Ubuntu 20.04:

For this example, we have expanded the same Bash script a little further than
we have used in our first example. The aim of this modified Bash script was to
use the $0 special variable somewhere in the middle of the script to figure out
if its functionality differs from that of the first example or not. This
modified Bash script can be seen from the following image:
In this Bash script, we have declared three variables, “a, b, and c” and
assigned them the values “10, 20, and 30,” respectively. After that, we have
used the “echo” command to print the values of the variables “a” and “b” on the
terminal. Then, another “echo” command will attempt to print the value of the
$0 special variable. Finally, there is yet another “echo” command that will
print the variable “c” value on the terminal.
This Bash script file can also be executed similarly as we did in the first
example. Upon execution, the output rendered by this modified Bash script is
shown in the image below:
From this output, you can see that this Bash script has first printed the
values of the variables “a” and “b”, then it has printed the value of the $0
special variable, i.e., the name of the Bash script followed by the value of
the variable “c”. It means that even when the $0 special symbol was used in the
middle of the Bash script, it still contained the same value as it did in the
first example.

Example # 3: Using $0 at the end of a Bash Script in Ubuntu 20.04:

This example is yet another modified version of the first Bash script. In this
Bash script, we intended to use the $0 special variable at the end of the Bash
script to see if its working differs from that of the first example or not.
This modified Bash script file is shown in the following image:
In this Bash script, we used the same three variables we had in the second
example. Then we have used an “echo” command to print the values of all of
these variables, followed by another “echo” command that will attempt to print
the value of the $0 special variable, i.e., the name of our Bash script file.
This Bash script file can also be executed similarly as we did in the first
example. Upon execution, the output rendered by this modified Bash script is
shown in the image below:
This output shows that this Bash script has first printed the values of the
three variables followed by the value of the $0 special variable, i.e., the
name of the Bash script. It means that even when we used the $0 special
variable at the end of a Bash script, it still held the name of the Bash script
file in it.

Usage of $0 in the Terminal in Ubuntu 20.04:

This is just an additional usage of the special variable under discussion. The
$0 special variable can be used in the terminal to print the name of your
current shell simply by executing the following statement:
$ echo $0
Since our current shell name was Bash, it is also evident from the output of
the statement mentioned above.

Conclusion:

From this article, we can conclude that the special variable $0 can serve two
different purposes i.e. for printing the name of a Bash script and printing the
name of the current shell. Moreover, we also found out that regardless of the
placement of the $0 special variable within a Bash script, it will always hold
the name of that Bash script as its value.


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
