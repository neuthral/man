





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Search for your Files on the Linux Command Line

4 years ago
by Zeeman_Memon
For a Linux desktop, a user can easily install an app to search their files and
folders in the file system, but another way is via command line. Anyone who has
been working on the command line would find this method much easier as compared
to others. This article will guide you on how to use the find command, so you
can search for files with the help of various filters and parameters.
The best way to locate your files on a Linux desktop is with the help of Linux
Command line as it provides various other options to search for the file which
is rarely provided by the graphical tool.


What is Linux find command:

A command that is used to recursively filter objects on a basis of the
conditional mechanism is known as find command. The find command in a Linux
system is a powerful tool and can be used easily to find different files. The
files can be searched based on name, size, date, permissions, type, ownership
and more.

The syntax of Linux Find Command:

Before understanding the usage of find command let’s review the syntax of Linux
find command. Find command takes the following form:
find [options] [path...] [expression]

* The options attribute controls the optimization method and behavior of the
  searching process.
* The path attribute defines the top directory where the search will begin.
* The expression attribute will control the actions and search patterns
  separated by operators.

Let’s see this how this works.

Find by Name:

As already explained the simple structure of command would include an option, a
path and an expression which would be the file name itself in case you are
searching by name. It gets a lot more easy and efficient if you know the path
of the search as you would have an idea of where to start locating your
particular file.
The next part of the command is an option. In case of Linux command line, there
is a number of options to choose from. But starting from the beginning let’s
choose an easy one. In this case where we are searching for a file by its name
two options can be used:

* name for case sensitive,
* iname for case insensitive.

For example, if you are searching for a file named abc.odt, you would have to
use the following command to get the appropriate results.
find / -iname abc.odt
This means to search for a file by its name and ignore the case.
However, if you use the -name option with this file you will get no results.

Find by Type:

This would be helpful in case you want to search a number of files of a
particular type. So, instead of searching for a separate file each time by its
name you can easily search them all by their type. Following are the most
common types of file:

* f for a regular file,
* d for the directory,
* l for a symbolic link,
* c for character devices,
* b for block devices.

Now, for example, you want to search a directory file on your system with the
help of -type option. So, type this command as:
find / -type d
You can also use the same command to search for configuration files. For
example, to search for files with an extension of .conf your command would look
like the following:
find / -type f -name “*.conf”
This command would give you all the files ending with an extension of .conf.

Find by Size:

When your drive is mysteriously filled by some unknown file which you are
unable to identify, then you can find that file by using the -size command.
This would help you to make some space in your drive quickly. For example, you
want to search files that are above 1000MB. Then the find command would be
typed as:
find / -size +1000MB
The result might be surprising. You can, later on, free up space by deleting
the file that is taking more space. Following are some of the size
descriptions:

* c for bytes,
* k for Kilobytes,
* M for Megabytes,
* G for Gigabytes,
* B for 512byte blocks.

Take another example, if you want to search all files with the exact size of
1024 bytes in /tmp directory, then the command would be typed as:
find /tmp -type f -size 1024c
You can also locate the files less than or greater than a specific size. For
example, to search for all the files that are less than 1MB you have to type
minus – symbol before the value of size. The command would become:
find . -type f -size -1M
To locate the files that are greater than 1MB you have to type plus + symbol
before the value of size. The command would be:
find . -type f -size +1M
To search the files in between two size ranges for example between 1 and 2MB,
the command would go as follows:
find . -type f -size +1M -size 2M

Find by Permission:

When you want to find the files on the basis of file permission, use the option
of -perm.
For example, to search for the files with permissions of 775 exactly in the
directory /var/www/html the following command would be used:
find /var/www/html -perm 644

Find by ownership:

When you want to locate a certain file owned by any user or group then you can
use the option of -user and -group. For example, to find the files owned by the
user linuxadmin, then the command would be:
find / -user linuxadmin
Take an advance example, to find the files owned by user linuxadmin and change
the ownership of those files from linuxadmin to newlinuxadmin. Command for this
would be:
find / -user linuxadmin -type f -exec chown newlinuxadmin {} \;

Find to Delete:

If you want to delete the files that you have searched add -delete at the end
of the command. Before you do this, make sure that your searched result are the
files that you want to delete.
For example, to delete the files with an extension of .temp from the /var/log/
the following command would be used:
find /var/log/ -name `*.temp` -delete

Conclusion:

The fundamental knowledge of powerful find command would help you to locate
your files on Linux system easily. The above guide showed the number of ways
through which you can find your file in the Linux system.


About the author


Zeeman Memon

Hi there! I'm a Software Engineer who loves to write about tech. You can reach
out to me on LinkedIn.
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
