





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash script to While Loop while Reading Stdin

2 years ago
by Aqsa_Yasin
The concept “stream” in a computer applies to something that might move data.
Any instruction you are executing in the terminal would be at any position of
the flow. These positions can be an origin or an outflow. Let’s get a quick
overview of the specific Stdin stream. In Linux, stdin refers to the default or
standard input. The input it requires must be a text. To acquire data or
information from you, it’s the file handler that your procedure readout. Almost
all flows are viewed in Linux as if they are directories. We may read/write
information from all of these streams, exactly as you can read/write a
document. By using a special file descriptor number related to it provides a
great approach to access a document. There have been special values allocated
to every one of these throughout the situation of such streams. Stdin has a
value of 1.

Stdin: 1

Let’s begin by understanding through practice about Stdin Stream using while
loops. At very first, we will be having a basic example of the stdin as read.
Execute the instruction below. The instruction would demand keyboard input. In
this, through stdin, the reading tool gets the text.
$ read

Example 01:

Create a new file, “input.sh” and add the appended script to it. We have been
using the while loop to read the text by a user from the terminal and print it.
The script is named with a “/dev/stdin” as the very first $1 parameter, in
which the corresponding approach reads the regular input from the console. Save
this file and close it.
Open the terminal, and run the newly updated file “input.sh” as:
$ bash input.sh
When you execute the file using the bash command, you will be jumped to the
next line to write something. As you can see below, the user has written a one-
line text and press Enter.
The text written by a user will be read out first and printed out on the next
line as below.
You can even provide one space between your text input as below.

Example 02:

Now we will read the text from the file. Update the same file “input.sh” by
providing the filename “script.sh” as the very first $1 parameter. The
corresponding approach reads from this document.
We have the following text information in the file “script.sh” as below. Let’s
check how it works.
Execute the file “input.sh” using the bash command. You will see that the read
stream reads out from the provided file “script.sh” and print it out in the
terminal as below.
$ bash input.sh

Example 03:

Let’s have an example to read each directory one by one using stdin. You have
to consider the parameter -u with the read. In this, “-u 1” implies “read from
stdin.” In this code, “line” represents the filename, and the increment “i++”
is used to jump over to the next directory or file. It will also count the file
number that has been read as well. Let’s run this code to check what happens
next.
Execute the bash file “input.sh”. It will prompt you to enter some text to jump
over to the next file. Here “comm” represents the name of the first file.
$ bash input.sh
While continuing this, you can see we have a list of files that we have gone
through.

Example 04:

In this example, we have two related files to read from. Assign the required
privileges to both files using the “Chmod” command as below.
chmod u+x filename
Write the below code in the file “input.sh”. Until the “while” loop is getting
lines, it will print those lines. While the “line” refers to another file
“script.sh”.
We have the below code in the file “script.sh”. While the loop is running, it
is printing the line number.
Execute both files using “”./” at the start of the filename and separating
using “”|” in the shell. You will see that it is printing the line numbers
while printing the text from the files as well. It’s a very simple method to
correlate two files or their contents.
$ ./script.sh | ./input.sh

Example 05:

Let’s end this topic by having this simple and efficient example. We have a
file “script.sh” with the below contents or names of persons. We will be
reading these names one by one from another file.
Update the file “input.sh: with the below script. In this script, we have a
while loop to elaborate “stdin” working. We have been using read “read –r”
while reading from another file as other than standard input. On the other
hand, using “-u” as bash-specific, the standard output from the user in the
terminal. Here, the “name” is the text or content of the file “script.sh”. The
option “-p” is used to “read”. The read statement will read the “name” from
another file and ask if you want to delete it or not. The keyword “ip” is used
for user response to affirm the action of deletion. Whatever the user response
is, it will print it out. In the “if” statement, it will check if the standard
input from the user is same as “y”, then it will print out some message as
mentioning that it has been deleting the “name”. This process will be
reiterated until the last content of the file “script.sh”.
Let’s have a look at the output of the above code. Execute the file using the
bash command. The system will ask you if you want to delete this “name” or not.
Enter “y” and tap “Enter”.
$ bash input.sh
Here on pressing “y”, it will print “y” and show a message that it has been
deleting the particular “name”. After that, it will switch to another “name”.
It will ask you to delete the names until all the names or contents of file
“script.sh” have been lopped over as below.

Conclusion:

We have magnificently gone through all the simple examples of standard input
while using the “while” loop in the bash script.


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
