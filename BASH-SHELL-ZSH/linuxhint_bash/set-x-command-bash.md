





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Set -x Command in Bash

10 months ago
by Taimoor_Mohsin
Linux users pull out all the stops to make sure that their apps are free of
bugs before anyone can access them. However, it is difficult to develop a code
that is error-free especially if it contains hundreds or thousands of lines.
For troubleshooting, we can use debugging which is a continuous process that
aids in the detection of problems and collecting important information from the
code. But this is a time-consuming task that can become much more difficult if
you don’t know how to debug your code.
There is a set -x command that you can use in bash scripting to aid you in
troubleshooting and this article offers a comprehensive approach to help make
your code error-free.

How to use Set -x Command in Linux

While debugging, when things don’t go as planned, you’ll need to figure out why
the script isn’t working. So, the most popular method is to launch the subshell
with the -x option, which forces the script to execute in debug mode. Now
before learning about the set -x command we are going to execute a normal bash
script first and then see the difference between them.
Create a bash script by using the text editor of your choice:
$ nano testbash.sh
As you can see, we have created a bash file with the name of ‘testbash.sh’
using a nano text editor. After that you need to follow the general bash script
syntax as shown below:
#!/bin/bash
Var=5
while [ $var -gt 0 ]; do
  var=$[ $var-1 ]
  echo $var
  sleep 2
done
Now after writing a code, you need to save it and then execute it by typing:
$ bash testbash.sh
As you can see, this is a straightforward code and it does not explain anything
about the output so in this case, it would be difficult for a user to
troubleshoot any issue.
Let’s look at the “set -x” and try to figure out what it does. The set -
x command can also be used to monitor the outcome of a command under process.
This helps you to debug more accurately by showing you where your script is and
what each command’s result is in real-time. Now we are going to take the same
example which was discussed before and type “set -x” inside a bash script to
see its result as shown below.
Now let’s view the result of this bash script by typing:
$ bash testbash.sh
Now as you can see in the above output that it will not only execute but also
explain the output as well. So, what the above code is doing is decrementing
the value of variable ‘var’ from five to zero that we have initialized in the
above bash script and also pausing the execution for 2 seconds after each
iteration.
If you don’t want to put “set x” in the script then you can also use x while
executing the bash script in the terminal as shown below and this will also
provide you the same result that has already been discussed above:
$ bash -x testbash.sh
To debug a specific part of the code then specify “set -x” at the beginning and
“set +x” at the end as shown below:
#!/bin/bash
Var=5
while [ $var -gt 0 ]; do
  var=$[ $var-1 ]
set -x
  echo $var
  sleep 2
set +x

Conclusion

It is a difficult task for the users to develop a code that is error-free
especially if it contains hundreds or thousands of lines. So, this is where you
can use a debugging process to troubleshoot your code that not only aids in the
detection of problems but also collects important information from the code,
and for that you can use the set -x command that has been described in detail
in this article.


About the author


Taimoor Mohsin

Hi there! I'm an avid writer who loves to help others in finding solutions by
writing high-quality content about technology and gaming. In my spare time, I
enjoy reading books and watching movies.
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
