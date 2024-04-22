





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


What is [email protected] in a Bash Script?

1 year ago
by Aqsa_Yasin
Most of us use Bash scripts for maintenance and certain other tasks. However,
we aren’t always acquainted with the various Bash options. Whenever a user is a
novice to the Bash shell and Linux, the user tends to seek a pre-written Bash
script. This is due to some users finding the unique Bash characters such as
[email protected], $_, and $1 confusing. Beginning with the [email protected]
Bash parameter, it is being used to extend into the positional arguments. Each
parameter extends into something like a distinct word whenever expanding
happens within double-quotes. Separate parameters should be enclosed in
quotations and distinguished by a space if [email protected] is used. Remember
that [email protected] should be quoted to function properly. Nonetheless, it
behaves similarly to arguments as distinct strings.
We will be looking at several examples to elaborate on the functionality of
[email protected] in the Bash Script while using Ubuntu 20.04 system:

Example 01:

At the start, we need to log in from the Ubuntu 20.04 distribution as a sudo
user. After the successful login, we will be opening the command line to start
working. To open it, use “Ctrl+Alt+T”. As an alternative, we can also use the
Activity area to find the console terminal from the search bar. After opening
it properly, we will start working on [email protected] in Bash by creating a
new Bash file. So, we have been utilizing the “touch” query with the name of a
file as “one.sh”. Note that the Bash file contains a “.sh” extension. Hit
“Enter” after writing the following instruction in the shell to run it. You
will find the newly generated Bash file in your Home directory of Ubuntu 20.04:
$ touch one.sh
Now, the Bash file has been generated; we have to open it in an editor to add
and edit the Bash script within it. So, we will be opening it using the “GNU
Nano” editor from the terminal shell. Hence, we have used the “nano” keyword
instruction in the shell along with the name of a file as “one.sh” as per the
following image:
$ nano one.sh
You need to write the following three-liner script in your Bash file “one.sh”.
We have added the Bash extension in the file first. After that, we have used
the three echo statements in this script to use the three special characters
and output their respective results. Note that the “$#” character has been used
to output the total number of input or parameter strings of values that will be
added by the user in the shell. The “[email protected]” character is used to
show those three values or parameters on the terminal, and the “$?” character
has a special task to return 0 if the last command becomes successful. In Bash,
the “Ctrl+S” shortcut is frequently used to save the Bash file while open in
some sort of “nano” editor. So, save your one.sh file and leave it using
“Ctrl+X” to return it to the terminal:
Now, the newly created Bash script has been saved and secured in our system;
it’s high time to make it executable. You have to note that the character like
[email protected] takes parameters of values within the terminal during the
execution of a file. So, use the “bash” keyword query in your Ubuntu shell with
the name of a file “one.sh” and assigning parameter values, as stated. You can
see from the snap below that we have provided 3 string-type parameter values to
the Bash script one.sh, e.g., Aqsa, Rimsha, and Awan. The output result is
displaying the 3 line output. The first line is showing the number of total
parameters added. The second line is displaying the values of arguments passed
by the user. Last, the third line is showing 0 as its return value because the
second line command has become successful:
$ bash one.sh Arg1 Arg2 Arg3

Example 02:

To understand the [email protected] character and functionality concept more,
we need another example in our article. Hence, we will be opening the same
file, “one.sh”, with the GNU nano editor. For this, we have tried the following
instruction and clicked the “Enter” button from the keypad to continue:
$ nano one.sh
As the file is opened now, we will be adding a new and updated Bash script to
it. This time, we have been using a simple Bash script to elaborate the
function of the [email protected] character. So, you have to update your Bash
script with the one shown in the image below. We are using the for loop to take
one item at a time as the arguments passed in [email protected] by a user on
the terminal. Each item is displayed on the terminal via the echo statement.
After saving the file, we returned to the console to execute the Bash script:
Within the Bash instruction, we have passed the 5 string-type arguments along
with the name of a file “one.sh”. Upon hitting the “Enter” key, the terminal
has been displayed with each argument separately:
$ bash one.sh Arg1 Arg2 Arg3 Arg4 Arg5

Example 03:

Let’s have a closer look at another same example of [email protected] as
elaborated above. In this example, we will be using the [email protected] and
$* to compare and differentiate the working of both special characters. This
way, we will be able to possibly understand the working of [email protected]
character correctly. To open the already created file “one.sh”, write and then
run the following instruction within your console of Ubuntu 20.04.
$ nano one.sh
We have updated the above example code. All we have done is to add the same
code for “$*” within the for loop. We have saved the Bash code and exited the
file:
While execution, due to usage of $* character, it shows the first line as the
whole of parameters. All the other lines are the output of [email protected]
character:
$ bash one.sh Arg1 Arg2 Arg3 Arg4 Arg5

Example 04:

In our last example, we will be explaining the functionality of
[email protected] character through functions and loops. Therefore, to update
the Bash script, we have opened the file “one.sh” once again by the “nano”
editor command in the shell as follows:
$ nano one.sh
This time, we have been using the method foo() to print the arguments passed in
the respective methods of special characters until it gets nothing. The method
“Dollar1” is for [email protected] special character and “Dollar2” for $*
character functioning. Both methods contain the calling of method foo() with
the special character [email protected] and $* separately to pass arguments.
The Dollar1 and Dollar2 methods are called after echo statements while both
contain the same three arguments as their parametric values:
The execution of code shows the output for both Dollar1 and Dollar2 methods
separately. The “Using [email protected]” is showing the output for
[email protected], and the “Using $*” is showing the output for $* character
separately.
$ bash one.sh

Conclusion:

This guide has described how to use [email protected] in the Bash script,
declare it and how it works. We have also described the difference between
[email protected] and other dollar-related characters to make it more
understandable. We hope you enjoyed it as well while implementing it.


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
