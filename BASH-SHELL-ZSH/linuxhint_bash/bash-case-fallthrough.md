





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Case Fallthrough

4 months ago
by Saeed_Raza
While working in many programming languages, you may have used different
conditional statements like if-else, switch, and many more. Within the Bash
programming, we tend to use a “case” statement in which only one matching block
gets executed after the execution of the case statement. The Bash also provides
us the opportunity to perform the fallthrough in the case statement like
executing the several matching blocks or all blocks.
Before starting our examples, we need to create the Bash file. For this, you
must launch the consol application that is built-in in each Linux distribution.
To launch the console application, you can try the shortcut “Ctrl+Alt+T”. Use
the Linux list “ls” query to list down all the folders in the current home
directory. There are no Bash files available, so execute the “touch”
instruction to generate a new Bash file named “fall.sh”. After this, list the
contents of the directory again and the file “fall.sh” is listed in it.

Example 01: Simple Case Statement

After the file creation, it’s time to open it within some built-in editor to
start adding the Bash script in it. You can utilize the text editor if you are
new to Bash for your convenience. Otherwise, prefer to use the “Gnu Nano”
editor for quick edits and execution of the Bash script. Execute the “nano”
command in the shell to open the “fall.sh” file within the Nano editor in a
second. The command is as follows:

The “fall.sh” empty file is opened in the Gnu Nano editor. Add the following
Bash script in it. The Bash script starts with the simple Bash path which is
not necessary to add. A variable “v” is initialized with a value “1”. The case
statement starts with the use of the “$v“ variable to check if the value of
this variable lies in any of the mentioned cases. If case 1 matches the
variable “v” value, it display “Physics” by using its echo statement. If case 2
matches the variable “v” value, it displays “Chemistry” by using the echo
statement. And, if case 3 matches the variable “v” value, it shows “Biology” by
using the echo statement. Within the simple case statement, there is one thing
to be noted and that is the use of the double “;;” characters within each case
of the case statement. This sign makes the case statement a simple statement.
The case statement is completed by the keyword “esac” as displayed in the
following. Let’s save our code first and then execute it on the console via the
use of Ctrl+S and Ctrl+X.

Within the console query area, we execute the Bash instruction to run the
“fall.sh” Bash file and see its results. The output displays the result of the
first case – “Physics”. This is because the first case matched with the
condition in the case statement start – variable “v” has a value of 1.

Example 02: Case Fallthrough Statement

Within this example, we will expalain how we can use the fallthrough in the
case statement using the special character “;&” in it. Within this code, we use
the very same variable “v” with the same value in the case statement and
execute each of its cases for the value 1, 2, and 3. All the echo statements
within each case of the “case” statement are similar to the previous example
that demonstratres the use of a simple case statement. The only change in this
overall code is the use of “;&” special character combination instead of “;;”
special character combination. Save this Bash script first and then execute it
to see what happens in the end.

We tried the “Bash” instruction with the updated “fall.sh” file name in the
query area of a console application of the Ubuntu 20.04 system. The use of “;&”
special characters leads to the case fallthrough where each echo statement from
each case is executed and displayed the respective result due to the fall-
through that happened in the code.

Example 03: Fallthrough Using Specific Patterns

Within the example, we will use a pattern matching to perform the fall-through
in the case statement. We update the value of variable “v” with some string
value, “gmr”. The case statement used in this Bash script uses the variable “v”
to search for specific patterns in each case. All three cases are different
from the previous two examples containing patterns to be matched. The first
case matches only the middle character, the second case matches its first
character, while the third case matches all the three characters with the
variable “v”. As the first two cases got satisfied, their respective “echo”
statements are executed and the console displays “Physics” and “Chemistry”.
This is because we utilized the pattern matching along with the “;;&” special
characters. End this program with a Ctrl+X shortcut after saving the Bash file
with the “Ctrl+S” shortcut.

Our code is saved and is ready to be executed. We tried the Bash instruction in
the Ubuntu 20.04 console along with the “fall.sh” file as presented. It
displayed the result of the first two cases after matching the pattern while
utilizing the fallthrough in the case statements “Physics” and “Chemistry” .
The third case was not executed because the pattern didn’t match.

Conclusion

The starting paragraph elaborates on the use of the different conditional
statements along with the case statements in different languages. It also
discussed the use of the fallthrough within the case statement. After that, we
implemented and discussed some Bash examples in Ubuntu 20.04 to show the
difference between using a simple case statement and the fallthrough case
statement. In the end, we performed the fallthrough using the pattern matching.
As far as the uniqueness is concerned, this guide would be of great assistance
to you.


About the author


Saeed Raza

Hello geeks! I am here to guide you about your tech-related issues. My
expertise revolves around Linux, Databases & Programming. Additionally, I am
practicing law in Pakistan. Cheers to all of you.
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
