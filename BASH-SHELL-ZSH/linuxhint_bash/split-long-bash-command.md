





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Split Long Bash Command into Multiple Lines in a Script

1 year ago
by John_Otieno
Bash Scripting is something every Linux nerd should strive to master. Scripts
help us automate repetitive work and create custom tools.
However, in some instances, you may encounter a scenario where you have a long
command. In bash, long commands do not affect the functionality of the tool.
However, they are not easy to read.
In this quick tutorial, we shall discuss how to format a long command to span
multiple lines. Splitting a long command into multiple lines makes the commands
more readable and easy to edit.

How to Use Bash Backslash To Split Long Commands

To split long commands into readable commands that span multiple lines, we need
to use the backslash character (\). The backslash character instructs bash to
read the commands that follow line by line until it encounters an EOL.
The example below shows how to write a long command into multiple lines making
it easier to read.
sudo cat syslog | \

> awk ‘{print $6}’ | \

> sort -u
In the command above, we split multiple commands into individual lines. This
way, we can see what each command is doing and modify it quickly if the need
arises.
It is good to note that you can also use pipelines to split commands in the
example above. However, this is not universally applicable as the following
commands might not support input from pipes.
NOTE: Do not enclose the backslash in quotes or include whitespaces before it.
We can also apply the method above to a bash script. Using backslash, we can
span a command into multiple lines making it more readable.
Here’s is an example use case:
#!/bin/bash
zstd -z \
    --ultra \
-r --rm \
--format=zstd *
exit_code=$?
if [$exit_code -eq 0]; then
    echo “Success”
else
    echo “Fail”
fi
In the example above, we use backslash characters to span the options of the
zstd command to multiple lines.

Conclusion

In this short tutorial, we discussed the basics of the backlash characters in
bash and how we can span long commands into multiple lines. To learn more about
bash and bash scripting, consider the documentation.


About the author


John Otieno

My name is John and am a fellow geek like you. I am passionate about all things
computers from Hardware, Operating systems to Programming. My dream is to share
my knowledge with the world and help out fellow geeks. Follow my content by
subscribing to LinuxHint mailing list
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
