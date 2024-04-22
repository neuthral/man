





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash if –e and –s and other File Test Operators

2 years ago
by Aqsa_Yasin
While working with files in any operating system, it is mandatory for the user
to test those files for certain aspects such as their ownership, access rights,
content, existence, etc. These aspects can be figured out while coupling the
“if” statement with various file test operators in Bash. The “if –e” and “if
–s” are such operators in Bash, used for testing the existence of a file. The
difference between the two is that the former only tests the existence of a
file, whereas the latter also checks if there are any contents in that file or
not. Today, we will try to understand the usage of these two operators, along
with a few other file test operators in Bash.
Note: To demonstrate the usage of file test operators in Bash, we have used
Linux Mint 20.

Examples of Using File Test Operators in Bash

There are different ways in which the file test operators “if –e” and “if –s”
can be used. To explain their usage, we will share some examples with you.

Example of Using “if –e” Operator

For using the “if –e” operator in Bash, you need to follow these steps:
First, we have created an empty text file named Test.txt in our Home directory.
Then we created a bash file named FileTestOperators.sh in the same directory.
After creating this file, we typed the script shown in the following image in
our file. In this bash script, declared a variable named “file” and assigned it
our text file named Test.txt as its value. Then we have an “if –e” statement,
which produces a “true” output if any specified file exists.
For testing our script, we will run it using the command stated below:
$ bash FileTestOperators.sh
In our case, since the text file existed, that is why the output of our script
will be true, as shown in the following image:

Example of Using “if –s” Operator

For using the “if –s” operator in Bash, you should perform the steps listed
below:
For this example, our bash script is the same as we used above. We have just
changed the “if –e” statement to “if –s”. Also, we have used the very same
empty text file Test.txt.
Now, when we run this script, the output will be false because the “if –s”
operator returns true if a file exists and also if it is not empty. Since in
our case, although the file existed, still it was empty that is why our output
turned out to be false as shown in the following image:
For making this flag to be true, we will write some dummy text in our text
file, as shown below:
Then we run our bash script again, and this time the output will be true, as
shown in the following image because the text file has some text in it now.

Examples of Using Other File Test Operators

Other than the “if –e” and “if –s” operators, there are other file test
operators too. Below we will share with you some of the most important file
test operators other than the ones that are discussed above.

Example of Using “if –d” Operator

For using the “if –d” operator in Bash, you should perform the steps listed
below:
For this example, our bash script is the same as we used above. We have just
changed the “if –s” statement to “if –d”. Also, we have used the very same text
file Test.txt.
The “if –d” operator returns true if your file is a directory, otherwise, it
will be false. Since our text file was not a directory, therefore, the output
will be false, as shown in the following image:

Example of Using “if –h” Operator

For using the “if –h” operator in Bash, you need to follow these steps:
For this example, our bash script is the same as we used above. We have just
changed the “if –d” statement to “if –h”. However, we have used a different
file for testing this time, which was in fact, a symbolic link named
NewBash.sh.
The “if –h” operator returns true if your file is a symbolic link, otherwise,
it will be false. Since our test file was a symbolic link, therefore, the
output will be true, as shown in the following image:

Example of Using “if –r” Operator

For using the “if –r” operator in Bash, you need to follow these steps:
For this example, our bash script is the same as we used above. We have just
changed the “if –h” statement to “if –r”. Also, we have used the very same text
file Test.txt.
The output of the “if –r” operator will be true if the current user can read
the file, otherwise, it will be false. Since our text file was readable by us,
therefore, the output will be true, as shown in the following image:
In the same manner, you can use the “if –w” and “if –x” operators to check
whether a file is writable and executable by the current owner, respectively.

Example of Using “if –O” Operator

For using the “if –O” operator in Bash, you should perform the steps listed
below:
For this example, our bash script is the same as we used above. We have just
changed the “if –r” statement to “if –O”. Also, we have used the very same text
file Test.txt.
The output of the “if –O” operator will be true if the current user owns the
file, otherwise, it will be false. Since our text file was owned by us,
therefore, the output will be true as shown in the following image:

Conclusion

This article briefed the reader about the usage of the different file test
operators in Bash using the Linux operating system. By making use of these file
test operators, it gets very convenient for the user to work with files without
any potential difficulties. There are some other file test operators too, which
can be used for different purposes However, the ones that are discussed in this
article are most commonly used.


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
