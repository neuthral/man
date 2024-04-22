





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Remove Last x Characters From String

1 year ago
by Aqsa_Yasin
One might have to delete letters from either a string sometimes. Just what the
case may be, Linux includes several built-in, useful tools for removing letters
form such a text in Bash. This article demonstrates how to delete letters from
either a string using those methods. In this post, the instructions were run on
Ubuntu 20.04 Focal Fossa. The very same instructions may be run on any Linux
system that has the utilities mentioned above installed. To execute the
instructions, we’ll utilize the usual Terminal. The Ctrl+Alt+T shortcut will
open the Terminal tool.

Method 01: Substring Way

Our first method to remove letters or characters from a string is more like
creating a substring from an original one. Meanwhile, the terminal has been
opened already; we will make a bash file to add our bash code. So that we can
do character removal or substring making in it. So, we have used the built-in
touch instruction in our shell to create a bash file.
As the file has been quickly generated in the home folder of Ubuntu 20.04, open
it in some editor to edit. So, we choose GNU editor to open the file.sh
document as below.
Copy the code shown below in it. This code contains bash extension at the
start, and after that, we have declared a string variable “val” with a string
value. At the other line, we use the “echo” phrase to display this variable in
the terminal. The real task begins from here. We have initialized a variable
“new” and assign it a value which is a substring of the original variable
“val”. We have done it by mentioning “-14” in the braces after double colons.
This tells the compiler that it has to remove the last 14 letters from the
original string “FirstWorldCountries”. The remaining letters will be saved into
the variable “new”. In the last line, the “echo” has been used to print the new
variable “new”.
The proper execution of a file “file.sh” using the “bash” command comes out as
expected. Firstly, it displays the value of the first string variable “val”,
and after that, It displays the value of the newly created string from a first
variable as per shown output.

Method 02: Using Special Symbols

Another simple and easier method to remove the last letters or characters from
any string is via the special symbols or characters, e.g., percentage and
question mark symbols. So, this time we will be using percentage and question-
mark to remove the characters from any string. Hence, we have already opened
the same file to update the bash script using a “GNU Nano” editor. Overall code
is the same, but the variable “new” part is a little different. We have used a
percentage sign to let the system know that the mentioned numbers of question
marks represent the number of characters from a variable “val” to be removed
after this percentage sign. You can see we have added 9 question mark symbols.
This means the last 9 characters from the string “FirstWorldCountries” will be
removed, and the remaining string will be “FirstWorld”. This remaining string
will then be saved to a variable “new”.
When we have executed the updated bash file, the output comes as anticipated.
It shows the original string from the first variable and the value of the
second variable, “new” which has been created from the variable “val”.

Method 03: Using Sed

Sed is a useful and effective tool for altering text sequences. That’s a non-
interactive development environment that lets you work with data input and do
simple text transformations. You may also use sed to delete letters from texts
that you don’t want. We’ll use an example string and route it into the sed
command for illustration purposes. You may delete a particular character from
some kind of string with sed. So, we have used the simple line of a string
within the echo statement. We have used “sed” to remove the letter “A” from the
mentioned string. Make sure to follow the syntax ‘s/string_to_be_removed//’.
The output shows the letter “A” has been removed.
To remove the whole word “Aqsa” we have mentioned the first and last character
of a word with the dots within to represent missing letters. The output shows
the string with the removal of the word “Aqsa”.
To remove any number of last characters from a string, mention the number of
dots as per your requirement before the dollar symbol as shown.

Method 04: Using Awk

Awk is a sophisticated scripting language that may be used to match patterns
and process texts. You may use Awk to shift and modify input in a variety of
different ways. You may also delete letters from strings using awk. Awk seems a
little different from “sed”. This time we have changed the string with “Aqsa
Yasin”. The awk function will make substring via the substr method and print it
in the terminal. The function length has been used to demonstrate the number of
letters removed from the mentioned string. Here, “length($0)-5” means to remove
the last 5 characters of a string, and the remaining will be a part of a
substring to be printed out.
We have tried to remove the last 9 characters from a string “Aqsa Yasin” and
got “A” as the output substring.

Method 05: Using Cut

Cut seems to be a command-line utility for extracting a piece of text from such
a phrase or document and printing it to standard output. This operation can
also be used to remove letters from some kind of string. We’ll use an example
phrase and pass it to the cut instruction for testing purposes. So we have used
the “Aqsa Yasin” phrase and passed it to the “cut” query. After the flag –c, we
have defined the range of indexes for a string to cut the characters from a
string mentioned. It will show the characters from index 1 to index 5. Index 5
has been excluded here. The output shows the first 4 characters as “Aqsa”.
This time we will use the cut instruction differently. We have used the “rev”
function to reverse the string. After the reverse of a string, we will be
cutting the first character from a string. The flag “-c2-“means our substring
will be onward character 2 . After that, the reverse function is again used to
revert the string. So, this time we got the original string back with the
removal of the last character.
To remove the last 7 characters, you just have to mention “-c7-“in the cut
command while using the reverse function as well.

Conclusion:

There is time more than one method to do a basic task on Linux. Similarly,
deleting characters out of a text is possible. This article demonstrated five
distinct methods for eliminating undesired characters out of a string, as well
as some instances. Whatever tool you choose is entirely dependent on your
choice and, more crucially, what you’d like to accomplish.


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
