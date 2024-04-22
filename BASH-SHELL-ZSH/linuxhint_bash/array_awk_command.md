





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to use array in awk command

3 years ago
by Fahmida_Yesmin
An array variable is used to store more than one data. It is supported by most
of the programming languages to store multiple data. An array has two parts.
These are key and value. Key is used to access the location of the value. An
array can be numeric and associative. The numeric array supports only numeric
value as key and associative array supports both numeric and index value as
key. An associative array is supported by awk command. How you can define,
access or modify the associative array in awk command is shown in this tutorial
by using various examples.

Syntax:

arrayName[Key] = Value
A name has to declare for the array variable. arrayName is the name of the
array here. Every array has to use the third bracket to define the key or index
and it will be any string value for the associative array. Value can be any
character, number or string that will store in the particular index of the
array.

Example-1: Defining and reading one-dimensional array in awk

A one-dimensional array can store a single column data list. This type of array
contains a single key and value for each array element.  This array can be used
in awk command like other programming languages. In this example, an array
named book is declared with three elements and for loop is used to read and
print each element. Run the following command from the terminal.
$ echo | awk 'BEGIN {book["HTML"]="HTML Pocket Guide 2010";
book["JS"]="Effective JavaScript";
book["CSS"]="Learning Web Design";}
END{for (i in book) print "The book of ", i, " is ",book[i];}'
Output:

Example-2: Defining and reading two-dimensional array in awk

A two-dimensional array is used to store tabular data list that contains a
fixed number of rows and columns. The two-dimensional array named students is
declared in this example that contains three elements. Here, student id and
name are used as key values of the array. Like the previous example, for-in
loop is used in the awk script to print the values of the array. Run the
following script from the terminal.
$ echo | awk 'BEGIN {
students["87462,Mohammed Ali"] = 87;
students["98376,Sakib Al Hasan"] = 99;
students["79937,Musfikur Rahman"] = 88;
print "(ID,Name) => Marks";
}
END { for (i in students) print  "(", i, ") => ", students[i]; }'
Output:

Example-3: Deleting array element

Any value of the array can be deleted based the key value. Here, book array
with three elements is defined in the beginning of the script. Next, the value
of the key HTML is deleted by using delete command. The element value of HTML
key is printed before and after the delete command. Run the following command
to check the output.
$ echo | awk 'BEGIN {book["HTML"] = "HTML Pocket Guide 2010";
book["JS"] = "Effective JavaScript";
book["CSS"] = "Learning Web Design";
print "Before Delete - ",book["HTML"];
delete book["HTML"];
print  "\nAfter Delete - ", book["HTML"];}'
Output:
The output shows that the value of HTML index is empty after executing delete
command.

Example-4: Reading bash array in awk

In the previous examples, the array is declared in the awk command and iterated
by for-in loop.  But you can read any bash array by awk script. In this
example, a bash array named lang is declared in the first command. In the
second command, the bash array values are passed into the awk command that
stores all the elements into an awk array named awkArray. The values of
awkArray array are printed by using for loop.Run the following command from the
terminal to check the output.
$ lang=( "PHP"  "ASP"  "JSP" "C#" "C++" )
$ printf '%s\n' "${lang[@]}" |  awk ' { awkArray[NR] = $1} END { for
(i in awkArray) print awkArray[i], "\n"; }'

Example-5: Reading the file content into an awk array

The content of any file can be read by using awk array. Create a text file
named bird.txt with the content given below.
bird.txt
Cocktail
Quail
Gray Parrot
Baazigar
The following awk script is used to read the content of bird.txt file and store
the values in the array, awkArray. for loop is used to parse the array and
print the values in the terminal. Run the following script from the terminal.
$ awk '{ awkArray[counter++] = $1; } END { for (n=0; n<counter;n++)
 print awkArray[n],"\n"; }' bird.txt
Output:
The script prints the content of bird.txt.

Example-6: Removing duplicate entries from a file

awk script can be used to remove duplicate data from any text file. Create a
text file named fruits.txt with the following content. There are two duplicate
data in the file. These are Apple and Orange.
fruits.txt
Apple
Orange
Grape
Apple
Banana
Orange
Guava
The following awk script will read every line from the text file, fruits.txtand
check the current line exists or not in the array, arr. If the line exists in
the array then it will not store the line in the array and will not print the
value in the terminal. So, the script will store only the unique lines from the
file into the array and print. Run the commands from the terminal.
$ cat fruits.txt
$ awk '!($0 in arr) { print arr[$0],$0;  }' fruits.txt
Output:
The first will print the content of the file, fruits.txt and the second command
will print the content of fruits.txt after omitting duplicate lines from the
file.

Conclusion:

This tutorial shows the various uses of the array in awk script by using
different examples with explanation. Bash array and any text file content can
also be accessed by using awk array. If you are new in awk programming then
this tutorial will help you to learn the uses of awk array from the basic and
you will be able to use array in awk script properly.


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
