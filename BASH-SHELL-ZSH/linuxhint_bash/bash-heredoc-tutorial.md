





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to use Here Document in bash programming

1 year ago
by Fahmida_Yesmin
A block of code or text which can be redirected to the command script or
interactive program is called here document or HereDoc. Different types of
scripting languages like bash, sh, csh, ksh, etc., can take text input directly
using here-document without using any text file. So when the coder needs less
amount of text data, then using code and data in the same file is the better
option, and it can be done easily by using here-document in the script. Without
scripting language, here document can also be used in various high-level
languages like php, perl, etc. How you can use here-document in the bash script
is shown in this tutorial.
To use here-document in any bash script, you have to use the symbol << followed
by any delimiting identifier after any bash command and close the HereDoc by
using the same delimiting identifier at the end of the text. The syntax of
writing HereDoc is shown below.
Command << HeredocDelimiter    
. . .
. . .
HeredocDelimiter

Example-1: Use of Simple heredoc Text

When the heredoc is used in any script, it is necessary to keep the same name
for the starting and ending delimiter. Suppose the command is `cat` and the
heredoc delimiter is ADDTEXT. Create a bash script file named heredoc1.bash
with the following code to check the simple use of heredoc.
#!/bin/bash
cat <<ADDTEXT
This text is
added by Here Document
ADDTEXT
Run the following command to execute the script.
$ bash heredoc1.bash
Output:
The following output will appear after executing the script.

Example-2: Use of heredoc with ‘-’ symbol

HereDoc uses the ‘–‘ symbol to suppress any tab space from each line of heredoc
text. In the following example, tabspace is added at the start of each line,
and the ‘–‘ symbol is used before the starting delimiter. When the script
executes, all tab spaces are omitted from the starting of each line, but it
creates no effect on normal space. Create a bash file named heredoc2.bash with
the following script to test the function of ‘–‘.
#!/bin/bash
cat <<-ADDTEXT2
    Line-1: Here Document is helpful to print short text
    Line-2: Here Document can be used to format text
    Line-3: Here Document can print variables within the text
    Line-4: Here Document with '-' removes tab space from the line
ADDTEXT2
Run the following command to execute the script.
$ bash heredoc2.sh
Output:
The following output will appear after executing the script. The tabspace has
been removed from the heredoc content.

Example-3: Use of Variable within heredoc Text

Create a new bash script with the following code. Here, two variables named
start and end are declared. These variables are used within the heredoc text.
If you use a quotation mark at the starting delimiter of heredoc, then the
variable’s value will not print in the console.
#!/bin/bash
start="Hello everybody"
end="Good Luck"

cat <<ADDTEXT3
$start
Welcome to Linux Blog Site.
$end
ADDTEXT3
Run the following command to execute the script.
$ bash heredoc3.sh
Output:
The following output will appear after executing the script. The output shows
the heredoc content with the value of the variables.

Example-4: Create a new bash file using HerDoc

In the previous examples, how you can use heredoc in any bash script are shown.
You can also create a new bash file using heredoc, shown in the next part of
this tutorial. Create a new bash file named heredoc4.sh with the following
code. Here, the NewFile variable is declared to set the file name of the new
bash script, which will be created after the execution of heredoc4.sh file.
After the execution, a new bash file named output.sh will be created.
#!/bin/bash
NewFile=output.sh        
(
cat < $NewFile
Run the following commands to test the above script. The first command will
execute the main script file. The second command will display the content of
the newly created file. The third command will run the newly created bash file.
$ bash heredoc4.sh
$ cat output.sh
$ bash output.sh
Output:
The following output will appear after executing the script.

Example-5: Using Function with heredoc

You can pass input values to the variables of any function of the bash script
from heredoc content. Create another new bash file named heredoc5.sh to test
how function can be used with heredoc. Add the following code to the file. A
function named BookInfois declared in the script, which will take data from
heredoc text. Six variables are declared in the function named ISBN, bookName,
authorName, edition, publication, and price. To set the value of the variables
properly, you have to maintain the order of the values in the heredoc section
according to the variables declared in the function. After setting the data in
the function variables, the price value is calculated by a 10% discount and
printed the values of all variables in the console.
#!/bin/bash
#Declare the function which will retrieve data from Here Document
BookInfo ()
{
  read ISBN
  read bookName
  read authorName
  read edition
  read publication
  read price
}
# Declare here document part to send data into the function
BookInfo <<ADDTEXT5
ISBN-78633567809
Easy Laravel 5
W. Jason Gilmore
9th Edition
Learpub
100
ADDTEXT5
# Print the value of the function variables after calculating price value with
10% discount
((price=$price-$price*10/100))
echo "$bookName"
echo "$authorName"
echo "$edition, $publication"
echo "$"$price
Run the following command to execute the script.
$ heredoc5.bash
Output:
Here, the value of the price variable has been set to 100. After setting a 10%
discount on price value, the value has been set to 90. After the execution, the
following output will appear in the terminal.

Example-6: Execute commands inside the heredoc

Create a bash file named heredoc6.bash with the following script to execute
`date`, `pwd`, and `whoami` command with `sudo` command.
#!/bin/bash

# Add three commands inside the heredoc content with the `sudo` command
sudo -s  <<COMMAND
date
pwd
whoami
COMMAND
Output:
The following output will appear after executing the above script. The output
of the three commands has printed in the output.

Example-7: Use of heredoc to write multiple lines into a file

Create a bash file named heredoc6.bash with the following script to add
multiple lines in the text file named temp.txt and print the file’s content.
Three lines will be added to the text file after executing the code.
#!/bin/bash

: 'This script will write multiple lines
into a text file
'
# Write multiple lines into a file using heredoc
cat > 'temp.txt' <<FileContent
Bash is a popular scripting language.
Many administrative tasks can be done easily
by using bash script.
FileContent

# Print the content of the file
cat temp.txt
Output:
The following output will appear after executing the above script. The output
shows that three lines are added in the temp.txt file.

Example-8: using heredoc with pipe to search and replace the content

The heredoc input can also be piped. Create a bash file with the following
script to search and replace a particular character from the heredoc content.
The first heredoc will print the original text, and the second heredoc will
print the replaced text. The `sed` command has been used here to replace all
instances of the character ‘a’ by ‘A’.
#!/bin/bash

echo "The original content is:"
cat <<'ORIGINAL'
Bash is a shell scripting language
HTML is a markup language
Javascript is a client-side scripting language
ORIGINAL

# Add a newline
echo

echo "The content after replacing 'a' by 'A':"
cat <<'REPLACE' |  sed 's/a/A/g'
Bash is a shell scripting language
HTML is a markup language
Javascript is a client-side scripting language
REPLACE
Output:
The following output will appear after executing the above script. In the
output, all ‘a’ have been replaced by ‘A’.

Example-9: Use of heredoc to comment out the block of lines

One of the important use of heredoc is to comment on multiple lines of the bash
script. Create a bash file with the following script to find a year is a leap
year or not. The purpose of the script has been described by multi-line
comments using heredoc.
#!/bin/bash

<<multiline_comment
    This script is used to find out
    a year is a leap year or not a
    leap year
multiline_comment

# Take 4-digit year value from the user
echo -n "Enter the four digit year value: "
read yr

# Check the taken year value is a leap or not a leap year
if [ $(($yr%400)) -eq 0 ]; then
    echo "$yr is a Leap year."
elif [ $(($yr%100)) -eq 0 ]; then
    echo "$yr is not a Leap year."
elif [ $(($yr%4)) -eq 0 ]; then
    echo "$yr is a Leap year."
else
    echo "$yr is not a leap year."
fi
Output:
The following output will appear after executing the above script. The
following output shows that 2008 is a leap year and 2021 is not a leap year.

Conclusion:

The various uses of the heredoc document have shown in this tutorial by using
multiple examples. It can be used with different types of shell commands and
adding multi-line comments in the bash script. The uses of the heredoc will be
cleared for the bash users after practicing the examples of this tutorial.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
