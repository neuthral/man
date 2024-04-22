





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How do I Sleep in a Bash Script?

1 year ago
by Aqsa_Yasin
When you create your Bash scripts, their functionality is such that you have to
wait for some function within it to complete its processing before proceeding
further. The wait within a Bash script is introduced with the “sleep” command.
The sleep command in Bash allows you to wait for as long as you want before
doing any further processing. This functionality finds a special use case while
dealing with clients and servers in Linux.
Multiple clients can connect to a single server depending upon its request
handling capacity in a client-server model. A client always initiates a
connection request, whereas a server listens to this request. However, at
times, a server might be busy processing other requests. Therefore, there
should be a time duration defined for the client for which that client should
wait before canceling the connection initiation request. This time duration can
be defined while making use of the sleep command.
This was just a simple use case of the sleep command with the client-server
model; however, this command can also serve other different purposes within
this model. Our motive is to learn how we can sleep in a Bash script in Ubuntu
20.04. For doing that, we have designed this tutorial so that you will get the
maximum benefit out of it once you follow the examples shared in it.

How do I Sleep in a Bash Script in Ubuntu 20.04?

For sleeping within a Bash script, the command that is used is known as
“sleep”. For your ease, the syntax of this command is stated below:
$ sleep duration
Here, duration refers to the number of seconds, minutes, hours, or days for
which you want your program to sleep. The default sleep duration is in seconds,
which means that if you execute the command “sleep 2”, your program will simply
sleep for 2 seconds. However, if you want your program to sleep for minutes,
hours, or days, then you will have to use the “m”, “h”, or “d” characters after
the sleep duration for specifying the minutes, hours, or days respectively.
Now, to understand the working of the sleep command in a better way, you will
have to read through the following examples that we have especially designed
for you to get your hands on the usage of the sleep command in Bash in Ubuntu
20.04.

Example # 1: Simple Usage of the Sleep Command in Bash:

The first example is the simplest one of all in which we just intended to teach
you how you can create a Bash script that uses the sleep command. The sample
Bash script is shown below:
We have just used the sleep command in this script followed by the sleep
duration, which in our case was 2. It means that our script will sleep for two
seconds before doing any further processing. After sleeping for two seconds, we
wanted our script to print a random message on the terminal with the help of
the “echo” command.
Now, to execute this script through the Ubuntu 20.04 terminal, we will run the
subsequent command in it:
$ bash Sleep.sh
Sleep.sh is the file’s name in which our Bash script for this specific example
is written.
Once this command was executed, our terminal waited for 2 seconds before
displaying the message stated in our script on the terminal, as shown in the
image below:
You will verify it once you create a similar Bash script and execute it on your
Ubuntu 20.04 system.

Example # 2: Using the Sleep Command to Compare Two Different Times in Bash:

Now we want to take you a little further with the usage of the sleep command in
Bash in Ubuntu 20.04. For that, you should first take a look at the following
Bash script that we have designed:
In this Bash script, we first used the date command to print the current system
time in the “hours, minutes, seconds” format. After that, we have used the
sleep command for putting the script to sleep for 2 seconds. Then again, we
have used the date command to print the current system time. Basically, we
wanted to compare the two different times, or in other words, we wanted to
check whether our sleep command has actually put our script to sleep for 2
seconds or not.
This Bash script can be executed with the same command that we used in our
first example. We have displayed the output of this script in the image shown
below:
In this output, you can notice the difference between the two times. The first
time was 18:26:06, after which our Bash script slept for 2 seconds. The second
time was 18:26:08. Both times differ exactly by 2 seconds which implies that
our sleep command has been executed correctly.

Example # 3: Using the Sleep Command within a For Loop in Bash:

Finally, we will now design an example Bash script that will use the sleep
command within the “for loop”. You can first take a look at the following Bash
script that we have designed for this purpose:
This Bash script starts with declaring an array named “numbers,” and three
values, i.e., 1, 2, and 3 were assigned to this array, meaning that the
declared array has three elements. Then, we have a variable to which we have
assigned the length of this array so that our “for loop” can easily iterate
through this array. Then, we have our “for loop,” which will have a total of
three iterations since it iterates through the length of the “numbers” array,
which is 3. Within this “for loop,” we wanted to print the elements of our
“numbers” array one by one with 1 -the second pause before printing the next
value. That is why we have first used the “echo” command to print the array
index value followed by a random message. Then our script will sleep for one
second, after which the next value will be printed.
This script will be executed in the same manner as we executed our first two
example scripts. The output of this Bash script is shown in the image below:
You can easily visualize from the output shown above that our Bash script slept
exactly for a second after printing each index value of our “numbers” array.

Conclusion:

This article started with a brief description of the sleep command in Bash in
Ubuntu 20.04 system, followed by its general syntax. Then, we shared three
different examples that use this command within a Bash script with you. These
examples started with a very easy to complexity level and rose to a relatively
difficult complexity level. However, our main goal was to show you how to use
the sleep command in a Bash script on Ubuntu 20.04 system. Hopefully, by going
through this tutorial, you will be able to use the sleep command within your
Bash scripts very efficiently.


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
