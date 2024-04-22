





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Copy List of Files Using Bash Script

2 years ago
by Karim_Buzdar
Bash (Bourne Again Shell) is the kind of shell that is for executing commands
and scripts. Bash was a developed version of the sh shell. Bash Script is a
file where multiple shell commands are scripted to perform a particular task.
In this article, we will see how we can copy multiple files using a bash
script. For this article, I am using Ubuntu 20.04 to demonstrate the example.
Note: – $USER will print current login users’ usernames.
If you are curious what version of bash shell is installed in the system, we
can check it using the following command.
$ bash --version
Bash Version Output.

Creating and Executing Bash Script

Let’s start with creating a simple file using any editor of your choice. For
me, the vi editor is more comfortable. To make the file executable, we need to
add shebang (!#) and bash interpreter location at the beginning of the script.
I have created a text.txt file and add it to bash_demo dir in my home dir that
contains some text for demo purposes.
$ touch bash_demo.sh
$ vi bash_demo.sh
Add the following lines in your text editor for a sample demo after creating a
file; if you haven’t, the editor will create a new file on write and quit.
#!/bin/bash
cp text.txt /tmp/
echo “File copied.”
We can execute the script using ./ before the script file, which determines the
current dir file.
$ ./bash_demo.sh
When we execute the script, the following error will be thrown in our terminal.
Initial execution of bash file.
When we create a file by default, the user doesn’t have execution permission
for the file. To provide execution permission to the user, the following
command must be executed.
$ chmod +x bash_demo.sh
Output after permission granted.

Copy only files from a specific directory

For fetching all the files and dir from a specific path, we will use for loop
in the script then filter out the only file using if condition. In the example
below, we execute the cp command only executed if the iterator was a file which
is determined -f flag.
#!/bin/bash
dpath = /var/log/nginx/*
for FILE in $dpath
do
if [[ -f $FILE ]]
then
        cp $FILE /home/$USER/
else
    echo “There are no files in the given path.”
fi
done

Copy all files of specific extensions

In this example, we will copy all the files with the .log extension. We need to
add *.log to the path so that iterate the only file with .log extension for
loop only.
#!/bin/bash
for FILE in /var/log/nginx/*.log
do
        cp $FILE /home/$USER/
done

Copy all Files, Including Directory

In this example, we will copy all the files, including directories,
recursively. For that, we simply need to add -R cp command where -R determines
recursively fetching of the directory.
#!/bin/bash
for FILE in /var/log/*
do
        cp -R $FILE /home/$USER/
done

Copy files from the user-specified path

In this example, we will copy files from user-specified dir. To do so, we will
use the read command to request the path from the user then check if the user
provides the path to dir or not, which is done by the -d flag in the condition.
After verifying dir, we will use a for loop to iterate all the files and dir
inside the given path, then again filter out the only files using the if
condition. If the condition matches, the following cp command will be executed.
#!/bin/bash
echo “Please provide a path to dir.”
read path
if  [[ -d $path ]]
then
for FILE in $path/*
do
if [[ -f $FILE ]]
then
        cp $FILE /home/$USER/
else
    echo “There are no files in the given path.”
fi
done
else
    echo “Path to dir is required”
fi
In my home dir, I have the following files and dir.
Output when providing the path to a file.
Output when providing dir location path.
After executing the script file, we can check the output in the predefined dir
in the script. In my case, I have copied the file in my home dir, and the
following is the result.

Conclusion

In this article, we learn about how to copy files using bash scripting. We can
use many other operations like a loop, if-else, etc. Bash scripting is more
effective when working with multiple commands to perform specific tasks. I hope
you like this article on copying files using a bash script.


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
