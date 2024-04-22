





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Get the Size of a File in a Bash Script

1 year ago
by John_Otieno
When writing shell scripts, we may come across a situation where we need to
know the size of a file. For example, you may need to use this size to perform
other actions, such as moving the file to a different directory or deleting it.
This tutorial will discuss quick methods you can use in a bash script to get
file size in the specified format such as Bytes, Kilobytes, Megabytes, or
Gigabytes.

Method 1: The ls command

The first method is to use the good old ls command. When paired with other
commands, the ls command can grab the size of a file.
To implement the script, we need the full path of the file, list the file
information with ls, and grab the size using a command such as awk.
A sample script for that would look like this:
#!/bin/bash
echo "Enter the full path to the file."
read file
filesize=$(ls -lh $file | awk '{print  $5}')
echo "$file has a size of $filesize"
The above script is relatively simple. Using the echo and read command, we get
the name of the full path of the file.
Next, we use the ls -lh command to list all directories and the size in human-
readable format, and finally, pass the output to awk and grab the size as the
5th variable.
The following is an illustration of the script.
chmod +x size.sh
./size.sh
Here is the output for that:
sudo ./size.sh
Enter the full path to the file
/etc/passwd
/etc/passwd has a size of 2.9K

Method 2: The wc command

Another method we can use to grab the size of a file in a bash script is the wc
command. The wc command returns the number of words, size, and the size of a
file in bytes.
Now:
As you know, reading the file size in bytes is not very easy. To counter this,
we can implement a simple menu and ask the user the size format such as KB, MB,
and GB.
Depending on the format selected, we will convert the bytes to said format.
Here is an example script to implement such logic:
#!/bin/bash
echo "Select size format, use numerical values (1 for Bytes,  2 for Kilobytes,
etc.)"
echo """
        1. Bytes
        2. KiloBytes
        3. MegaBytes
        4. GigaBytes
     """
echo "************************************************************************"
read format

echo "Enter the full path to the target file: "
read file
filesize=$(wc -c $file | awk '{print $1}')
if [[("$format" == 1)]];
then
    echo "$file is approx $filesize Bytes"
elif [[("$format" == 2)]];
then
    kb=$(bc <<<"scale=3; $filesize / 1024")
    echo "$file is approximately $kb KB"
elif [[("$format" == 3)]];
then
    mb=$(bc <<<"scale=6; $filesize / 1048576")
    echo "$file is approximately $mb MB"

elif [[("$format" == 4)]];
then
    gb=$(bc <<<"scale=12; $filesize / 1073741824")
    echo "$file is approximately $gb GB"
else
    echo "Incorrect format."
    exit
fi
In the script above, we start by asking the user to enter the file size format.
Bash reads this input and stores it to the format variable.
Next, we prompt the user for the file path and store this variable in a file.
The next step calls the wc -c-command on the specified file. Since wc -
c returns the file size in bytes and the file's path, we use AWK to grab only
the file size. We store the size in bytes as filesize.
Finally, we implement a simple if statement to check if the size format is
either 1 (Bytes), 2 (Kilobytes), 3 (Megabytes), 4 (Gigabyte). We then use the
bc command to convert file size in bytes to the specified format.
NOTE: We use a variating scale for the bc command to accommodate the number of
decimals per evaluation.
The image below shows how the script works.
ANOTHER NOTE: The above script is pure barebones and is therefore open to
significant improvements. Feel free to improve it and tweak it to your needs.

Method 3: Using stat command

We cannot forget the stat command. Using the stat command, we can display
detailed information about a file or the file system.
The stat command returns the size in bytes as well. You can use similar logic
in the script above to select the format.
Here is a simple script using the stat command:
#!/bin/bash
echo "Enter the file path."
read file
filesize=”$(stat -c %s $file)
echo "$file is precise $filesize bytes."

In Closing

This tutorial has discussed three methods you can use to get the size of a file
using a bash script. It is good to note that Linux has a comprehensive
collection of tools and methods to achieve this. Find the one that works for
you and stick with it.


About the author


John Otieno

My name is John and am a fellow geek like you. I am passionate about all things
computers from Hardware, Operating systems to Programming. My dream is to share
my knowledge with the world and help out fellow geeks. Follow my content by
subscribing to LinuxHint mailing list
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
