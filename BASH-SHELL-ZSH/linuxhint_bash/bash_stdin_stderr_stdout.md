





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


What are stdin, stderr and stdout in Bash

3 years ago
by Sidratul_Muntaha
Whenever running any command in the terminal, stdin, stderr, and stdout are
three data streams that bash creates. If you’re familiar with the command line,
you may already have taken advantage of these features. Essentially, they allow
piping/redirecting data from one command to another.
Let’s check out how stdin, stderr, and stdout works and how you can use them as
well.

stdin, stdout and stderr

In computing, the term stream refers to something that can transfer data. Here,
all three streams carry text as the data.
Similar to water streams, data streams also have two endpoints. There are a
source and an outflow. Whatever command you’re running in the terminal will be
at either point of the stream. Using the stream, you can connect two terminal
windows, two different commands, and even files!
Let’s have a quick breakdown of the special streams.

* stdin: Stands for standard input. It takes text as input.
* stdout: Stands for standard output. The text output of a command is stored in
  the stdout stream.
* stderr: Stands for standard error. Whenever a command faces an error, the
  error message is stored in this stream.

In Linux, almost all the streams are treated as if they were files. Just like
you can read/write a file, you can read/write data from these streams.
An easy way to access any file is by using the unique file descriptor number
associated with it. In the case of these streams, there are unique values
assigned to each one of them.

* 0: stdin
* 1: stdout
* 2: stderr


stdin, stdout, and stderr in action

Let’s get started by learning more about these streams through action, we will
start with stdin.
Run the following command.
$ read
The command will require input from the keyboard. Here, the read tool is
getting the input from stdin.  Now let’s look at stdout.
Run the command first.
$ ls -l
Here, the ls command lists the file(s) in the current directory. The list is
sent to stdout and the terminal prints it out.  Let’s check stderr now.
There are different ways an error may occur. For this example, sending ls an
invalid argument will result in an error.
$ ls -l anything
Here, there’s no file named anything. That’s why the message ls returns is sent
to stderr.

Piping

This is a common technique that takes full advantage of the stdin and stdout
streams. Let’s explain it with an example.
$ echo "hello world" | grep hello
Here, the | sign is responsible for piping. The output echo generates is
written in the stdout stream. Then, the piping redirects the content of stdout
to stdin for the grep command. That’s how grep knows what content to perform
the operation on.
If you want to pipe both the stderr and stdout to the next command, then use
the “|&” instead.
$ echo “hello world” |& cat
$ anything |& cat

Redirecting streams

Now we know how these streams work, let’s have a look at how you can redirect
them. Piping is a form of redirection. However, it only involves stdin and
stdout. Bash allows specific control over all three of the streams.
To redirect the stdout content to a file, add the “>” angle followed by the
target file name.
$ echo “hello world” > hello.txt
Here, the output of the echo command will be stored in the hello.txt file.
If the file did already exists, then the command above will overwrite it. To
avoid it, make sure that the file name is unique. If you don’t want to
overwrite, you may want to use “>>” instead. It appends the output at the end
of the target file.
$ echo "hello world" >> hello.txt
The goal of stdin is to work with input. This can also be redirected. For
example, instead of typing the input from the keyboard, it can be loaded from a
file.
In this command, cat will take its input directly from the hello.txt file.
$ cat < hello.txt
Let’s check out the redirection with a different example. This time, it’s going
to involve a Python script.
$ # pyin.py
$ name = input("Enter name\n")
$ email = input("Enter email\n")
$ print("Your name is %s and email is %s" % (name, email))
The input for the script is located at hello.txt.
$ cat hello.txt
Let’s send the file as input for the script.
$ python3 pyin.py < hello.txt
Interestingly, you can redirect both stdin and stdout in the same command line.
Here, the following command will use hello.txt as stdin and send the stdout of
the command to a file.
$ python3 pyin.py < hello.txt > output.txt
Redirecting stderr is similar to stdout. However, you need to mention the
description ID 2 for indicating stderr. Otherwise, it’ll just use stdout.
Here, I’ll be redirecting the content of the stderr to a text file.
$ anything 2> error.txt

Redirecting Stdout and Stderr

Yes, it’s possible to redirect both of them simultaneously. All you need is to
mention the description ID 1 and 2 before the redirection.
$ echo “hello world” 1>output.log 2>debug.log

Final thoughts

stdin, stdout, and stderr are wonderful features bash offers by default. If
you’re into bash scripting, using them can be incredibly useful in tricky
situations.
Want to learn more about bash scripting? Let’s get started with this beginner’s
guide_to_bash_scripting!
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
