





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to run a shell script as a different user

2 years ago
by Karim_Buzdar
Sometimes you might find yourself required to run a shell script as a different
user other than the active user on the shell. This is quite easy and can be
done in a few simple steps So how do you go about this? Let’s find out.

Prerequisites

Before getting started, ensure that you have access to the shell of a Linux
system; any Linux distribution will do just fine. In this guide, we are running
Ubuntu 18.04.
Equally crucial is to make sure that you have a shell script with execute
permissions. We have a simple shell script called welcome.sh that requests a
user’s name and prints it out to the terminal. Here’s a sneak peek.

How to run a shell script as another user

Ordinarily, running a shell script as the currently logged-in user is quite a
breeze. Simply call the shell script as follows:
$ ./welcome.sh
But how would you run the script as another user apart from yourself? To
achieve this, simply use the syntax shown where the otheruseris the different
user you want to run the script.
$ su otheruser -s script.sh
Suppose we want to run the script as the linuxways user. The command to be
executed will be:
$ su linuxways -s welcome.sh
To confirm that the other user has executed the script, we will run the command
as shown.
$ sudo -H -u otheruser bash -c 'echo "I am $USER, with uid $UID"'
In this case, our other user is linuxways, so we shall invoke the command.
$ sudo -H -u linuxways bash -c 'echo "I am $USER, with uid $UID"'
The $USER and $UID variables print the username and the UID of the user running
the script. If in doubt or in case you want to verify this, you can view the/
etc/passwd file and search for the user’s details as follows.
$ cat /etc/passwd | grep linuxways
Here is a summary of the output from both commands. Notice how the username and
the UID from running the shell script match those in the /etc/passwdfile.

Conclusion

If you wondered how to run a shell script as another user, we are hopeful that
your search has now come to an end.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
View_all_posts

RELATED LINUX HINT POSTS


* How_to_Take_Input_From_a_User_in_Bash_Script_[Advanced_Techniques]
* 10_Cool_and_Awesome_Bash_Loop_Examples
* How_to_Handle_Command_Line_Arguments_in_Bash?
* What_are_Double_Parentheses_in_Bash
* Floating_Point_Math_in_Bash
* Bash_Continue_Built-In_Statement
* 10_Most_Important_Things_to_Know_About_Bash_Scripting

Linux Hint LLC, [email protected]
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
