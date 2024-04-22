





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


String concatenation in bash

4 years ago
by Fahmida_Yesmin
The way of joining two or more strings together is called string concatenation.
It is a common requirement of any programming language. A specific character or
built-in function is used to do the concatenation operation in the standard
programming language. But, there is no built-in function in bash like other
languages to combine string data or variables. The string data can be combined
easily in bash by placing one after another or by using shorthand operator. How
string concatenation can be done in bash is shown in this tutorial by using
several examples.

Example-1: String variables one after another

The most simple way to join two or more strings together is to place the
strings one after another. Create a file named ‘concat1.sh’ and add the
following code to combine strings. Two variables, $string1 and $string2are
initialized with string data and stored in another variable, $string3. The
value of $string3 is printed by combining another string data.
concat1.sh
#!/bin/bash
#Declare first string
string1="Welcome"
#Declare second string
string2=" everyone "
#Combine first and second string
string3=$string1$string2
# Print the third string by combining with other string
echo "$string3 to our site"
Output:
Run the script by bash command.
$ bash concat1.sh
The following output will appear after combining all data.

Example-2: String variable after and before the string data

The string variable can be added in any position of the string data. Create a
file named ‘concat2.sh’ and add the following code. Here, a string variable is
initialized and printed by adding the variable in the middle of the other
string.
concat2.sh
#!/bin/bash
#Declare string variable
string="Programming"
#Add the variable in the middle of the string
echo "Bash $string Language"
Output:
Run the script by bash command.
$ bash concat2.sh
The following output will appear after executing the script.

Example-3: Using shorthand ‘+=’ operator to combine string

Another way of concatenating string data in bash is by using shorthand (+=)
operator.  Create a file named ‘concat3.sh’ and add the following code to check
the use of shorthand operator.  Here, the shorthand operator, ‘+=’ is used
inside a ‘for’ loop to combine the elements of a list. At first, $food variable
is initialized with an empty string. ‘for’ loop is used to read a list of four
elements. Each value of the list will be combined with each other serially with
a space in each iteration of the loop. The values are stored in the
$foodsvariable. In the last statement, the value of $foods is printed.
concat3.sh
Output:
Run the script by bash command.
#!/bin/bash
echo "Printing the list of foods"
#Initialize the variable before combine
foods=""
#for loop for reading the list
for value in 'Cake' 'ice-cream' 'Burger' 'Pizza'; do
#Combine the list values by using shorthand operator
foods+="$value "
done
#Print the combined values
echo "$foods"
Output:
Run the script.
$ bash concat3.sh
The following output will appear after executing the script.

Example-4: Combine using literal strings

The literal string variable can be used to combine with other string data.
Create a file named, ‘concat4.sh‘ and add the following code. Here, $string
variable is used to store string data and it is used as a literal string in
`echo` command to print.
concat4.sh
#!/bin/bash
#Declare a string variable
string="Learn bash programming "
#Print the string variable as literal
echo "${string} from the basics"
Output:
Run the script by bash command.
$ bash concat4.sh
The following output will appear after executing the script.

Example-5: Combine strings with any particular character

Any particular character can be added inside to combine two or more strings
data.  This type of task is required when you need to add a separator among the
string data. Each string value can be separated easily later if they are
combined by a specific character. Create a file named, ‘concat5.sh‘ and add the
following code. Here, three string data are taken as input at the beginning of
the script. The values are assigned in three variables, those are $name,
$address and $phone. These variables are combined with a character “:”and
stored in $combinevariable. This variable is redirected to a file named
‘customers.txt’ to append the values of $combineto the file. If the file does
not exist then the file will be created and the value of $combine will be added
at the beginning of the file. If the file exists the value of $combine will be
added at the end of the file. If you want to extract the values from this data
then you have to use the ‘:’ character to separate each part from the data.
concat5.sh
#!/bin/bash
# Taking first input
echo -n "Enter customer's name: "
read name
#Taking second input
echo -n "Enter customer's address: "
read address
#Taking third input
echo -n "Enter customer's phone: "
read phone
#Store the values  by adding ‘:’ between two variables
combine="$name:$address:$phone"
 
#Write the combined values into a file
echo "$combine" >> customers.txt
Output:
Run the script by bash command.
$ bash concat5.sh
View the file,customers.txt to check the data is properly added to the file or
not.
$ cat customers.txt
The following output will appear after executing the above commands.

Conclusion

String concatenation requires in the programming language to generate
meaningful output. The output of the script needs to be formatted by combining
data properly. All possible ways of combing strings in bash are tried to
explain in this tutorial. Hope, the users will be benefited after practicing
this tutorial and able to combine strings properly in the bash script.


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
