





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Change file permissions recursively Linux

3 years ago
by Karim_Buzdar
Linux as all other operating systems is a multi-user OS that can be accessed by
multiple users at the same time. Therefore, it is very important for the
administrators to apply proper set of permissions in order to prevent
unauthorized access and misconfigurations. Permissions define who can access
and modify the files stored in a multi-user system. Linux provides users
greater flexibility and granular control on the access permissions of its file
systems.
Normally a user who creates the file has the rights to access and change the
file permissions. Also, the root user has by default all privileges to access
every file on the system.
In this article, we will explain how to change the directory permissions
recursively in a Linux OS using the two different methods. First, we will give
a quick overview of how to view and change the file permissions, and then we
will discuss how to change the permissions recursively.

View current file permissions

To look at the current permissions of a file or a directory, run the following
command in your Terminal:
$ ls –l
For instance, if we run ls-l, we would receive a similar output:
In the above list, if the first character of a row starts with “d”, it
indicates it is a directory while if it starts with “-” indicates it is a file.
After this, the next nine characters show the permissions of the file or a
directory. These nine characters are actually grouped into three sets for the
user, group, and owner respectively. In addition, each set comprises three
kinds of permissions that are r, w and x are for “read”, “write” and “execute”
permissions respectively.

Change permissions

In Linux, to change the permissions of a file or a directory, chmod command is
used. However, to change the permission, you must be the file owner or the root
user.
The syntax is:
$ chmod [reference][operator][mode] file1 file2...
Where

* reference: whom to assign permissions e.g u (for user), g(for group), o(for
  owner).
* operator: + (add the permission), – (remove the permission), =(set only this
  permission)
* mode: what permission to assign r (for read), w (for write),x (for execute)


Changing the permissions recursively using -R

You may have noticed that if you apply permissions through the above chmod
command, these permissions are only applied to the file or directory specified
in the command. It will not be applied to the sub-directories or files within a
directory.
Chmod allows you to change the permission of multiple files and subdirectories
within a directory using the –R option as follows:
$ chmod –R [reference][operator][mode] file...
Let’s say the subdirectories under the downloads directory have the following
permissions as shown in the following screenshot.
If we view one of the subdirectory named files, it contains some files with the
following permissions.
Now let’s modify the permission of our “files” parent directory by assigning it
the write permission as follows.
$ chmod u+w files
Where U stands for “user”, the + for “add”, and the w for “write”.
After assigning the write permission, run the “ls –l” command, you can see the
new permission has assigned to the “files” directory.
However, this command only apply the permissions to the directory not the files
under it. To verify this, navigate to the files directory using the “cd”
command. Then run the “ls –l” command. You can see in the following screenshot
the permissions has unchanged.
Let’s apply the permission recursively using the following command:
$ chmod –R u+w files
It will not only apply the permission to the parent “files” directory but also
to the files under it.
Now, to verify if the permission is applied successfully, navigate to the
“files” directory using the “cd” command and then run the “ls –l” command. From
the following input, you can see that the permissions have applied successfully
to all the files under the parent directory.
In the same way, you can also recursively assign the permissions in absolute
form. For instance, to assign the read, write, and execute permission to only
the user, the following command can be used:
$ chmod –R 700

Changing the permission recursively using Find command

When chmod with –R is used to apply permission in a directory, it assigns the
same permission to all the files and subdirectories under it. However
sometimes, you may want to give separate permissions to files and directories.
An example of this would be to apply the execute permission on directory but
not on files as files do not need the execute permission. Generally, the
following permissions are assigned to the files and directories.
For directories: 755 or drwxr-xr-xx
For files: 644 or -rw-r--r--
If this is the case, to recursively assign permission to directories, use one
of the either absolute or symbolic form:
$ find /path/to/directory -type d -exec chmod 755 {} +
$ find /path/to/directory -type d -exec chmod u=rwx,go=rx {} \;
While to recursively assign permissions to files, use one of the either
absolute or symbolic form:
$ find /path/to/directory -type f -exec chmod 644 {} +
$ find /path/to/directory -type f -exec chmod u=rw,go=r {} \;
Make sure to replace the permissions with your required permission sets.
This is how you can change the directory permissions in Linux recursively. To
apply the same recursive permissions to all the file and subdirectory, use –R
option while to apply recursive permissions to file and subdirectories
separately, use the Find command.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
