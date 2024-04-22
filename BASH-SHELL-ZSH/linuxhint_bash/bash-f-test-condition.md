





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash –F Test Condition

2 weeks ago
by Prateek_Jangid
The test command is integral to conditional statements in Bash scripting that
compare one element to another. Sometimes, we need to check whether the file is
regular or not. By running a Bash script, you can do this easily using the -
f flag and the test command. However, many new users don’t know about this
amazing utility of Bash scripting. In this tutorial, we will use the Bash -
f test condition to determine whether the file is regular.

Bash -F Test Condition

A regular file is a type of file which is stored in the file system. As a Linux
user, you mostly use the regular files like text files, image files, etc. Here,
we will test whether the file is regular through the Bash -f test condition.
Let’s run the Bash script and the syntax to test the regularity of the file:
test -f <filename>
Let us take some random files and test the regularity of the file. Let’s run
the following Bash script:
#!/bin/bash
test -f LinuxHint.txt
echo $?
Output:
Upon running the previous script, we see 0 in the output. Hence, our file is
regular. If your file is not regular, it gives us 1 in the output.
Let’s take one more example to clarify everything better. For instance, we can
use the Bash -f test condition with an if-else statement.
#!/bin/bash
test -f rufus-3.20.exe
If echo "rufus-3.20.exe"
then
        echo "File is regular"
else
       echo "File is not regular"
fi
Output:
After running the previous script, it tells you that your file is not regular.

Conclusion

In this tutorial, we used the Bash -f test condition to see how to check
whether a file is regular or not using a Bash script. Regular files are those
that the users easily execute. You can check if the file is regular by using
the -f flag with the test command without opening the file. The test command
contains various options to check the type of files in Linux.


About the author


Prateek Jangid

A passionate Linux user for personal and professional reasons, always exploring
what is new in the world of Linux and sharing with my readers.
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
