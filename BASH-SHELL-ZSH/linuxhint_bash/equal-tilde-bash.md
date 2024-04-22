





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


What Does =~ Mean In Bash?

1 year ago
by Aqsa_Yasin
A Bash program is a simple text document with a series of instructions in it.
These statements combine instructions we’d put on the command prompt manually
(including such ls or cp). Likewise, whatever you can accomplish with a script
could also be done with a command prompt. A regular expression matching sign,
the =~ operator, is used to identify regular expressions. Perl has a similar
operator for regular expression corresponding, which stimulated this operator.
Let’s have some examples to see the working of =~ operator in Ubuntu 20.04.

Example 01:

Firstly, we need to get logged in from our system. After that, On the desktop,
press “Ctrl+Alt+T” to open the console terminal in Ubuntu 20.04. As an
alternative way, we can also use the menu “Activity” from the top left corner
of the desktop. Tap on “Activity,” and the search bar will be popped up. Click
on it and write “terminal”. The terminal application will be poped up. Hit on
it to open it. Now the terminal has been opened by using one of both mentioned
methods as shown. Let’s see how the =~ operator works in it. First of all, to
write a bash script, we need some bash files to be created. Therefore, we have
created a file “new.sh” with the console’s typical “touch” query as beneath.
$ touch new.sh
You can find the created bash file within the home folder of Ubuntu 20.04. As
the file is created, we will be adding some bash script to it. For that, we
have to open this file within the terminal using some editor. So, we have
utilized the GNU Nano editor to do so, as shown below.
$ nano new.sh
Now the file is opened in the GNU editor; we have to put the below-shown bash
code in it. You can see we have added the bash extension within it. After that,
we have initialized a variable “var” with some string type value containing
numbers and alphabets. We have put the “if” statement to check the condition if
it meets or not. This condition will check whether the variable “var” contains
the mentioned characters, symbols, and alphabets on the right side within the
condition clause. If the pattern contains some alphabets and symbols, it will
display “Matched” within the terminal by echo statement; otherwise, print “Not
matched”.
Save the bash script by Ctrl+S and exit via “[email protected] Let’s execute
the bash file “new.sh” via bash query as below. The output shows the output as
“Matched”, as the variable pattern matches with the defined set of characters
and alphabets.
$ bash new.sh

Example 02:

Let’s have a simpler example this time. Open the same “new.sh” file to update
its content. So, use the below instruction in the shell again.
$ nano new.sh
After opening it in the GNU editor, let’s update it with the below script of
bash. Bash has had a constructed pattern matching comparison operator,
symbolized by =~ from version 3 (approximately 2004). Many scripting techniques
that formerly required all use of grep or sed may well be managed using bash
statements, and bash phrases may even make your scripts simpler to understand
and manage. Bash returns a 0 when an argument such as $var = “[[0-9]]”
demonstrates that the field on the left satisfies the phrase on the right, or a
one elsewhere, just as much as other contrast operators (e.g., -lt or ==). As
we have given the value “6” to variable “var”, it satisfies the condition,
hence returns 0. Then it will print the message that “6 is a number”. If the
condition goes wrong, it will print “Not Number”. We have saved the file by
“Ctrl+S” and returned it to the terminal via the “Ctrl+X” shortcut key.
Once we have executed the file again on the terminal, it displays that “6 is a
number” via the following query.
$ bash new.sh
It displays the message “6 is a number” because the variable “var” satisfies
the condition within the “if” statement. Let’s update our variable to see the
output once again. Open the bash file once more via:
$ nano new.sh
After opening the file in an editor, we have updated the variable and assigned
it a string type value “G”. This time, the condition shouldn’t be satisfied and
must output the second echo statement “Not a number” in the terminal. Save and
close the bash script file.
Upon the execution of the bash file, we have found the expected results. You
can have a look that is displayed the message “Not a number” in return for the
“if” statement condition. We have used the stated query in the console to see
the output.
$ bash new.sh

Example 03:

Let’s take a very simpler yet a little different example. Open the bash file
“new.sh” again.
$ nano new.sh
When you’re not sure exactly what “regular expression” means, here’s a quick
description. A sequence is represented by a regular expression, which is a
series of letters. Firstly, we have displayed a message “Enter anything” to a
user and then read the input a user enters through the terminal. Then, we have
put the if statement to check whether the input value entered by a user matched
with the mentioned pattern. In the illustration below, [0-9] fit the single
number, but [A-Z] fit a certain capital letter. [A-Z]+ will fit any upper case
combination. The phrase [A-Z]+$, but on the other side, could satisfy a string
consisting entirely of capital letters.
Upon execution, the user entered, 9. It prints that “9 is a number”.
Upon execution again, the user entered #. It displayed that “# is not number”.
When a user entered “K”, it displays that “K is not number”.

Example 04:

Let’s take a complex example to elaborate on the =~ operator. Open the file
once more.
$ nano new.sh
Regex in Bash may be a little tricky. We’re checking if the content of the
$email field seems like that of an email address throughout the sample beneath.
It is indeed worth noting that the very first phrase (the account name) can
include letters, numbers, and special symbols. The @ symbol appears in-between
name and also the email site, as well as a literal dot (.) seen between
principal web domain as well as the “com”, “net”, “gov”, and so forth. Dual
brackets are used to surround the contrast.
Upon first execution, the user entered the correct pattern of email. The output
displays the email with a success message that “email is correct”.
Upon another execution, the user entered the wrong pattern of email. Hence, the
email output shows the failure message that “email doesn’t seem correct”.

Conclusion:

In this guide, we have seen the working and functionality of the =~ operator
within the bash script and what it means in the bash. We hope this guide has
helped you at its best and you have found no issues while taking help from it.


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
