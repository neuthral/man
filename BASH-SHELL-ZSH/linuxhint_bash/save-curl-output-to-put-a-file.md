





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How do I Save a Curl Output to a File?

2 years ago
by Aqsa_Yasin
CURL is a repository as well as a command-line interface. It supports a variety
of protocols, including HTTP, HTTPS, FTP, SFTP, and several more interfaces for
downloading and transferring data/files. We can use the curl terminal tool to
retrieve a link or file via the terminal.
In this tutorial, we will show you how to import the files using the curl
instruction while working on the various Linux distributions as well as Unix-
like and macOS-type operating systems.
Make sure you have any Linux distribution or any Unix-like operating system
installed on your system. Users must have some sudo rights to use the system.
Open the command-line shell using the Application area of the Linux desktop.
You can find the version of curl utility installed on your system using the
below “version” command:
$ curl --version

Example 01: Save Pdf File via Curl

We will be having a very simple example of saving pdf files in the Linux system
using a curl command. Suppose you find some pdf book file regarding Linux
introduction for beginners on the web and you want to download it on your Linux
system. For this purpose, we will be using a very simple “curl” command in our
command terminal of Linux as presented in the image. The command keyword “curl”
has been followed by a link or URL of the particular pdf file, as shown:
$ curl https://tldp.org/LDP/intro-linux/intro-linux.pdf
It is possible to save the specific pdf book file to a specific name output
file created by you, using the below-stated command. We have been using
“new.pdf” as the name of the output file followed by the link to the pdf file.
You can see the download statistics of this particular pdf file.
$ curl –o new.pdf https://tldp.org/LDP/intro-linux/into-linux.pdf
Now open the home directory and you will find your newly downloaded pdf file in
it, e.g., new.pdf. Right-click on the file and tap on the “Open with Pdf”
option to open this pdf file and check whether it works properly or not.
You can see the file has been successfully saved in your Linux system and
working right.

Example 02: Save Html File via Curl

Imagine you want to search for simple and beginner-level Linux files, e.g, pdf
or HTML, to save these files in your Linux system using Curl instruction. You
have opened one web page and copied its URL on the Linux terminal within the
“curl” command. Note that we have been using the “-o” flag in our command to
forcefully save this “html” type page into a new output file “output.htm”. Now,
this new file “output.html” can be found in the home directory.
$ curl https://www.computer-pdf.com/operating-system/linux/786-tutorial-linux-
fundamentals.html -o output.html
Open the home directory of your Linux distribution to see a file “output.html”
is in it. When you double-click on this file, it will open the webpage provided
in the above query as a URL.
You can see, the “.html” file will be automatically opened in your browser of
Linux system, probably Mozilla Firefox.
The above illustration was about saving a URL or pdf file into a system output
file with some name decided by a user. Now, we will see how to save the URL
data into a file without naming a file using the simple curl command.
So, execute the below query in the shell for this. You can see we have been
using the capital “-O” flag followed by a URL in this query to save the data
without specifying the file name. You can see it will show you some statistics
about the web.
$ curl –O https://www.computer-pdf.com/operating-system/linux/786-tutorial-
linux-fundamentals.html
Now, when you again check the home directory of your Linux system, you will
find a file with a name as it is mentioned in the URL of the “html” webpage
used in the command. Open this file by double-tapping it.
Your browser, e.g., Mozilla Firefox, will open a link to the Html page, as
shown in the screenshot image below.

Example 03: Save Html File via Curl

As you have an idea that the “curl” utility is standard for saving the curl
output to a file. To understand the concept of saving curl output into files
using the “curl” command, we will be having another example. In this example,
we will be using a new weblink to save its web page into a file of our Linux
system. This file has some information regarding the software of GNU. So we are
using the curl command along with the lower case “-o” flag to save the HTML
page output into a user modified name file. We are using the “mygettext.html”
name for the output saving file.
The execution of the below command is showing some information regarding the
HTML page.
$ curl –o mygettext.html https://www.gnu.org/software/gettext/manual/
gettext.html
Now it’s time to open your Linux Home directory by clicking on the folders
icon. You can see the file has been generated with your specified name in the
command as “mygettext.html”.
Right-click and tap on “Open mygettext.html” to open this file to check if it
works or not.
Our browser has been opened and it shows the Html page as output, which was
mentioned in the “curl” command.
Now, we will use the capital “-O” flag in the curl command to save the Html
page into a file without creating a new file name. Hence, try to execute the
below query in the terminal of Ubuntu 20.04.
$ curl –O https://www.gnu.org/software/gettext/manual/gettext.html
Take a look at the home directory. It has created a file with a standard name
used for the page. Double-click on it to see the page.
The browser Mozilla Firefox has opened the Html page as specified in the URL of
the curl command.

Conclusion:

We have brilliantly done with many of the examples for saving the curl output,
e.g., Html or pdf file, into the file using the CURL command in the command
shell of Linux based system.
curl


About the author


Aqsa Yasin

I am a self-motivated information technology professional with a passion for
writing. I am a technical writer and love to write for all Linux flavors and
Windows.
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
