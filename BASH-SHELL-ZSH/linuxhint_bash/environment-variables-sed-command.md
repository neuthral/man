





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use Environment Variables in Sed Command

1 year ago
by Prateek_Jangid
An environment variable is a dynamically named value. Environmental variables
are usually exported to a terminal using the command shown below.
export $SOMEVARIABLE=value
Files are available in all terminals after source; for this purpose,
environmental variables are stored inside bash files.
Suppose the user has to use or change environmental variables with the help of
the sed command. In that case, Users cannot use the command as mentioned above
for this. Different functions and methods have to be used for the sed command.
In this article, we will see some such methods, which are as follows.
In the Linux command-line, sed is a potent processing tool. Using compact sed
one-liners, users often do text replacement which is quite convenient. When
users replace sed with shell variables, it also has some disadvantages.

How to Use Environment Variables in Sed Command

Let’s have an example, here we have a file named test.txt.
cat test.txt
CURRENT_TIME = # fill the
current date and time
JAVA_HOME = # fill the
JAVA_HOME path
We will write a shell script to populate the JAVA_HOME path and current time in
the above given current system. This process is easy, but there are some
problems in it which are possible. Here we will write a script using GNU sed.
As we have mentioned above, here, we will substitute the JAVA_HOME path and
current time. For this, we will first fill the current time in the right places
here. We can use the date command to get the current time.
cat solution.sh
#!/bin/sh
MY_DATE=$(date)
sed -i -r 's/^(CURRENT_TIME =).*/\1 $MY_DATE/' test.txt
The script written above is not too difficult to understand. By first
substituting the command in a variable MY_DATE, get the time and current date
and save it.
After getting the data using sed substitution, the user fills it in the file.
We have used the -i option of the GNU sed command to perform in-place editing.
Now we will check and execute our script.
$ ./solution.sh
$ cat test.txt
CURRENT_TIME = $MY_DATE
JAVA_HOME = # fill the JAVA_HOME path
We see in the output that the line with “CURRENT_TIME =” has been replaced.
However, the literal “$MY_DATE” is filled in instead of the time and current
date.
The reason why shell variables are not expanded within single quotes is that we
used single quotes under the sed command.
Double quotation marks are used in the sed command to allow quick fix shell
variable expansion.
$ cat solution.sh
#!/bin/sh
MY_DATE=$(date)
sed -i -r "s/^(CURRENT_TIME =).*/\1 $MY_DATE/" test.txt
Now we will test the solution.sh script again.
$ ./solution.sh
$ cat test.txt
CURRENT_TIME = Wed Jan 27 10:02:05 PM CET 2021
JAVA_HOME = # fill the JAVA_HOME path
After filling the time and date in the right places, the JAVA_HOME path is
filled.
We see which delimiter we should use by adding another sed command to our
Solution.sh script.
$ cat solution.sh
...
sed -i -r "s/^(CURRENT_TIME =).*/\1 $MY_DATE/" test.txt
sed -i -r "s/^(JAVA_HOME =).*/\1 $JAVA_HOME/" test.txt
Checking the above script.
$ ./solution.sh
sed: -e expression #1, char 24: unknown option to `s'
We see that the new sed command that has been added is not working. If we test
it for the second time, we see that only its variable is different, but working
is the same as the sed command. To Solve This, We Should Take the Following
Measures:

The Delimiter Does Not Exist in the Variable

To know this well, users must first understand what the environment variable
$JAVA_HOME contains.
$ echo $JAVA_HOME
/usr/lib/jvm/default
We can see those shell variables are expanded within double-quotes. So our
second sed command comes after variable expansion.
sed -i -r "s/^(JAVA_HOME =).*/\1 /usr/lib/jvm/default/" test.txt
The slashes (/) in the variable’s value interfere with the ‘s’ command (s/
pattern/replacement/), which is why the above sed command does not work. In
this way, we can select other characters as delimiters of the ‘s’ command.
Users can slightly modify the second sed command to solve this by using ‘#’ as
the delimiter of the s command.
sed -i -r "s#^(JAVA_HOME =).*#\1 $JAVA_HOME#" test.txt
Now we test the above script.
$ ./solution.sh
$ cat test.txt
CURRENT_TIME = Wed Jan 27 10:36:57 PM CET 2021
JAVA_HOME = /usr/lib/jvm/default

Solution 2

solution.sh works in most cases. Also, we see that ‘#’ in filenames is a valid
character on most *nix file systems. If we execute our script to JAVA_HOME on a
system set to /opt/#jvm#, the user’s script fails again. We Will Do the
Following Work for Our Script to Work in all Cases

  1. If the user takes ‘#’ as the delimiter for better readability, they must
     select a delimiter for the sed command.
  2. We have to escape all the delimiter characters which are in the contents
     of the variable.
  3. Lastly, collect the remaining material in the sed command.

Users can use bash substitution to escape the delimiter. For example, the user
can escape all ‘#’ characters in variable $VAR.
$ VAR="foo#bar#blah"
$ echo "${VAR//#/\\#}"
foo\#bar\#blah
Now we will apply our script here.
$ cat solution.sh
#!/bin/sh
MY_DATE=$(date)
sed -i -r "s/^(CURRENT_TIME =).*/\1 $MY_DATE/" test.txt
sed -i -r "s#^(JAVA_HOME =).*#\1 ${JAVA_HOME//#/\\#}#" test.txt
We will test by executing our script with the spurious JAVA_HOME variable to
see if it works as expected.
$ JAVA_HOME=/opt/#/:/@/-/_/$/jvm ./solution.sh
$ cat test.txt
CURRENT_TIME = Thu Jan 28 11:23:07 AM CET 2021
JAVA_HOME = /opt/#/:/@/-/_/$/jvm
We conclude that our script works even though we have many special characters
in our JAVA_HOME variable.

Conclusion

In this article, we saw how to use environmental variables with the sed
command. They also make many mistakes that they cause, which we have also
mentioned in this article and their redressal. We hope that from this article
you will get the complete knowledge that you need.


About the author


Prateek Jangid

A passionate Linux user for personal and professional reasons, always exploring
what is new in the world of Linux and sharing with my readers.
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
