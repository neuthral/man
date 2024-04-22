





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Check If a Path is a Directory or Something Else in the Bash Script

1 year ago
by Aqsa_Yasin
We are attempting to develop a very basic Ubuntu script that will enable us to
provide the information, whether it’s a filename or perhaps a folder. How can I
verify if a folder exists inside a shell script underneath Linux or Unix-like
virtual machines? Or how do I see if a file exists? How will a user distinguish
if the mentioned path is a directory or a file? So, let’s have some examples in
a Bash script to elaborate on this concept. Make sure to log in from your
system first. We are utilizing Ubuntu 20.04. After the login, open your console
application to get examples done.

Example 01:

For the opening of the shell, try “Ctrl+Alt+T”. Creating a bash file first
starting with a simple example of checking if the path mentioned in a bash file
is a file or directory. To create a bash code file, type “touch” in the
terminal while mentioning the name of a file with the “.sh” extension. So, we
have named the file “test.sh”. Hit the key “Enter” to process the query.
$ touch test.sh
You can easily find the just-created bash file within the home directory. To
add a bash code to it, we need to open it in some editor. So, we have been
utilizing a built-in GNU editor of Ubuntu 20.04. Hence, we have tried the query
underneath in a shell and opened it in an editor.
$ nano test.sh
The file has been launched in an editor. Write out the script shown below in
it. Firstly, add the bash extension in the file as “#!/bin/bash”. We have
declared a new variable “v1” and assigned it a “path” of a file as its value.
It is clear from the path that it indicates some bash files. The “if” statement
has been initialized. Inside the braces [], we have to use the flag of “-d”
representing the directory within its condition part. It will check whether the
mentioned variable value is a directory or something else. If the condition
meets, it will execute the “then” part and display “$v1 is a directory”.
Otherwise, it will be executing the else part of the “if” statement and
displaying “$v1 is a file” at the shell terminal. The “fi” states that the “if”
statement has been ended here. After saving this bash code, we will be back to
the console via “Ctrl+S” and “Ctrl+X” consecutively.
Now the time is to execute the bash file “test.sh”. Therefore, we have used the
bash instruction in our console with the file’s name to check out the output.
The output for this instruction shows that the path mentioned in the file is
specifying a file. Hence, we can say that the “else” part must have been
executed his time.
$ bash test.sh

Example 02:

Let’s see the result for a directory this time. This time, we will see how the
flag “-d” works on a variable containing a path for a directory. So, we have
opened the file “test.sh” again in the editor via the “nano” query in the
shell.
$ nano test.sh
After opening it, we have updated the value of variable “v1” and changed the
path to a directory path. We have replaced the file “file.sh” with a directory
“Pictures/”. The remaining bash script is the same all over the file in an
editor. You have to simply and quickly save the updated bash code and exit the
editor using “Ctrl+S” first and then “Ctrl+X” after that.
So, let’s execute our file again. For execution, the same above query has been
utilized in the console. This time the execution shows that the mentioned path
in the bash script is a directory within the home directory of Ubuntu 20.04.
$ bash test.sh

Example 03:

In the above two examples, you have seen how to use a “-d” flag to see if the
mentioned path variable is a directory or not. This time, we will utilize
another flag, “-f,” in our example specifying if the mentioned path is a file
or not. On the other hand, we will be using a nested “if-else” statement in our
bash code to use the “-d” and “-f” flags. We have opened the “test.sh” file in
GNU editor via the terminal using the “nano” instruction once more.
$ nano test.sh
After opening the bash document, we have written the below-shown bash script
within it. Added the bash extension and initialized a variable v1, containing a
file path as its value. Moreover, the nested “if-else” statement has been
utilized properly to check whether the path of a variable is a file or a
directory. So, within the first, if statement, we have mentioned a condition to
check whether the variable value is a directory via the “-d” flag. If the
condition meets, it will print “$v is a directory”; otherwise, the other part
of a statement will be compiled. Within the “else” part, there is another “if-
else” statement mentioned. Within the “if” part of this statement, the
condition has been used to check whether the variable path “v” contains a file
or not via the “-f” flag. If the path contains a file, it will print that “$v
is a file”; otherwise, the “else” part echo statement will compile at the
terminal.
After the code has been saved, this is a time to compile the bash script via a
bash query. Therefore, we have used the “bash” query with the file name
mentioned within it. The output is as same as we have expected. As the variable
value contains the path that specifies the file path, it displays that the “$v
is a file”.
$ bash test.sh

Example 04:

In the above-illustrated example, we have used the path for a file to see how
the nested “if-else” statement reacts while using the flags “-d” and “-f”. This
time we will use the directory path. Open the file once again and update the
variable path value. We have replaced “test.txt” with “Documents/”. The
remaining script is the same.
Upon successfully compiling a bash script, the declared path in variable value
“v” is a directory, e.g., Downloads.
$ bash test.sh

Example 05:

The last and bonus example is for extra practice. Open the new file “file.sh”
and fill it with the below code. Two variables have been declared to show the
file and directory path consecutively. The “if-else” statements have been
utilized with the “-d” flag to specify the path type, e.g., directory or file.
Once the code has been compiled, the first variable contains a file, and the
second contains a directory as per the below output.
$ bash file.sh

Conclusion:

In this guide, we have seen how to find that the mentioned path is a file, a
directory, or something else. We have used “if-else” and nested “if-else”
statements while utilizing “-d” and “-f” flags in our examples to elaborate
better.


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
