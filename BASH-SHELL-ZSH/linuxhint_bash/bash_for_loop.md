





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash for loop examples

4 years ago
by Fahmida_Yesmin
Loops are a very essential part of any type of programming or scripting
languages. Like any other standard programming, loops are used in bash
programming for doing repetitive tasks. Among the three types of loops (while,
do-while, for ), for loop is very useful to do various types of iterative
tasks. The basic uses of ‘for’ loop is shown here. But ‘for’ loop can be used
for doing some advance level tasks. If you want to know more uses of for loop
then you must read this tutorial. 12 most useful examples of ‘for’ loop are
shown in this tutorial to know other specific uses of ‘for’ loop in bash.

Syntax:

for loop can be used by two ways in bash. One way is ‘for-in’ and another way
is the c-style syntax. Both syntaxes are shown below.
for variable in list
do
Statements
done
Or
for (( expression1; expression2; expression3 ))
do
Statements
done

Example-1: For loop to read input variable

List of predefined strings or array can be read easily by using ‘for’ loop
which is shown in the previous tutorial of for loop. How the content of an
input variable can be read by using ‘for’ loop is shown in this example. Create
a file named ‘forloop1.sh’ with the following script. An input value of a text
of multiple words will be taken after running the script. Here, for loop is
used to split the text into words based on white space and print each word with
the position.
forloop1.sh
#!/bin/bash
echo "Enter a text of multiple words"
read text
i=1
for word in $text
do
echo "Word No-$i = $word"
((i=$i+1))
done
Output:
Run the script.
$ bash forloop1.sh
Here, a text of 5 words is taken, so five lines of output are printed.

Example-2: For loop with a break statement

‘break’ statement is used inside ‘for’ loop to terminate from the loop. Create
a file named ‘forloop2.sh’ with the following code. ‘for’ loop is used here to
read a  list of four person’s. Two conditions are tested here. If the person
name is ‘Amir’ and the color is ‘Blue’ then the loop will terminate after
printing the person’s name and color. The color values of the second for loop
will be printed until the color value, ‘Blue’ is matched.
forloop2.sh
for name in Watson Micheal Sinha Amir Lily
do
if [ $name == 'Amir' ]
then
for color in Red Green Blue White
do
if [ $color == "Blue" ]
then
echo "The favorite color of $name is $color"
break
else
echo "The current color is $color"
fi
done
fi
done
Output:
Run the script.
$ bash forloop2.sh
The following output will appear after running the script. First, two colors,
‘Red’ and ‘Green’ are printed. When ‘Blue’ value appeared then it printed the
person’s name and color value and terminated from the loop for the ‘break’
statement.

Example-3: For loop with continue statement

‘continue’ statement is used inside the ‘for’ loop to skip any statement based
on a particular condition. Create a file named‘forloop3.sh’ with the following
script. Here, a variable named $courses is used to assign a text value. ‘for’
loop is used to read the variable, $courses. The text value will be split-ted
based on the space and read by the ‘for’ loop. When the value, ‘Oracle’ is
matched with $course then it will print ‘Oracle is not available now’. For
other values, ‘The class of $course is running’. The course that is not
available will not execute the last statement of the ‘for’ loop for the
continue statement.
forloop3.sh
#!/bin/sh
 
courses="Java PHP Oracle VB.net"
for course in $courses
do
if [ $course == 'Oracle' ]
then
echo "$course is not available now"
continue
fi
echo "The class of $course is running"
done
Output:
Run the script.
$ bash forloop3.sh
The following output will appear after running the script.

Example-4: Using command output as the list

Any bash command output can be used in the ‘for’ loop by using backtick(`).
Create a file named ‘forloop4.sh’ with the following script. Here,`ls *.txt`
command is used in the loop. This command will generate a list of the text file
from the current directory. ‘for’ loop will iterate each filename from the
command output and store it in the variable $filename that will print later.
Here, $n variable is used to display the file number.
forloop4.sh
n=1
for filename in `ls *.txt`
do
echo "File No-$n : $filename"
((n++))
done
Output:
Run the script.
$ bash forloop1.sh
The following output will appear after running the script.

Example-5: For loop to read a range

‘for’ loop can be used for reading range of data. The following example read a
range of character and search each character is exist in the text or not.
Create a file named ‘forloop5.sh’ and add the following script. Here, the
range, [A-Z] is used in ‘for’ loop. That means ‘for’ loop will iterate for 26
times for each capital letter. Each character is searched in $text by using
‘awk’ command. If any character found then it will store the value in $result.
Next. $result is checked for any content. If it is not empty then a message
will print.
forloop5.sh
text="Bash Scripting Language"
for c in {A..Z}
do
result=`printf "$text" | awk "/$c/"`
if [[ $result != "" ]]
then
echo "$c exists in the text"
fi
done
Run the script.
$ bash forloop5.sh
Here, the alphabets, ‘B’, ‘L’ and ‘S’ found in the text, “Bash Scripting
Language”. So, three lines of output are printed.

Example-6: For loop to read a range with the increment

The example shows how you can use ‘for’ loop to find out all even numbers
within a particular range. Create a file named ‘forloop6.sh’ and add the
following script. Here, a range of [2-20] is used in the loop where each step
is incremented by 2. The loop will iterate for 10 times and print the number in
each step.
forloop6.sh
echo "Printing all even numbers from 1 to 20"
for n in {2..20..2}
do
echo -n "$n "
done
printf "\nDone\n"
Run the script.
$ bash forloop6.sh
All the even numbers within 2-20 are printed after running the script.
 

Example-7: For loop to work with file

This example shows how you can ‘for’ loop to read a list of specific file.
Create a file named, ‘forloop7.sh’ and add the following script. Here, the loop
is used to the list of all text files from the current directory and replace
the file extension from ‘.txt’ to ‘.doc’.
forloop7.sh
echo "Replacing the file extension of all text file to doc file."
for filename in *.txt; do
mv "$filename" "${filename%.txt}.doc"
done
echo "Replacement is done successfully"
Output:
Create a text file first if no text file exists in the current directory. Here,
a text file named ‘newfile.txt’ is created by using `cat` command.
$ cat > newfile.txt
Run the script mentioned above.
$ bash forloop7.sh
Next, check the extension is changed or not by using `ls` command.

Example-8: For loop with sequence command

The following example shows how you can use ‘seq‘ in ‘for’ loop to print a list
of sequential number. ‘seq’ command works similarly like the range with
increment. Create a file named ‘forloop8.sh’and add the following script. The
loop will print the numbers between 1 to 30 by omitting three number each step.
forloop8.sh
echo "Print numbers by skipping 3"
for sq in $(seq 1 3 30)
do
echo "Sequence Number : $sq"
done
Output:
Run the script.
$ bash forloop8.sh
The following output will appear after running the script.

Example-9: Using infinite for loop

The infinite loop can be used to do any repetitive tasks many times until a
specific condition appears. Create a file named ‘forloop9.sh’ with the
following script to check the use of the infinite loop. Here, no termination
condition is defined in the loop. The loop displays the menu of 5 lists until
the number 5 is pressed. It will print a particular message for other numbers
from 1 to 4 and display the menu again.
forloop9.sh 
for (( ; ; ))
do
echo "1. Print success message"
echo "2. Print information message"
echo "3. Print Warning message"
echo "4. print error message"
echo "5. Exit"
echo -n "Select any number from [1-5]:"
read answer
 
case "$answer" in
1) echo "Successfully completed." ;;
2) echo "Invalid input";;
3) echo "Your computer has low battery";;
4) echo "Wrong number of arguments are submitted";;
5) exit 0;;
*) echo "Wrong selection";;
esac
done
Run the script.
$ bash forloop9.sh
Here, 9 is pressed the first time that does not exist in the list. For this
input, it is printed “Wrong selection” and display the menu again. Next, 1 is
pressed and it displayed a message, “Successfully completed”. Next, 5 is
pressed to terminate from the program.

Example-10: Using For loop without the list.

‘for’ loop can be used without any list or array or command output. How you can
use  ‘for’ loop to read command line arguments is shown in this example. Create
a file named, ‘forloop10.sh’ and add the following script. The loop will
iterate based on the number of command line arguments. $counter variable is
used to find each step of the loop that is incremented by 1 in each step.
forloop10.sh
counter=1
for text
do
if [ $counter -eq 2 ]
then
str="My favorite color is "
elif [ $counter -eq 3 ]
then
str="I love "
else
str="I like "
fi
echo "$str $text"
((counter=$counter+1))
done
Run the script with command line argument values.
$ bash forloop10.sh ice-cream blue programming
The script has printed the message, “I like ice-cream” when the $counter is 1,
“My favorite color is blue” when the $counter is 2 and “I love programming”
when the $counter is 3.

Example-11: Reading files and directories by using for loop

‘for’ loop can be used to print the list of files and folders of the current
directory. Create a file named ‘forloop11.sh’ and add the following script.
Here, ‘*’ symbol is used in the ‘for’ loop to read the files and folders of the
current directory. The loop read each file or folder name in each step and
print it in the terminal with a ‘tab’ space.
forloop11.sh
printf "Pinting the files and folders of the current Directory...\n\n"
for list in *
do
printf "$list\t"
done
printf "\n\nDone\n"
Run the script.
$ bash forloop11.sh
File and folder names of the current working directory are printed after
running the script.

Example-12: Using a comma in the bash C-style for loop

C-style ‘for’ loop is also supported in bash and this ‘for’ loop has three
expressions. These are initialization, termination condition and increment or
decrement. But using the comma(,), you can define multiple initialization
variables in bash that is shown in this example. Create a file named,
‘forloop12.sh’ and add the following script. Nested ‘for’ loop is used in this
script. Two initialization variables, $team, and $jersey are declared in the
first ‘for’ loop. The first loop will be terminated when$team will more than 2.
There is no initialization variable in the inner ‘for’ loop and the inner loop
will be terminated where the $jersey is more than 3. $jersey is set to 1 after
completing the iteration inner loop. So, the outer loop will iterate for 2
times and the inner loop will iterate for 3 times.
forloop12.sh
for ((team=1, jersey=1; team <= 2 ; team++))
do
for(( ; jersey <= 3 ; jersey++))
do
echo "Team No-$team, Jersey No-$jersey"
done
jersey=1
done
Run the script.
$ bash forloop12.sh
The following output will appear after running the script.

Conclusion:

Many effective uses of ‘for’ loop is tried to explain in this tutorial. After
practicing the above examples, hope the readers will get clear knowledge about
‘for’ loop and 0able to use this loop properly in the bash script.


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
