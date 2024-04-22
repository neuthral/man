





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash –S Test Condition

2 weeks ago
by Prateek_Jangid
The test command is integral to conditional statements in Bash scripting that
compare one element to another. Sometimes, we need to check whether the file is
regular or not. You can do this by running a Bash script easily using the -
f flag and the test command. However, many new users don’t know about this
amazing utility of Bash scripting. In this tutorial, we will use the Bash -
f test condition to determine whether the file is regular.

Bash -S Test Condition

The test command with the -s flag allows you to check if files are empty or not
in a Bash. If the file is not-empty, i.e. its value is greater than 0, it
returns 0 as a true value. However, if the file is empty, it returns 1 as a
false statement. To check if the file is empty or not in a Bash, we use the
test command with the “-s” flag:
test -s <filename>
Under the Bash script, we will test whether the file named “LinuxHint” is
empty:
#!/bin/bash
test -s LinuxHint.txt
echo $?
Output:
Upon running the given script, you can see that 0 is returned in the output
which means that the file is not empty.
Similarly, we will test the second file named “file.txt” and see if the file is
empty or not:
#!/bin/bash
test -s file.txt
echo $?
Output:
You can see that it returns 1 after running the previous file, so it is empty.
Now, let’s use the -s test condition with the if statement to explain it
better:
#!/bin/bash
test -s LinuxHint.txt
If echo "LinuxHint.txt"
then
        echo "File is not empty"
else
       echo "File is empty"
fi
Output:
You can see that after running the previous Bash script, it tells you directly
whether your file is empty or not.

Conclusion

In this tutorial, we explained the -s test condition in Bash. Through the -
s flag, the test command displays whether the file is empty or not. Here, we
tested two files using the Bash -s test condition to see if the files are empty
or not. Bash is not limited to specific topics or segments. That’s why we
uploaded a ton of guides on our website to give a complete Bash tutorial. Make
sure you check them out!


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
