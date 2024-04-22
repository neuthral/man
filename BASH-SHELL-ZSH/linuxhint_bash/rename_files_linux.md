





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Rename a Batch of Files in Linux with the rename Command

3 years ago
by Sidratul_Muntaha
Need to rename a file from the command line? Most of the time, using the mv
command is more than enough to do the job. However, when you need to rename
multiple files or a group of files, using mv is a very difficult job.
This is where the rename tool comes in. Every Linux system comes up with the
rename tool built-in. The rename tool supports a wide range of features, for
example, rename group of files, rename to lowercase/uppercase, even overwrite
files but most of all, controlling the behavior using Perl expression!
Let’s have a look at how to rename a batch of files with the rename command.

Rename usage

The rename tool requires Perl installed to perform. It’s a part of Perl.
Generally, it’ located under /usr/bin.
$ which rename
The command structure of the rename tool is as follows.
$ rename 's/<old_name>/<new_name>/' <files>
Rename also supports a handful of optional arguments. However, the Perl
expression must be present because that’s what rename follows when performing
the actions.
$ rename [-v] [-n] [-f] <perl_expression> <files>
Here’s what those arguments mean.
-v: Echo file names that have been successfully renamed
-n: What file would have been renamed
-f: Force overwrite

Renaming files

For demonstration, I’ve created a bunch of demo text files with the file
extension “.txt”.
Let’s rename the file extension of all these files into “.random”.
$ rename 's/\.txt$/\.random/' *.txt
Check out the result.
Here, there are 2 parts of the argument. The first one is a Perl expression and
the second one tells rename which file to operate on.

File(s) to be renamed

There is an interesting function rename offers. Instead of renaming, you can
check out which file(s) will be renamed if the operation was run for real. For
this purpose, use the “-n” flag.
$ rename -n 's/\.txt$/\.random/' *.txt

Check file name changes

Want to see rename to display output as it performs its actions? Use the “-v”
flag. The behavior is quite similar to the “-n” argument. In this case,
however, it actually performs the renaming of the file.
$ rename -v 's/\.txt$/\.random/' *.txt

Renaming lowercase to uppercase and vice-versa

In some situations, you may want to batch rename the files from lowercase to
uppercase or, uppercase to lowercase. To change the case of the target file
names, let’s use the following commands.
The game here is the Perl expression. Run the following command for turning all
the lowercase characters of the file names into uppercase.
$ rename -v 'y/a-z/A-Z/' *.txt
Note that even the file extension will be changed to uppercase. To change from
uppercase to lowercase, run the following command.
$ rename -v 'y/A-Z/a-z/' *.TXT

Rename with the capitalized first letter

To make only the first letter of the file name to be capital, use the following
command instead.
$ rename 's/\b(\w)/\U$1/g' *.txt

Overwriting existing file(s)

In certain situations, renaming the files will conflict with the pre-existing
file(s) in the same directory. If you want to overwrite the old file(s) with
the new one, then add the “-f” argument to rename.
$ rename -f -v 'y/a-z/A-Z/' *.txt
Note that in this situation, the file permission comes into play. If you don’t
have permission to operate on those files, it won’t succeed.

Final words

The functionality of the rename command is quite simple. It’s not a complex
tool itself. However, the true magic hides in the power of Perl expression.
It’s only up to you how you want rename to perform. No matter whatever crazy
expression you come up with, rename got your back.
If you want to know all the available options for rename, check out the help
page.
$ rename --help
For full in-depth info, check out the man page.
$ man rename
Perl expression is also at the core of sed, another really powerful tool that
can perform insane text edits. Learn_more_about_sed. Here’s another sed_guide
that implements this tool into bash.
Enjoy!


About the author


Sidratul Muntaha

Student of CSE. I love Linux and playing with tech and gadgets. I use both
Ubuntu and Linux Mint.
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
