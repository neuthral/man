





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


What is Cat EOF in Bash Script?

2 years ago
by Aqsa_Yasin
The EOF operator is used in many programming languages. This operator stands
for the end of the file. This means that wherever a compiler or an interpreter
encounters this operator, it will receive an indication that the file it was
reading has ended. Similarly, in bash, the EOF operator is used to specify the
end of the file. When this operator is paired with the “cat” command in bash,
it can be used to serve various other purposes.
It is generally used either to print the text of a file in the terminal or to
copy the contents of a file to another specified location. The “cat” command,
followed by the file name, allows you to view the contents of any file in the
Linux terminal. However, instead of performing this step to view the contents
of a file, we can simply incorporate this step into our bash script to serve
the same purpose. This article shows you the usage of the Cat EOF operator in a
bash script in Linux Mint 20 with examples.

Two Cases of using Cat EOF in Bash Script in Linux Mint 20

To explain the usage of the Cat EOF operator in bash script, we have designed
two simple example scenarios using this operator in Linux Mint 20. We will be
going through these scenarios one by one.

Case # 1: Printing File Contents in the Terminal

In this scenario, we will show you how to use the EOF operator to print the
contents of a file in the terminal. For this purpose, we will first create a
bash script that will contain some sample text. When this bash script executes,
it will display the text enclosed within our bash script in the terminal.
Follow the steps provided below to print the contents of any given file in your
terminal.

Step 1: Create Bash Script

First, we will create a file named EOF.sh in our Home directory. You may choose
any other name you would like for this bash file. Also, you can create this
bash file in any directory of your choice; however, it is always convenient to
create files in the Home Directory for demonstration purposes. This saves us
the hassle of providing the file path every time we want to access it.
After creating this file, we will open the file with a text editor in Linux
Mint 20. Then, we will type the script shown in the following image in this
file. This script uses the cat << EOF-EOF block to print the contents enclosed
within this block in the terminal. We have written some random text within this
block to be printed in the terminal.

Step 2: Execute Bash Script

When our bash script is ready, we will execute it with the following command:
$ bash EOF.sh

Step 3: Analyze Output of Bash Script

After executing the command in Step 2, you will see the contents enclosed
within the cat << EOF-EOF block in your bash script in the terminal, as shown
in the following image:

Case # 2: Printing File Contents to Another File

In this scenario, we will show you how to print the contents of one file to
another file. For this purpose, we will modify the bash script that we created
in the previous scenario, Case # 1. This bash script will also contain some
sample text.
When this bash script executes, it will save the text enclosed within our bash
script in the specified file. If a file with the specified name already exists,
then our bash script will simply copy our sample text to that file. Otherwise,
the script will first create a file at the specified path, then copy the
contents to the newly created file. After executing this bash script, you can
navigate to the specified path and check the contents of the file. Follow the
steps provided below to print the contents of any file to another file using
the bash script.

Step 1: Modify Bash Script Created in Case # 1

In this step, we will simply open the bash file that we created for
demonstrating our first scenario. In that bash script, we created the variable
named “var” and equalized it to a file path, i.e., the name and path of the
file to which we want the contents to be copied. Then, we will use the cat <
$var-EOF block to enclose the sample content.

Step 2: Execute Bash Script

When our bash script has been modified, it is now time to execute it with the
same command as stated in Case # 1. However, this time, you will not be able to
see anything on the terminal as shown in the following image:

Step 3: Analyze Contents of File to which Sample Text Has Been Copied

To verify whether the desired operation has been performed successfully, first,
we will navigate to our Home Directory. In the Home Directory, we will attempt
to locate the file to which we wanted the contents of our bash script to be
copied. Once the file is located (in our case, the filename was “temp.txt”),
you can simply open it to view its contents. The content of our file is shown
in the image below, which is an exact copy of the content enclosed in our bash
script.

Conclusion

After going through the two scenarios provided in this article, you should be
able to say that you understand the basic usage of Cat EOF in a bash script in
Linux Mint 20. These scenarios provide you two different ways to use this
operator in Linux Mint 20 for printing the contents of a file or copying the
contents of one file to another.


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
