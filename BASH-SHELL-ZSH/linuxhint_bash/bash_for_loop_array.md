





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash “For” Loop To Iterate Through an Array

2 months ago
by Karim_Buzdar
A “for” loop is a fundamental part of almost every programming language. It
helps write the code you want to be repeated in the desired number of times.
For Linux-based systems, Bash also features dedicated syntax that enables its
users to leverage loops for automating their day-to-day tasks through scripts.
Though you can use the “for” loop in a virtually infinite number of scenarios,
this guide will look at three basic scenarios that you can plug into more
extensive and complex scenarios to achieve bigger goals. We will explore three
basic scenarios that employ the for loop for iterating through an array.
To demonstrate the working of the “For” loop, I will demonstrate the Bash
scripts using Ubuntu 22.04.

Creating the Bash File

Before we explore the scenarios, let’s create our Bash file, which will contain
our Bash script. Simply navigate to your desired directory in the terminal and
create a file using the “nano” or “touch” command.
For this guide, I will create a “test.sh” file in my “Documents” directory.
This will open your Bash file using the nano text editor.
Here, you can start writing the code that you want in your script file. Let’s
start by exploring the scenarios.

Using the “for” Loop To Display the Contents of an Array

With your Bash file opened up in the editor, we can start adding code to it. To
specify that this is a Bash file, you need to indicate the following:
“#! /bin/bash”
First, we need to define an array and assign five values to it. Let’s assign
the names John, Jane, Jim, Jack, and Janis.
Now comes the fun part; we need to set up the for loop, which using the
iterator “i” will iterate through the array’s contents and perform the display
function. You can do it as such:
This line sets up the loop. With the “$” symbol, we are specifying that we are
trying to access the value of the specific index of the array. The “@” symbol
refers to the index of the array, which contains the value we are trying to
access using the “i” iterator.
In Bash scripting, the syntax dictates that we specify our function within the
“do” and “done” keywords. So, as we are trying to display the contents of the
array, we will type it out as shown below:
This will go through all the contents of the array and display them one by one.
Now, our script looks like this:
Press “Ctrl+O” to save the contents of this script file and “Ctrl+X” to exit
from the nano editor.

Running the Script

With all the code in place, you might wonder how you can execute this code to
see the output. In your terminal, type:
$bash test.sh
Here, you can see the names displayed as we have defined them.

Using the “for” Loop To Write the Contents of an Array to a Text File

This scenario works well in cases where we get the output of a specific
scenario in an array, and we have to output the contents of the array for
future reference or another calculation.
So, let’s take the code that we’ve written in the previous scenario and modify
it. Instead of printing each entry in the array one by one, we need to write it
out in a text file. Open up your script file using:
$nano test.sh
Now, as we have the array named “writers”, we will be writing them out to a
file named “writers.txt” using the >> symbols. So your code should look like
this:
Save and exit from the file to run the script.

Running the Script

Similar to the previous scenario, you can run the updated script using:
$bash test.sh
This time when you run the code, you will see that there will be no output in
the terminal. This is because the code is outputting everything to the text
file. A text file would have been created in the same directory.
Upon opening the file (you can just double-click on the file to open it), you
will see that the names have been added to the file:

Using the “for” Loop To Compare a Given String With the Elements of the Array

We will use the same Bash script for this scenario and extend it further.
The main structure of our code will remain the same, and we will need to update
the contents of the loop code. Using the same script, we will see if our
provided name matches with any of the names in the array; if it does, we will
greet them. For the other names of the array, it will just display them.
Let’s open up our file using “nano”:
$nano test.sh
Now, we’d want to update the code between the do and done keywords to the
following:
This code will check at the time of execution if any of the names in the array
match “Janis”, then display “Hi Janis”. Otherwise, just display the names. Your
code should look like this:
In order to be able to run this code, you need to save the file and exit from
the text editor.

Running the Script

When you are back in the terminal, you can use the same to execute your
modified Bash script:
$bash test.sh

Conclusion

These three are very primitive examples of using the “for” loop in your Bash
scripts. As you continue learning more about what these scripts can do, you’ll
see that this loop comes in very handy and can be utilized in very complex
codes. To better understand scripting and use it in your day-to-day operations,
you need to understand these basic components of the code and what the syntax
does.
If you run into any issues with any of these scenarios or want to learn more
about loops or Bash scripting, feel free to engage us through the comments
section, and we’ll be glad to help you out. Cheers.


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
