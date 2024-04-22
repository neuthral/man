





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


What exactly does 2>/dev/null do?

1 year ago
by Zeeman_Memon
Whether you are a new Linux user or an experienced bash programmer, it is
highly probable that you encountered the cryptic command 2>/dev/null. Although
this command looks technically complex, its purpose is very simple. It refers
to a null device that is used to suppress outputs of various commands. This
article will break down each part of the 2>/dev/null command, explain its
purpose, and see examples of how it is used.

Null Device – ‘/dev/null’

All Linux-based systems have a feature called virtual devices. These virtual
devices interact like actual files in the operating system. The working of such
virtual devices is similar to real devices; they are used to write and read
data. The main difference between the two is that the data for the virtual
devices are supplied by the operating system.
/dev/null is a null device–a special type of virtual device. It is present in
every Linux system, and the purpose of this device is to discard anything sent
to it and read the End of File (EOF). Most virtual devices are used to read
data; however, /dev/null is unique since it is used to suppress any data
written to it. In simple words, it acts as a black hole for any data that is
written to it in Linux operating systems.
Now, let us take a look at the remaining parts of the 2 > /dev/null command

File descriptor – ‘2’

Every command execution in Linux generates three associated files: standard
input, standard output, and standard error files. The Linux operating system
refers to each of these files with a unique non-negative integer.

* ‘0’ for standard input
* ‘1’ for standard output
* ‘2’ for standard error

The technical terms for standard input, standard output, and standard error
streams are stdin, stdout, and stderr, respectively.
We know that the number ‘2’ in the command ‘2>/dev/null’ refers to the standard
error (stderr) stream.

File redirection operator – ‘>’

The ‘>’ symbol is known as the file redirection operator. Its purpose is to
direct what is to its left to the commands on the right side. In simpler words,
any string of data to the left will be directed to the right side of the
operator.
So far, we have understood the purpose behind each component of the 2>/dev/null
command. It sends the error stream to /dev/null, which discards it. In other
words, this command is used to discard and suppress error outputs. However, if
you are an experienced Linux veteran, you can look at the contents of the /dev/
null file by running the following command in the terminal:
$ ls -l /dev/null
This command is typically used in scenarios where we need to filter output
based on errors or when we want to discard any output associated with erroneous
descriptions. Moving forward, we will be looking at examples of its usage on a
Ubuntu system.

Using 2>/dev/null

Since we know that the command 2>/dev/null is used to discard errors, it will
always be used in conjunction with other commands. We will see a similar
approach in the following examples. You can open the terminal either by
accessing it through the applications menu or using the keyboard shortcut Ctrl
+ Alt + T.
In the first example, we will be conducting a search in the /sys/ directory for
a random string (helloworld in this case). The command for searching is grep,
and its argument will be the search string. Enter the following command to
search for your string.
$ grep -r helloworld /sys/
This search command is bound to display numerous errors since it is being used
without root access. We will send its error stream to /dev/null by using the
command 2>/dev/null to discard these errors.
$ grep -r helloworld /sys/ 2> /dev/null
We can see that the output of the command is much neater and simpler than the
last one. The reason is that the errors are being discarded by using 2> /dev/
null, and since the grep command was unable to find any file matching our
string ‘helloworld’, it doesn’t show any output.
To understand the usage of /dev/null better, we will be looking at the
following example of pinging any website (google.com in our case). You can ping
google.com by executing the following command:
$ ping google.com
If we wish to exclude all the failed pings, we can use the 2>/dev/null command:
$ ping google.com 2> /dev/null
In this case, the standard error stream (which shows the failed pings to
google.com) is sent to the virtual device /dev/null that discards them.
However, if we wish to see only the failed pings, we can execute the following
command:
$ ping google.com 1> /dev/null
Here, we send the standard output stream (stdout) to the /dev/null device that
discards it. Consequently, we are only left with the pings that failed to reach
the google.com server. However, in our case, there were no failed pings. We can
also direct stdout and stderr to different locations. This is helpful if we
want to discard output and store errors in a log or vice versa. You can run the
following command to store the failed pings in an error log while discarding
the standard output of the ping command:
$ ping google.com 1> /dev/null 2> error.log
On occasions, you might want to suppress all output of a command (including
standard output and standard errors). We can achieve this by using the /dev/
null device in a slightly different manner. You can type the following command
to suppress all output:
$ ping google.com >/dev/null 2>&1
Note that the order of commands here is very important. After executing the
ping command, ‘>/dev/null’ tells the system to suppress the output, and ‘2>&1’
directs the standard error stream to standard output. In this way, all output
of the command is discarded.

Conclusion

We have dissected the 2>/dev/null command and simple examples in this article,
and hopefully, now you understand what each bit of it does. However, this is
just the tip of the iceberg; null devices are used in a multitude of ways in
bash programming. Some of the more advanced uses include checking file
existence, automating package installations, and avoiding scripts from running
into unwanted exceptions.


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
