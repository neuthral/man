





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How do I Pass Argument in a Bash Script?

2 years ago
by Aqsa_Yasin
Most of the Linux Mint 20 Users find themselves stuck when passing an argument
in a bash script. You can pass the arguments to any bash script when it is
executed. There are several simple and useful ways to pass arguments in a bash
script. In this article guide, we will let you know about some very easy ways
to pass and use arguments in your bash scripts.

Passing Arguments Using Default Variables:

Create a new file with any name using the “touch” command, e.g., “file.sh”.
$ touch filename
Open this newly created file and add some bash script to it. I have added some
default variables, e.g. “$1”, “$2”, and “$3” consequently. Whatever arguments
will be passed through the terminal will be stored in the stated variables.
You have to run this file using the “./” command followed by some arguments. As
you can see in the picture that when I passed the arguments, an error occurs:
Permission denied. This is because this file doesn’t have execution rights.
$ ./filename argument1 argument2 argument
So to grant the execution rights to this file, use the sudo “chmod” command to
do so.
$ sudo chmod +x filename
Now, again run the file using the same above command. This time I have provided
different arguments. You will see the newly passed arguments are stored in the
default variables.

Passing Shell Script Name as Argument:

Now, using the same old file “file.sh” with a little change in its default
variables. You have to add the variable “$0” in the script as shown.
On running the same “./” shell script command, the name of your shell script,
e.g. “./filename” will be stored in the “$0” variable as an argument.

Passing Arguments as an Array to Variable:

Starting with the same file “file.sh”, you have to add some extra lines in the
old script. Declare a variable named “array”. Add a default variable “
[email protected]” which will store the arguments entered by the user as an
array. These arguments will be parsed to variable “array”. The last line will
display all the arguments of the variable “array” sorted by the index number.
Execute the “./” shell script. You will see that it will display the arguments
or values stored as an array in “[email protected]” parsed to variable “array”
but not the shell script name in the second “echo” statement. You will have the
following output.
$ ./filename argument1 argument2 argument
Use the same file with the same script. Just remove the “${array[3]}” from the
last line as clear in the picture.
After executing the “./” command, you will see a similar output as you got in
the above example with no change.
You can also get the same result by replacing the last line of the bash script
with one single word. You just have to add “[email protected]” in the echo
statement, and it will display the arguments present in this variable array.
So running the “./” command again, you will get the same results.

Check Total Number of Arguments Passed:

On the contrary, if you want to know the total number of arguments passed by
the user, you can also do that. For this purpose, you just have to replace “
[email protected]” with “$#” in “echo”.
Again executing the “./” command, You are now going to see the entire figure of
arguments passed to the script. In our case, 3 arguments are passed as value.

Create Line by Line Output of Arguments:

Create a new file “test.sh” in the home directory. Add the bash script as
shown.
Now run the same old command with different arguments. Firstly, you will see
the error: Permission denied.
You have to execute the “chmod” command to grant this file sudo privileges.
After that, run the “./” shell script command again. And you will get the line
by line sorted output of arguments.

Limit the Variable via Argument Index Number:

If you want to limit the variable using its index number, you can do it very
easily. Add curly brackets after the “$” sign and add the argument index number
which you want to display before other arguments.
If the arguments provided by the users are less than the index number provided
in the limit variable, then you will get an empty argument value. As an
instance, I have provided 4 arguments, but I have given the “05” argument value
to be displayed. In this situation, the variable will be displayed empty
because the fifth argument has not been passed.
But when you pass the equal or more number of arguments in the command, you
will get the value displayed in the result as shown.

Checking Specific Value Arguments:

Make a new file with the name “Check.sh” in your home directory. Add the same
bash script as shown in the below image. In this script, we have a variable
“var” to store the argument value passed by the user. Then we have an “if”
statement, which will check for the argument value to be matched or not. If the
argument value is matched with the value provided in the parenthesis, then the
first “echo” statement will be executed. If the value does not match, the
second “echo” statement will be executed.
When we run the shell script command, it will raise an error. By using the
“chmod” command, we can correct this error.
After that, execute the shell script for the particular file with some argument
value. In our case, we have provided “Aqsa” as an argument value, which is the
same as the value displayed in the parenthesis. So the bash script will execute
the first “echo” statement as shown.
On the other hand, if you provide the different argument values in the shell
script, it will display the other “echo” statement. Here, I have added “Rimsha”
as an argument value, which is different from the value provided in the if
statement. So bash script will execute the second “echo” statement.

Conclusion:

I hope this guide has helped you sufficiently to have a strong grip on how to
pass arguments to default variables, pass argument value as an array to a
variable, get the total number of arguments passed, line by line output of
arguments, limit the argument output using index number, checking specific
value argument and many more.


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
