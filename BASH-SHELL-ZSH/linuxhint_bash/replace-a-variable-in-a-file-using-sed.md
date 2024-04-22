





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How Do You Replace a Variable in a File Using sed?

1 year ago
by Shehroz_Azam




Steam editor, shortened as sed, is a command used to find and replace any text
in a file using various techniques and syntaxes. In this post, we will grasp
the concepts of sed and learn how you can replace a variable or its value in a
file using sed.

The Syntax for Replacing String

For replacing a variable value using sed, we first need to understand how sed
works and how we can replace a simple string in any file using sed.
To replace any string, the syntax is pretty simple and given below:
$ sed -i 's/old-string/new-string/g' file_name
In this syntax, you just need to provide the string you want to replace at the
old string and then the new string in the inverted commas. After that, provide
the file in which you want to find and replace the mentioned string.

Example:

Suppose we have a text file “file.txt” in which we have some random text like
“Welcome to Linuxhint’s channel”, and in this file, we want to replace the word
channel to the website using the sed command.
$ cat file.txt
The command for altering the channel to the website would go like this:
$ sed -i 's/channel/website/g' file.txt
After running the command, we take a look back at the file:
$ cat file.txt
The string was replaced using the sed command. So, this is how you can find and
replace any string in any file of the Linux operating system using the sed
command.
Now, let’s learn to replace a variable value in a file.

Replace a Variable

The syntax for finding and replacing the value of a variable in a file using
sed is the same as finding and replacing a string in a file. The only tricky
part is writing a regular expression to find something in a file to replace
that part. So, for changing a variable’s value, the syntax will go like this:
$ sed -i 's/var=.*/var=new_value/' file_name
Let’s look at an example to see the true implementation and understand it with
more clarity.

Example:

Suppose we have a Python code file in which we have a couple of variables.
Those variables have some values assigned to them.
$ cat code.py
Now, to replace any variable, we can search for it by its name and provide a
new value to it using the sed command given below:
$ sed -i 's/num1 =.*/num1 =200/' code.py
After executing the above sed command, we display the file content again:
$ cat code.py
You can see that the value of the “num1” variable was replaced as per our
requirement.
Using this simple trick, you can replace any variable or its value in any file
using sed.

Conclusion

This post provides a simple and easy way to find and replace a variable in any
file using sed. We have learned to replace a string in a file and replace a
variable’s value using sed.


About the author


Shehroz Azam

A Javascript Developer & Linux enthusiast with 4 years of industrial experience
and proven know-how to combine creative and usability viewpoints resulting in
world-class web applications. I have experience working with Vue, React &
Node.js & currently working on article writing and video creation.
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
