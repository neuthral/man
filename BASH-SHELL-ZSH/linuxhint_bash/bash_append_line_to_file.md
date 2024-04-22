





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to append a line to a file in bash

2 years ago
by Fahmida_Yesmin
Sometimes we need to work with a file for programming purposes, and the new
line requires to add at the end of the file. This appending task can be done by
using ‘echo‘ and ‘tee‘ commands. Using ‘>>’ with ‘echo’ command appends a line
to a file. Another way is to use ‘echo,’ pipe(|), and ‘tee’ commands to add
content to a file. How these commands can be used in the bash script are shown
in this article.
Create a text file named books.txt with the following content to do the
examples shown in the next part of this article.
books.txt:
Learning PHP and MySQL
Learning Laravel
Web Design using HTML

Example-1: Append line to the file using ‘echo’ command and ‘>>’ symbol

In the following script, an existing file, books.txt is assigned to the
variable, filename, and a string value will be taken as input from the user to
add at the end of the file. If the input value is not empty, then the ‘echo’
command will append the value into the books.txt file by using ‘>>’ symbol.
#!/bin/bash

# Define the filename
filename='books.txt'

# Type the text that you want to append
read -p "Enter the text that you want to append:" newtext

# Check the new text is empty or not
if [ "$newtext" != "" ]; then
      # Append the text by using '>>' symbol
      echo $newtext >> $filename
fi
Output:
‘Learning JQuery‘ is taken as a new text value in the output that is appended
at the end of the file.

Example-2: Append line to the file using ‘printf’ command and ‘>>’ symbol

 
‘>>’ symbol can be used with the ‘printf’ command to append formatted content
to a file.  Like the previous example, the filename and the string values are
assigned to the variables, filename, and newtext. Next, ‘printf’ command will
redirect the value of newtext with other text into the end of the
books.txtfile.
#!/bin/bash

# Define the filename
filename='books.txt'

# Type the text that you want to append
read -p "Enter the text that you want to append:" newtext

# Check the new text is empty or not
if [ "$newtext" != "" ]; then
      # Append the text by using '>>' symbol
      printf "Appended text is: %s\n" "$newtext" >> $filename
fi
Output:
‘Website by WordPress‘ is taken as a new text value in the output that is
appended at the end of the file.

Example-3: Append line to the file using `tee` command

‘tee’is another useful command to append any string into a file. In the
following script, the filename and the new text values are assigned like the
previous examples. If the text value is not empty, then the ‘echo’ command will
send the value to the ‘tee’ command using ‘|’ symbol. ‘-a’ option is used with
‘tee’ command here to append the received input value to the file books.txt. ‘/
dev/null’ is used in the script to prevent showing the output in the terminal.
#!/bin/bash

# Define the filename
filename='books.txt'

# Type the text that you want to append
read -p "Enter the text that you want to append:" newtext

# Check the new text is empty or not
if [ $newtext != "" ]; then
      # Append the text by using `tee` command
      echo $newtext | tee -a  $filename > /dev/null
fi
Output:
‘Learning CSS3‘ is taken as a new text value in the output that is appended at
the end of the file.

Conclusion:

Three different ways are shown in this article to append text at the end of a
file using a bash script.


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
