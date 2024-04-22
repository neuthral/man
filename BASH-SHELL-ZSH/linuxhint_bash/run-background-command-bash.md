





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash run command in the background

2 years ago
by Aqsa_Yasin
While using the command line in Linux, users usually have to wait for one
command to run before proceeding to the next one. The commands usually seem to
run smoothly and do not take a lot of time in their execution. The cd is the
common example, for which users simply run the commands and quickly shift from
one directory to another to perform relevant and required functions. The
commands run and execute in a very short time, like in a few seconds and
provide useful information needed to the user.
At times, the processes might take a bit longer to run and complete its
execution. This is when the one by one execution might become a bit challenging
for the user. This can involve the pushing or monitoring of output to its logs.
Such processes might take a longer duration unexpectedly as code compilation is
not always smooth. This way, in the meantime, when the compilation is going on,
users might not be able to access the system unless the compilation is
finished. During compilation, the terminal cannot be used until it’s done. To
continue the regular work while you are processing a command, users need to
know how to run commands in the background in Linux. Let’s go through this
tutorial to know more about it.
To run command background in Linux Mint 20, you need to open up the
Terminalfrom Menuon the bottom left of the screen, then select the Terminal
option from the list of available applications.
Once the terminal is opened, you can now run commands in the background or send
them to the background as per user requirements to work smoothly.
Note: To enter the bash, the user needs to have a sudo account with rights.

Using the “&” to run a command in the background:

Users can execute the commands to run in the background if they append the “&”
character. This will imply that while the commands are running, users still can
take care of the relevant work alongside it, without any interruption. As an
example, let’s check out the command to add numbers inside a text file.
Here, the output would be like an affixed image:
The data inside the square bracket is the job number of the background process,
and the next set of digits is the process ID.
Note: As soon as the above process is to run, the command prompt reappears,
which allows users to resume their work by running the commands in the
background as per user requirements. If we had issued the command without
ending it up with the “&” character, then there would not have been any user
interaction, and it would have been blocked completely unless the action is
completed.

To send a running command in the background:

If users have already started a certain command and while they were using their
system, their command-line blocks up, then they can suspend the execution of
their currently foregrounded process by using “ctrl+z” for windows and
“command+z” for mac systems. They will put their processes in a temporary
stopping phase, and then it will help them use the job ID, which we already saw
earlier and were written in a square bracket.
Note: This time, remove the “&” character that was appended previously before
applying the “ctrl+z” keys.
The foreground process is now suspended, and knowing the ID of the job, we are
now able to set and adjust the background. We can do this by simply typing this
on our command line:
$ bg 1
Here as already mentioned above,1 is our Job ID. Now, it is time we check out
the background with the status of jobs running. Type jobs -l in your command
line, then press enter. The output shows our process running in the background,
as shown in the screenshot below:
$ jobs –l
The process is now back on and running in the background.

To bring a background process to the foreground:

Users can also easily bring the background process to the foreground by simply
using fg [job number] next to it.
$ fg jobnumber
Note: you can use any desired job number

Now, again, users can use ctrl+z keys to suspend the process once again. This
is an easy way to bring the process at first in the foreground and then stop
it.

To kill a background job:

Users can not only run and move different processes using the background
commands, but they can also kill a specific job or process using % before the
ID. The example below shows the same command. Simply type kill %1 because in
our case, we used 1.
$ kill % jobnumber
In your case, you can try by replacing the bolded number “1” with your specific
job number.
Note: You can also recheck the killing process by using “jobs -l”. It will
display the list of all terminated jobs.

Conclusion:

When users run a command in the background, they now don’t need to wait until
it finishes before executing the next one in line. The options discussed above
cover all related information to better facilitate the users in running and
moving the process, jobs and commands anywhere based on their requirements by
providing them enough flexibility. This tutorial will be helpful to all users
who plan to work on Linux OS and desire to work in parallel with multiple
processes running on their systems. This way, they can either send the running
commands to the background or can use the “&” operator by appending it at the
end of their commands and then move it in the background. The pointers
mentioned here with examples will also assist you in bringing processes to the
foreground. Not only this, but you can also kill a background job.


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
