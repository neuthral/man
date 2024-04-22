





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Find Files Case-Insensitive in Linux

2 years ago
by Aqsa_Yasin
If you have a large bulk of files in your computer system, it is very important
to keep them organized so that you can easily access the files whenever you
want. If you have a busy schedule, you may simply keep dumping files onto your
computer system without even knowing where a particular file is located. In
this situation, it can get very difficult to work, especially when you need a
specific file immediately.
The Linux operating system provides you with multiple commands that you can run
in the terminal to find a specific file. Although, most of these commands are
case sensitive, meaning that you need to know the exact name of your file and
whether it is in lower-case or upper-case letters or a combination of both. If
you do not know which letters are capitalized in the file name, then it would
not be possible to locate the file that you need with these commands.
There is a method that can be used to make a file search case insensitive using
certain flags in the command-line interface. This article shows you how to
perform a case-insensitive file search in Linux Mint 20.

Method for Finding a File Case-Insensitive

For this method, we will use the “find” command. To find a file case-
insensitive in Linux Mint 20, perform the following steps:
Click on the terminal icon in the taskbar to initiate the Linux Mint 20
terminal. This can be seen in the following image:

For the sake of demonstration of the “find” command, we will try to find the
file named “Cron.sh” in our Home directory.
This file is highlighted in the following image:

The “find” command is case-sensitive by default. This means that if you have a
file with a name that is in all caps, then you will need to write the file name
in caps while looking for it using the “find” command. You can verify this by
running the “find” command in the following manner:
$ find . –name cron.sh
Here, we have intentionally named our file “cron.sh” instead of “Cron.sh” to
see whether the “find” command ignores the case and manages to search for the
file with the simple “-name” flag.

You can see that the “find” command failed to look for our specified file with
the simple “-name” flag, which proves that the “find” command is case-
sensitive.

We can make this command case-insensitive by using the “-iname” flag with the
“find” command, which ignores the case of the file name and only focuses on the
initials. We can modify the “find” command to make it case-insensitive in the
following manner:
$ find . –iname cron.sh

After running the above command, we were easily able to find our file named
“Cron.sh,” since we used this command with the “-iname” flag. You can see the
output of this command in the image below. Since our file “Cron.sh” was located
in our Home directory, instead of showing any path on the terminal, our system
only displayed the exact name of our file in the terminal.

To make the scenario a little bit more complex and to test the effectiveness of
the “find” command with the “-iname” flag, we will try to look for a file that
is located within a directory inside the Home directory. The directory named
Directory1 is located in our Home directory. In this directory, we have a file
named “D2.txt.” This file is shown in the image below:

Now we will try to look for this file using the “find” command in the following
manner:
$ find . –iname d2.txt
Again, we have intentionally named our file as “d2.txt” instead of “D2.txt” to
check if our “find” command works correctly or not.

From the output of this command, you can see that the command has managed to
correctly find the specified file. The command has also displayed the correct
file path, along with the correct name, as shown in the image below:

To complicate the scenario even more, we created the subdirectory named
Directory2 inside of the directory named Directory1. We also created the file
named “AbCdEf.txt” in the directory named Directory2, as highlighted in the
following image:

We will now try to look for this text file. Since the name of this file
includes a combination of both the upper case and lower case letters,
therefore, this file name will be best for testing the effectiveness of the
“find” command. We will look for this file by running the “find” command in the
manner shown below:
$ find . –iname abcdef.txt
You can see from the command shown above that we wrote the name of our file
only in lower-case letters to check whether the “find” command is working
correctly.

The output of this command showed the correct path of our file named
“AbCdEf.txt,” along with its correct name, as shown in the following image.
Hence, it has been verified that the “find” command becomes case insensitive
when paired with the “–iname” flag.

Conclusion

By following the method explained in this article, you can perform a case-
insensitive search for any file in your Linux Mint 20 system, regardless of
where that file resides. To emphasize this point, we showed you multiple
scenarios with varied locations of the files that we tried to look for using
the command-line. You witnessed in all these scenarios that our method worked
perfectly well. You can use this method yourself to find any file, case-
insensitive, in your Linux Mint 20 system.


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
