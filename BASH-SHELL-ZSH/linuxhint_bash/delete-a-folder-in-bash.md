





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Delete a Folder in Bash

2 years ago
by Aqsa_Yasin
While working on Linux Mint 20, you have to work on different files and
folders. But the method of creating or deleting a folder or directory to some
extent is different than creating or deleting a file. When deleting files or
directories from the command-line, be vigilant because once the directory has
been removed using the commands mentioned in this article, it will no longer be
completely recovered.
In this article, you will learn about all the basic methods to delete folders
in Bash.
There are two methods to delete the folders or directories. These are as
follows:

* Command rmdir – Used for deleting the folders or directories that are empty.

  o Remove a Single Folder
  o Remove Folder within a Folder
  o Remove Multiple Folders

* Command rm – Used for deleting the folders or directories that are not empty.

Let’s try these two methods using some examples for deleting folders.

Command rmdir

If you are a Linux user and want to delete an empty folder, you have to use the
“rmdir” command. So, at the very start, you have to check how many folders are
currently present in your home directory as follows:
$ ls

Remove a Single Folder

Firstly, make a new directory with the name “Folder1” using the following
simple command, and list all the directories again. You will see a newly
created folder in the list of directories.
$ mkdir folder-name
To remove this newly created folder, which is empty right now, use the
following command:
$ rmdir folder-name
List all the directories, and you will see that the particular folder has been
deleted and not present in the list.

Remove Folder within a Folder

List all the directories you have. Make a new directory with the name “Folder2”
using the “mkdir” command as follows:
$ mkdir folder-name
Now, make another folder, “Test1”, within a newly created folder named
“Folder2”.
$ mkdir folder1-name/folder2name
You can also make a folder within a folder by going through a “cd” command, as
shown below:
$ cd folder1-name
$ mkdir folder2-name
Now, try to remove the “Folder2” folder using the “rmdir” command. You will end
up getting an error: “Directory not empty” since “Folder2” has “Test1” in it,
which is why the “rmdir” command is unable to delete the folder “Folder2”.
$ rmdir foldername
So, you have to delete the “Test1” folder using the command below:
$ rmdir folder1-name/folder2-name
You can also try another method to delete a folder within a folder using the
“cd” command instead of folder path as follows:
$ cd foldername
$ rmdir subfolder-name
You can see the folder “Test1” has been deleted from “Folder2”.
Note: If you want to see a removal message while the folder has been deleted,
you have to use the following command along with “-v” flag:
$ rmdir –v filename

Remove Multiple Folders

To delete multiple folders at a time, you have to create multiple folders
first. So, create three folders with the name “Test1”, “Test2”, and “Test3”
using the “mkdir” command. List all the newly created folders using the “ls”
command.
$ mkdir folder1 folder2 folder3
You may use the following command to delete folders if they have different
names:
$ rmdir folder1 folder2 folder3
If your folders have different names, then try the following command to delete
them:
$ rmdir –v folder*
In this command “*” sign shows that it will pick all folders that are started
with the specific word “folder”. In the image below, all the folders having
names started with “Test” will be deleted.

Command rm

If you want to delete a folder that is not empty, then you have to use the “rm”
command. So check how many folders are currently present in your home directory
by listing them as below:
$ ls
Now, make a new folder with the name “New” and also make some other folders
within this folder as “Test1”, “Test2”, “Test3”, etc.
$ mkdir foldername
$ cd foldername
$ mkdir subfolder1 subfolder2 subfolder3
Check out the currently available folders present in your home directory.
Now, it’s time to use the “rm” command to remove the non-empty folder. For this
purpose, use the following “rm” command followed by the name of the folder to
be deleted:
$ rm –r folder-name
In this command “-r” flag refers to delete all the contents of a folder first.
You can also use capital “R” instead of small “r”. You will see that the folder
will be deleted. Not only this, but all the folders inside the folder “New” are
also removed with it.
There is another command with a slight change to remove the non-empty folder,
as shown below:
$ rm –rf folder-name
In this particular command, the “-r” flag will delete all the sub-folders or
files in this particular folder, then proceeds to a folder that needs to be
deleted. On the other hand, the “f” flag is used to forcefully delete this
folder without showing a prompt.
Or
$rm –rfv folder-name
In the above-mentioned command, the “v” flag is used to show the process of
deleting a folder with text output. It will also display a message that a
directory has been deleted successfully, as shown below.

Conclusion

To sum up, we have successfully discussed the methods on how to delete the
empty and non-empty folders in Bash using the “rmdir” and “rm” command,
respectively. We have also elaborated on how to delete empty folders with
different conditions, e.g., single folder, folder within a folder, and removing
multiple folders. Hopefully, this article has helped you a lot to cover your
basics about deleting the folders in Bash. Also, by following the above
tutorial, you can now conveniently delete files and folders in Bash.


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
