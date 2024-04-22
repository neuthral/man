




















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


15 Interesting awk Commands

4 years ago
by Mokhtar_Ebrahim
This article will run you through some interesting awk commands and when to use
them. Read on to find out!


Introduction to awk

AWK is a popular language in UNIX and Linux. It got its name from its authors:
Alfred Aho, Peter Weinberger, and Brian Kernighan. The awk command allows
access to the AWK programming language, which is designed to process data
within text streams.
Popularly used for scanning patterns and simplifying complex operations, awk
helps you write effective statements for defining text patterns in a file. The
awk command then processes these statements by reading one line at a time and
takes an action based on the condition given.
Simply put, awk finds and replaces text, and helps sort, validate, or index the
given data.

Features of AWK

awk comes with a lot of unique features:

  1. No compilation is necessary in awk
  2. Often used for data extraction
  3. Commonly used for performing text manipulation
  4. Helps generate results as needed.

Now let’s explore the power of the awk commands.

15 Interesting awk Commands

Here’s a compiled list of some interesting awk commands:

  1. Printing random numbers in a set – Suppose you want to print a few random
     numbers from a selected pool. You can specify the quantity of random
     numbers from this pool and ask awk to print this. Here’s an example: let’s
     print 10 numbers from 0 to 1000. So the awk command for this will be as
     follows:
     awk 'BEGIN { for (i = 1; i <= 10; i++)
     print int(1001 * rand()) }'


  1. Searching for foo or bar – What if you want to write a line in which you
     want to perform a simple search for foo or bar? Here’s a command that will
     allow you to do just that:
     if (/foo/ || /bar/)
     print "Found!"


  1. Rearranging a field – If you want to print a particular field in a
     particular order, awk can do it for you. Suppose you want to print the
     first 5 fields of a particular set in one field per line, you can use the
     following command:
     awk ’{ i = 1
     while (i <= 3) {
     print $i
     i++
     }
     }’ inputfile


  1. Splitting a line – In any given set of files, awk can help split a line
     into fields, where x is the name of the field:
     $ awk '{print $x,$x}'xyz.txt


  1. Running several commands at once – To run several commands at once, you
     can use a semicolon to specify both the commands:
     $ echo "Good morning! Jack" | awk '{$2="Jill"; print $0}'


  1. Executing an awk script – If you want to execute an awk script from a
     particular file, you can create a file sum_column and paste the below
     script in that file:
     #!/usr/bin/awk -f
     BEGIN {sum=0}
     {sum=sum+$x}
     END {print sum}
     In the above script, x equals the column you need to input in the file. On
     the successful completion of this task, you can use the following command
     to display the sum of the x column in the input file:
     awk -f sum_column input_file.


  1. Using –f– When coding, it may often seem impractical to refer to the
     terminal. awk uses –f to perform search from a file:
     awk -f script.awk inputfile


  1. Performing Math functions – You can also use awk for simple Math
     functions:
     awk ’{ sum = $2 + $3 + $4 ; avg = sum / 3
     > print $1, avg }’ grades


  1. Hello World in awk – You can print a simple Hello World in awk using the
     following command:
     awk "BEGIN { print "Hello World!!" }"
     You can also create a Hello World program. The following code will not
     only print the ubiquitous hello message but will also generate header
     information:
     $ awk 'BEGIN { print "Hello World!" }'


  1. Printing the total number of bytes – You can find out the total bytes used
     by files using the following command:
     ls -l . | awk '{ x += $5 } ; END \
     { print "total bytes: " x }'
     total bytes: 7449362


  1. Anonymizing an Apache log – You can use the following code to anonymize an
     Apache log:
     cat apache-anon-noadmin.log | \
     awk 'function ri(n) \
     {  return int(n*rand()); }  \
     BEGIN { srand(); }  { if (! \
     ($5 in jack)) {  \
     jack[$5] = sprintf("%d.%d.%d.%d", \
     ri(255), ri(255)\
     , ri(255), ri(255)); } \
     $5 = jack[$5]; print __g5_token5b610ba53dbe4  }'


  1. Operating in rows – If you have an address that you would like to sort in
     rows, you can do so using the following command:
     BEGIN { RS = "" ; FS = "\n" }
     {
     print "Name is:", $1
     print "Address is:", $2
     print "City and State are:", $3
     print ""
     }


  1. Using the while loop – The while loop keeps on executing the action given
     to it in a repeated process until the condition is true. For example, for
     printing numbers from 1 to 100, you can use the following code:
     awk 'BEGIN {i = 1; while (i < 100) { print i; ++i } }'


  1. Using the do-while loop – In this loop, the condition gets executed at the
     end of the loop even if the statement is false. For example, to print
     numbers from 1 to 100 using a do-while loop, you can use the following
     code:
     awk 'BEGIN {i = 1; do { print i; ++i } while (i < 100) }'


  1. Using BEGIN and END – The BEGIN keyword is used to create a header for
     processing your record:
     $ awk 'BEGIN {print "XXX"}
     In the same way, the END keyword is used after processing the data:
     END {print "File footer"}'

This concludes the list of 15 interesting awk commands. You can try these out
and see the results. Hope you find it useful. If you found this article
interesting, you can explore Mastering_Linux_Shell_Scripting_–_Second_Edition.
In this book, you’ll discover everything you need to know to master shell
scripting and make informed choices about the elements you employ.


About the author


Mokhtar Ebrahim

Mokhtar Ebrahim started working as a Linux system administrator in 2010. He is
responsible for maintaining, securing, and troubleshooting Linux servers for
multiple clients around the world. He loves writing shell and Python scripts to
automate his work. He writes technical articles on the Like Geeks website about
Linux, Python, web development, and server administration. He is a father to a
beautiful girl and a husband to a faithful wife.
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
