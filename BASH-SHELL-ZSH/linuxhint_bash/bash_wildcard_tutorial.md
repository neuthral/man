





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Wildcard

1 year ago
by Fahmida_Yesmin
When we need to search for anything using shell commands then we need to define
a pattern for searching. Wildcard characters are used to define the pattern for
searching or matching text on string data in the bash shell. Another common use
of wildcard characters is to create regular expressions. How you can use
different types of wildcard characters for searching files is shown in this
tutorial.

Wildcard Characters

The three main wildcard characters are,

* Star or Asterisk (*)
* Question mark (?)
* Square brackets ([])

Asterisk (*) is used to search for a particular character(s) for zero or more
times. Question mark (?) is used to search for a fixed number of characters
where each question mark (?) indicates each character. Square brackets are used
to match with the characters of a defined range or a group of characters. The
uses of these characters are shown in the next part of this tutorial.

Use of Asterisk (*)

Asterisk (*) can be used in various ways with shell commands for searching
files. Different use of the asterisk (*) are shown in the following examples.

Example – 1: Searching Specific File with Filename and ‘*’

‘ls’ command is used to find out the list of files and folders of the current
directory. ‘ls a*’ command will search and print all filenames of the current
directory that starts with the character, ‘a’.
$ ls
$ ls a*
Output:
According to the following output, 12 files exist in the current directory that
starts with the character, ‘a’.

Example – 2: Searching File with Particular Extension and ‘*’

You can search any file by using the asterisk (*) and the file extension. If
you want to search all files with the ‘.txt’ extension from the current
directory then run the following command from the terminal. Here, the filename
can be any character(s) and any number of characters.
$ ls *.txt
You can also search files of different extensions by using the asterisk (*).
The following command will search any files with extension ‘.sh’ or ‘.txt’
$ ls *.sh *.txt
Output:
The output shows the list of all existing files of the current directory with
the extension ‘.sh’ and ‘.txt.

Example – 3: Removing File by Partial Match and ‘*’

You can use the asterisk (*) for matching any filename partially. The following
command will remove the file which contains the ‘test’ word in any part of the
filename.
$ ls
$ rm *test*
$ ls
Output:
The following output shows that two files exist in the current directory that
contains the word ‘test’ and these files have been removed after executing the
‘rm’ command.

Use of Question Mark (?)

When you know the exact numbers of characters that you want to search then the
question mark (?) wildcard can be used. The following examples show the
different use of question mark (?) wildcard.

Example – 1: Searching File with Filename and ‘?’

Suppose, the file extension, the total number of characters of a file, and some
characters of the file are known, then you can use this wildcard to search the
file. The first command will search those files which have the extension
‘.txt’. The second command will search those files which are four characters
long, the last character is ‘t’ and the extension of the file is ‘.txt’.
$ ls *.txt
$ ls ???t.txt
Output:
The output shows that 7 files exist in the current directory with the ‘.txt’
extension and one text file exists that is 4 characters long and the last
character is ‘t’.

Example -2: Searching File with Extension and ‘?’

Suppose, you know the filename and the total number of characters of the file
extension then you can use the question mark (?) wildcard to search the file.
The following command will search the file with filename ‘hello’ and the
extension is three characters long.
$ ls
$ ls hello.???
Output:
According to the output, two files exist in the current directory that has the
name, ‘hello’ and the extension is three characters long.

Use of Square Brackets ([])

Different ranges of characters or group of characters can be used within square
brackets ([]) for searching files based on the range.

Example -1: Search Files of Any Extension with Two Ranges Values

The following command will search any file whose name contains any character
within ‘a-p’ and any digit within ‘0-5’ and the file extension can be any
character.
$ ls
$ ls [a-p0-5]*.*
Output:
The following output shows the list of all files that match the pattern used in
the command.

Example-2: Search File Starts with a Particular Character and is Followed by
Another Character

In this example, the second command will search the filenames starting with any
of these characters [afgh] followed by the character ‘o’ with any extension.
$ ls
$ ls [afgh]*o*
Output:
The following output shows the list of all files that match the pattern used in
the command.

Example-3: Search Filenames with the Prefix Value

The following command will match those files whose name starts with ‘fn’ and is
followed by a number within 0 to 5.
$ ls fn[0-5]
The following command will match those files that contain the name, ‘hello’ and
the extension contains any character from t to z.
$ ls hello.[t-z]*
Output:
The following output shows the list of all files that match with the pattern
used in the commands.
The character class can be used in the third brackets to match the filename or
the particular string in the script. Different classes that can be used in the
pattern has described below.

Class name Purpose
[:alpha:]  It is used to match with any uppercase and lowercase letter and
           equivalent to [a-zA-Z].
[:digit:]  It is used to match with any digits and is equivalent to [0-9].
[:alnum:]  It is used to match any alphabet and digit. It is equivalent to [a-
           zA-Z].
[:upper:]  It is used to match with uppercase latter only and equivalent to [A-
           Z]
[:lower:]  It is used to match with uppercase latter only and equivalent to [a-
           z]
[:blank:]  It is used to match with space and tab.
[:print:]  It is used to match with printable characters.
[:cntrl:]  It is used to match with non-printable characters.
[:space:]  It is used to match with while-space.
[:xdigit:] It is used to match with hexadecimal digits.
[:ascii:]  It is used to match with ASCII characters.
[:word:]   It is used to alphanumeric characters including underscore(_).

The uses of four mostly used classes have explained in the following four
examples.

Example-1: Use of [:alpha:] in Bash Script

The following script will check that the input taken from the user contains
alphabetic characters only.
#!/bin/bash
echo -n "What is your name? "
# Assign input value to the variable
read name

# Check the input value contains the alphabet only
if [[ "$name"  =~ ^[[:alpha:]] ]]; then
    echo "Your name is $name."
else
    echo "Enter alphabetic character only."
fi
Output:
The following output shows the message for invalid and valid input.

Example-2: Use of [:digit:] in Bash Script

The following script will check that the input taken from the user contains
numeric characters only.
#!/bin/bash
echo -n "Enter your ID: "
# Assign input value to the variable
read id

# Set the ID value
ID="ID-$id"
# Set the pattern using [[:digit:]] class
regex="ID-[[:digit:]]+"

# Check the input value contains the number only
if [[ $ID  =~ $regex ]]; then
    echo "$ID is valid."
else
    echo "$ID is invalid."
fi
Output:
The following output shows the message for invalid and valid input.

Example-3: Use of [:alnum:] in Bash Script

The following script will check that the input taken from the user contains
alphanumeric characters only.
#!/bin/bash
echo -n "Enter your address: "
# Assign input value to the variable
read addr

# Check the input value contains the alphabet and number only
if [[ $addr  =~ ^[[:alnum:]] ]]; then
    echo "Address is valid."
else
    echo "Address is invalid."
fi
Output:
The following output shows the message for invalid and valid input.

Example-4: Use of [:upper:] in Bash Script

The following script will check that the input taken from the user contains
capital letters only.
#!/bin/bash
echo -n "Enter your code in uppercase letter: "
# Assign input value to the variable
read code

# Check the input value contains all uppercase latter
if [[ $code  =~ ^[[:upper:]] ]]; then
    echo "Code is correct."
else
    echo "Code can contain uppercase only."
fi
Output:
The following output shows the message for invalid and valid input.

Conclusion

The basic uses of wildcard characters for searching files in the terminal and
validating data using bash script have been shown in this tutorial. I hope the
examples shown here will help the Linux users to write regular expression
patterns properly to match any content for different purposes.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
