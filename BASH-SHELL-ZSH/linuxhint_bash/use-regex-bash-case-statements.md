





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Using Regex in Bash Case Statements

1 year ago
by Aqsa_Yasin
Regular expression or Regex is said to be alphanumeric strings used for the
creation of search queries. Regular expressions are used as Search and
substitute while validating some conditions. Regex can be used in bash
programming or any other programming language. Most of the time, regex is
usable within the grep statements and not in the case statements. This guide
will see how the regular expressions work with the case statement while using
the Ubuntu 20.04 Linux system. You must have to log in from the system before
going further.

Example 01:

Many times, users found it difficult to use regex (regular expressions) in the
“case” statements because the “regex” never works within case statements. As an
alternative, “grep” has always been utilized instead of a case statement for
regex usage in bash. We will see a simple example to see how the grep and
casework while using regular expressions. So, open the terminal console before
moving further via the shortcut “Ctrl+Alt+T”. After opening the terminal, you
have to create a new bash file with the touch query.
$ touch test.sh
After the creation of the bash file, open it to add the bash code. For that,
try out the query stated below.
$ nano test.sh
The bash file has been opened in the “GNU editor”. Add the bash code shown
below as it is within the bash file. This code will be discussing the usage of
grep while regular expression has been used within it. Add the bash extension
first. We have declared a variable “s” having space and strings as its value.
The first echo statement displays the message that the regex has been used with
“grep” in this example code. In the next line, we have used the echo statement
to display the variable “s”. While the grep, the command has been used to
search the text “word1” from the variable “s,” which matches the regular
expression given in the image. Save your code and leave it via “Ctrl+S” and
“Ctrl+X” in a row.
It’s time to run our bash file to see its results. So, we have used the bash
command to run the file “test.sh”. The output shows the result of variable “s”
along with the message “with grep”. This indicates that the regex works
perfectly within the grep statements.
$ bast test.sh
Let’s create the same output for the case statements this time. So, open your
bash file again in the editor using the “nano” query. Add the bash extension
and define a variable “s” with some value. We have used the “echo” statement to
elaborate on using the case statement now. We have started the case statement
while searching the variable “s” within the regular expression defined in the
code. When it finds the matching string, it must print the variable “s” in the
terminal. Then, the case statement has been ended with the “esac” keyword.
While running the bash file within the terminal, it turns out that it throws an
exception saying” syntax error near unexpected token in [expression]”. This is
simply showing that the regular expression doesn’t work with the case
statement.
$ bash test.sh

Example 02:

Let’s have a glance at another example of regular bash expressions. This time
we will be taking a little different regular expression to explore the working
of regex. On the other hand, we will see regex working within the “if”
statement instead of the “case statement”. So, open the “test.sh” file again.
$ nano test.sh
As the file is opened now, we have added the bash extension and using the “if”
statement to start the condition. Within the “if” statement, it doesn’t allow
us to add any regular expression. That’s why we have used the “=~” expression
to instantiate the regex in the code. Within this condition, we have added the
regex using “$” as a valid regular expression. When the added character matches
the regular expression condition within the “if” statement, it must save that
expression to a variable “n” and print “Valid”. If the condition doesn’t
satisfy, It must print “Invalid” in the terminal and close the “if” statement.
Just save the file by the “Ctrl+S” shortcut and leave the editor by “Ctrl+X”.
Now, returning to the terminal, we have tried the execution statement of bash
to run the file “test.sh” three times by parsing some characters and symbols.
We have added @, #, and f characters this time. All the characters have been
declared “Invalid” as per the bash code. This is because we have used the
regular expression to take “$” only as valid.
$ bash test.sh
Let’s take “$” this time within the execution query to test how it works. It
turns out that the “$” is a valid expression, and it prints the output “Valid”
within the console shell.
$  bash test.sh

Example 03:

Let’s have a different and simple example of using regular expression within
the case statement. Again, let’s open the bash “test.sh” file within the editor
of the Ubuntu 20.04 system.
$ nano test.sh
As the test.sh bash file has been launched within the GNU Nano 4.8 editor of
the terminal, add the bash extension at the start of a file. After that, we
have utilized the “read” statement with the “-p” flag to take input as server
name from the user. This server name as input would be saved in the variable
“SERVER”. This server must be some domain server URL. Now we will utilize the
case statement here to test the regular expression. So, we have started the
case statement with the variable SERVER to check if the added input server
domain matches with the other statements mentioned within the case statement or
not. When the variable “SERVER” value matched the ws*[email protected], it will
use the echo statement to display that this domain is “Web Server”. If it
matches db*[email protected], it will utilize the “echo” statement to display
that the server is some “DB Server”. If the domain is bk*[email protected], it
shows the “Backup Server”. Otherwise, it will display that the server is
unknown. The asterisk represents the regex. After this, the case statement will
be closed by the “esac” keyword in the script. Save this code and exit it by
utilizing the same “Ctrl+S” and “Ctrl+X” shortcuts.
Now coming back to the terminal, let’s test this bash code by executing the
bash command with the name of a test.sh file. After execution, it asks the user
to add the user name. We have added a valid “ws” server name with 1234 as a
regex and pressed Enter. It shows that the server syntax matches with the “Web
Server”.
We have done another execution, and this time we have changed the syntax of a
server. As the dot has been missed from the domain URL, it displays that the
server is unknown.
When we have added a similar and correct domain, it displays the name of a
server.

Conclusion:

Within this tutorial, we have discussed how to utilize a case statement in bash
to use regular expressions. We hope this article has assisted you at its best
to eliminate the doubts and complications.


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
