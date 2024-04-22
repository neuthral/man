





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to open the file in bash

1 year ago
by Fahmida_Yesmin
The file is used to store the data permanently and use the data in any script
when requires. A file can be opened for reading, writing, or appending. Many
bash commands exist to open a file for reading or writing, such as `cat`,
`less`, `more` etc. Any text editor can be used to open a file in bash. nano,
vim, vi, etc., an editor is used to open a file from the terminal. Many GUI
editors also exist in Linux to open a file, such as Gedit, Geany, etc. The file
can be opened for reading or writing by using bash script also. The ways to
open a file for various purposes have been shown in this tutorial.

Open file using Bash commands:

The uses of shell commands to open a file for creating or reading are shown in
this tutorial. The uses of `cat`, `less`, and `more` commands have shown here.

Use of `cat` command:

The `cat` is a very useful command of bash to create or display the file’s
content. Any file type can be created easily and quickly by opening the file
using the `cat` command with the ‘>’ symbol. Run the following `cat` command to
open a file named file1.txt for writing. If the filename already exists, then
the previous content of the file will be overwritten by the new content;
otherwise, a new file will be created.
$ cat > file1.txt
Add the following content to the file.
A bash script is a command-line interpreted language.
Many automated tasks can be done easily using a bash script.
Press Ctrl+D to finish the writing task. The following output will appear after
creating the file.
Now, run the following `cat` command to open the file.txt file for reading.
$ cat file1.txt
The following output will appear after executing the above command.

Use of `less` command:

The `less` command is used to open a file for reading only. It is mainly used
to read the content of the large file. The user can move backward or forward
through the file by using this command. It works faster than other text
editors.
Run the following command to open the file1.txt file for reading. Here, the
content of the file is very small. So when the user presses the enter key, then
the content will go upward. Press the character ‘q’ to return to the command
prompt.
$ less file1.txt
The following output will appear after opening the file using the `less`
command and pressing the enter key.

Use of `more` command:

Like the `less` command, the `more` command is used to open a large file for
reading only. This command is mainly used to read a file’s large content in
multiple pages to help the readers read long files.
Run the following command to open the file1.txt file for reading by using the
`more` command. It is a small file. So all content of the file has displayed on
one page.
$ more file1.txt
The following output will appear after opening the file using the `more`
command.

Open file using command-line editors:

The uses of vi and nanocommand-line editors for opening the file to create and
read have been shown in this part of this tutorial.

Use of vi editors:

One of the popular text editors of Linux is vi editors. It is installed on
Ubuntu by default. The user can easily create, edit, and view any file by using
this text editor. The advanced version of vi editors is called vim editor,
which is not installed by default. This part of the tutorial shows how to use
vi editor to open a file for creating and reading. Run the following command to
open the file2.txt file for writing.
$ vi file2.txt
You have to press the character ‘i’ to start writing into the vi editor. Add
the following content to the file.
Writing a file using vi editors.
You can do any of the following tasks after writing the content of the file.

  1. Type :wq to quit the editor after saving the file.
  2. Type :w to keep the file open in the editor after saving.
  3. Type :q to quit the editor without saving the file.

The following output shows that ‘:wq’ has been typed to quit the editor after
saving the file.
Run the following command to open the file2.txt file and check the content
exists or not that was added in the file.
$ vi file2.txt
The following output shows that the file contains the data that was added
before. Here,’:’ has typed to quit the editor.

Use of nano editor:

Another useful and popular editor of Linux is the nano editor that is used to
open a file for writing and reading. It is easier to use than the vi editor and
more user-friendly than other command-line editors. Run the following command
to open the file3.txt file for writing using nanoeditor.
$ nano file3.txt
Add the following content to the file.
Writing a file using nano editor.
If you type Ctrl+X after adding the content to the file, it will ask you to
save the file. The following output will appear if you press the character,
‘y’. Now, press the enter to quit the editor after saving the file.

Open file using GUI text editor:

The ways to use gedit and geany GUI-based text editor have shown in the part of
this tutorial.

Use of gedit editor:

The gedit is mostly used GUI-based text editor that is installed by default on
maximum Linux distributions. Multiple files can be opened by using this editor.
Run the following command the open the existing file1.txt file using
gediteditor.
$ gedit file1.txt
The following output will appear after executing the command.

Use of geany editor:

Geany is a more powerful GUI-based editor than the gedit editor, and you have
to install it to use it. It can be used to write code for many types of
programming languages. Run the following command to install the geany editor.
$ sudo apt install geany
After installing the editor, run the following command to open the file1.txt
file.
$ geany file1.txt
The following output will appear after executing the command.

Conclusion:

Many ways to open a file for reading or writing have been shown in this
tutorial by using bash command, command-line editors, and GUI-based editors.
The Linux users can select any of the ways mention here to open a file in bash.


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
