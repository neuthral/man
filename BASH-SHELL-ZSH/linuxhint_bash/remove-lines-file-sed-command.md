





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How do I Remove Lines from a File Using the SED Command

1 year ago
by Prateek_Jangid
The sed command is known as a stream editor. The sed command is used in Linux
to do basic text transformation.
One of the many essential commands of Linux is also the sed command which plays
a vital role in file manipulation. It is used for many purposes; some of the
main ones are as follows.
Remove or delete that particular line that matches the given patterns.

* Removing lines with regular expressions.
* Based on a file’s position, delete a specific line.

So, if you are thinking about removing lines from a file using the sed command,
please read our article from start to end. We will give you a brief on the
methods to remove lines

How do I Remove Lines from a File Using the SED Command?

We will use the sed command without -i in this article because it is a
demonstration article. A similar method is the “dry run” option, which shows
all values for the file without making any changes.
Using the sed command, we can remove the lines depending on the environment by
using -i.
To show the sed command, we create a file called LinuxhintOS.txt. In order to
provide better information, we include these line numbers in the following
content.

Removing Lines from a File Based on Position

This part will explain using the sed command to remove lines from a file
‘LinuxhintOS.txt’ based on its position.
First, open the file using the following command:
cat ~/<foldername>/<filename>
Now execute the below command to delete the first line:
sed 'Nd' file
In the above command:
N– “Nth” line in a file
D– deletion of the file
So, let’s execute this command into our example to delete the 10th line from
the text file:
cd Documents

sed '10d' LinuxhintOS.txt

Remove the Last Line from a File

If we have to remove the last line from the file, instead of ‘N’ in the syntax
used above, we will use ‘$.’ Here, $ represents the last line.
sed '$d' file
After this, our file will change to something like this.

Remove the First Line and Last Line Together

If we want to remove the first and last lines, we must combine the above two
commands.
sed 'Nd;$d' filename
With this command, both our first and last lines are removed from the file
simultaneously.
As you can see in the above image, the first and last line has been removed
from the text file.

Remove a Range of Lines

The sed command can remove the lines of any range. For this, we just have to
enter ‘minimum’ and ‘maximum’ line numbers.
In this example, we will remove the lines ranging from 4 to 7 numbers.
sed '4,7d' file
After removing these ranges of lines, our file will look like this.

Remove Multiple Lines

sed can also remove multiple lines in a set. As you can see, we removed the
third, sixth, eighth, and last lines in this example.
sed '3d;6d;8d;$d' file
When applying the sed command written above, the following changes occur in our
file ‘LinuxhintOS.txt’.

Removing Lines Other Than the Specified Line or Specified Range of Lines

Through the sed command, we remove those lines from the files which are not
defined in the command, i.e., the lines other than the ones that are described
are removed.
From this file, we will remove the remaining lines apart from the numbers 4 to
7.
Sed '4,7! d' file
Over here, the sign of “!” represents that we should not remove the line of
this specific number from the file.
! – used to keep the specific number of lines from the file
After this, our file will look something like this:

Remove the Blank or Empty Lines

The sed command written below removes blank or empty lines from the appropriate
file.
sed '/^$/d' file
Since there are no blank or empty lines in our file, no changes have occurred:

Remove Lines from the File Based On the Pattern

In the second part, we will see that with the help of the sed command, how we
remove lines of a similar pattern.

Removing Lines that Contain a Pattern

In the example, the following command removes the lines matching the “System”
pattern from the file ‘LinuxhintOS.txt’.
sed '/System/d' file
So, we need to remove those lines which have “Not Available”. That’s why we
will execute the below command:
sed '/Not Available/d’ LinuxhintOS.txt

Removing Lines that Contain One or Several Strings

Through the sed command, we can remove the lines matching the “Not Updated” or
“Not Available” pattern from the file ‘LinuxhintOS.txt’ and that command is
something like this:
sed '/Not Updated\|Not Available/d' LinuxhintOS.txt

Removing lines that starting with a specific character

We can remove all lines starting with any character through the sed command. We
have created a new file named ‘LinuxhintOS.txt’ with the following contents:
The below sed command will remove all lines starting with the ‘A’ character.
sed '/^A/d' file
We will remove such lines from our file, which start with ‘A’ and ‘L’. For
which we will use the following command.
sed '/^[AL]/d' file
Using sed, we remove all lines beginning with “A” and ending with the string
“Linux”.
sed '/^(A).*(Linux)/d' file

Removing Lines that End with a Specified Character

This sed command removes all lines ending with “m.”
sed '/m$/d' file
The following sed command will remove lines ending with both ‘M’ and ‘X’
characters.
sed '/[xm]$/d' file
The lines of characters ending with ‘M’ and ‘X’ are removed from our file;
then, our file will look like this.

Removing All Lines that Start With Uppercase

We will remove all those lines from the file using the following command: an
uppercase letter.
sed '/^[A-Z]/d' file
After applying the above command, all the lines from our file which started
with uppercase letters will be removed, and the change in our file will be like
this.

Removing a Matching Pattern Line With a Specified Range

With the help of the following command, we will remove only those lines from
some defined lines with a specific pattern.
This example only removes lines with Linux patterns from the file between 1 to
6 lines.
sed '1,6{/Linux/d;} file
After applying the command, our file ‘sed – demo-1.txt’ will look something
like this.
We will delete the second row with the following sed command only if it
contains the “openSUSE” pattern.
sed '2{/openSUSE/d;}' file
The appropriate command will remove the second line from our file ‘sed – demo-
1.txt’ as it has a specific pattern of “openSUSE.”
The appropriate command will remove the second line from our file ‘sed – demo-
1.txt’ as it has a specific pattern of “openSUSE.”
We can also delete the line matching the ‘system’ pattern and the following
line in the file using the sed command.
sed '/System/{N;d;}' file

Remove the Lines having Specific Patterns

You can remove all lines following the “CentOS” pattern using the sed command.
sed '/Centos/,$d' file

Removing Lines that Contain Numbers/Digits

With the sed command written below, we can remove all the lines containing
‘digit.’
sed '/[0-9]/d' file
By making some changes in the sed command, we will remove all those lines from
the file that start with only digits.
sed '/^[0-9]/d' file
After this command, all the lines that start with digits will be removed from
our file.
Again, by making some changes in the command, we will remove only those lines
from the file that ends with a digit.
sed '/[0-9]$/d' file

Removing Lines that Contain Alphabetic Characters from a File

With the sed command, we will delete all lines from the file ‘LinuxhintOS.txt,’
which contain any alphabetical characters.
sed '/[A-Za-z]/d' file

Conclusion

This article shows several examples of removing lines from a file using the sed
command. We see how with the help of the sed command, we can easily remove any
lines from files. If we remember these commands, then we save a lot of time
while reducing.


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
