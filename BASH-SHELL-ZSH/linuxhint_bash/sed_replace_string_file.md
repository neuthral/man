





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


sed Command to Replace a String in a File

2 years ago
by Aqsa_Yasin
Whenever we are working with any sort of files, it is a very common practice to
make modifications to those files by finding and replacing words. Most of the
text editors do provide different GUI based methods to perform these
modifications. However, at times, you need a way to find and replace the words
within a file via the terminal. Therefore, in this article, we will walk you
through the method of using the sed command to replace a string in a text file.
We will also throw light on the different scenarios in which this command can
be used.
Note: We will be using Linux Mint 20 for demonstrating the usage of the sed
command to replace a string in a file. You can also use any other flavor of
Linux if you wish to.

Usage of sed Command:

Now we are going to show you some very interesting examples for depicting the
usage of the sed command in Linux. Let us see, how this command works in
different scenarios.

Creating a Text File for Demonstration:

For demonstrating the usage of the sed command, we would like to work with a
text file. However, you can even create a Bash file or any other file of your
choice. Secondly, we will create the file in the Home directory so that we do
not have to specify any complex paths while accessing this file. For creating a
text file, the following steps should be performed:
Click on the File Manager icon located on your Linux Mint 20 taskbar:
Now create a new text file in the Home directory by right-clicking anywhere
over there and then choosing the New Document option from the cascading menu
and Empty document option from the sub-cascading menu. Once the text file has
been created, give a suitable name to it. For this particular example, I have
named it as sed.txt.
Double click on this file to open it and type any random text in it as shown in
the image below. Save this text file by pressing Ctrl +S and then close it.
Now launch the terminal in Linux Mint 20 as shown in the following image:
After launching the terminal in Linux Mint 20, you can go through all the
examples mentioned below one by one.

Using the sed Command for replacing all Occurrences of a Given Word:

You can use the sed command for replacing all the occurrences of a given word
in a text file. The syntax of achieving this goal is mentioned below:
$ sed ‘s/sed/FindWord/ReplaceWord/’ file.txt
Here, you need to replace FindWord with the word that you wish to replace and
ReplaceWord with the word to be replaced. Moreover, you also need to replace
“file” with the name of the file where you want to make these replacements. In
this scenario, I have replaced FindWord with sed and ReplaceWord with replace.
Our file name was sed.txt. It is also shown in the following image:
The successful execution of this command will show you the changes that have
occurred because of running this command on your terminal:

Using the sed command for replacing the nth Occurrence of a Given Word in every
Line:

The above scenario was the simplest replacement scenario, however at times, you
do not want to replace all the occurrences of a word rather you want to replace
only the first, second, or nth occurrence of that word in all the lines. For
doing this, you can execute the following command:
$ sed ‘s/FindWord/ReplaceWord/num’ file.txt
Here, you need to replace FindWord with the word that you wish to replace and
ReplaceWord with the word to be replaced. Moreover, you also need to replace
“file” with the name of the file where you want to make these replacements. In
this scenario, I have replaced FindWord replace and ReplaceWord with sed. Our
file name was sed.txt. Also, num refers to the occurrence or the position of
the word to be replaced. In the demonstrated example, I want to replace the
first occurrence of replace with sed in every line as shown in the image below:
The successful execution of this command will show you the changes that have
occurred because of running this command on your terminal:

Using the sed command for replacing a Given Word in a Specific Line:

At times, you only want to replace a given word in a specific line and not in
the whole document. For doing that, you explicitly need to specify that
particular line number in the following command:
$ sed ‘LineNum s/FindWord/ReplaceWord/’ file.txt
Here, you need to replace FindWord with the word that you wish to replace and
ReplaceWord with the word to be replaced. Moreover, you also need to replace
“file” with the name of the file where you want to make these replacements. In
this scenario, I have replaced FindWord sed and ReplaceWord with replace. Our
file name was sed.txt. Also, you need to replace LineNum with the line number
of the particular line in which you want to make the replacement. In this
example, we wanted to replace sed with replace in line number 2 of our file as
shown in the following image:
The successful execution of this command will show you the changes that have
occurred because of running this command on your terminal. You can easily
verify that the said changes have only occurred on line number 2 of our file
and not in the whole text.

Conclusion:

Whenever you feel the need of replacing any word in a file, the very first
thing you need to do is to identify your particular requirement i.e. whether
you want to replace that specific word in the whole file, or you want to
replace a specific occurrence of that particular word, or you want to replace
that word in a specific line. Once you have identified your particular
scenario, then you can use that specific method from the examples discussed in
this article.


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
