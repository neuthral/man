





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to resolve ‘bash wget command not found’ problem

3 years ago
by Fahmida_Yesmin
`wget` command is used on Linux to download files from the web. It is a free
tool that supports http, https and ftp protocols, and http proxies for
downloading any file. It is called non-interactive downloader because It can
work in the background. So, the user can disconnect from the system after
starting the download and the downloading task will be completed by this
command as background process. Using this command is beneficial, when
downloading files from slow or unstable network. If the network disconnects for
any reason before completing the download task, then this command will keep
trying to complete the download when connected with the network. Sometimes, the
Linux user get the error message, “ –bash:wget:Command not found” while
executing this command. It indicates that `wget` utility is not installed on
the operating system or it is not working properly. How you can resolve this
issue on Ubuntu operating system and download the file by using `wget` command
are shown in this tutorial.
Syntax:
wget [option] [URL]
Option and URL parts are optional for this command.  There are many options
exist for this command. Some basic start-up options for this command are, -V or
–version, -h or –help, -b or –backgroundand-e or –execute. URL will contain the
location from where the file will be downloaded. The uses of some common
options are explained with examples in this tutorial.

Check `wget` command is installed or not

Run the following command to check the installed version of `wget` command. If
the command is not installed before then you will get the error, “ –bash:wget:
Command not found”.
$ wget –V
The following output shows that wget command of version 1.19.4 is installed on
the system.

Install wget command on Ubuntu

Run the following command to install wget command on Ubuntu.
$ sudo apt-get install wget
After completing the install, again run the previous command to check the
install version of this command. Run the wget command with –h option to display
all option details of this command.
$ wget -h

Example-1: wget command without any option

The following `wget` command will download the index.html file from the site,
linuxhint.com and the file will be stored on the current working directory.
‘ls’ command is used here to check the html file is created or not in the
current directory.
$ wget https://linuxhint.com
$ ls

Example-2: `wget` command with -b option  

‘-b’ option is used with `wget` to complete the download in the background. The
following command will download, temp.zip file from the site,
fahmidasclassroom.com in the background.
$ wget -b https://fahmidasclassroom.com/temp.zip

Example-3: `wget` command with -c option

‘-c’ option is used with `wget` to complete the partial download. It is
mentioned in the beginning of this tutorial that `wget` command has resume
capability. If any incomplete download exists in the current directory due to
network error or other reason the `wget` will resumes the download to complete
the task with ‘-c’ option. The following command will resume the download if
the file, xampp-linux-x64-7.2.2-0-installer.run is downloaded partially before.
Run the following command to complete the partial download of xampp installer
file.
$ wget -c https://www.apachefriends.org/xampp-files/7.2.2/
xampp-linux-x64-7.2.2-0-installer.run

Example-4: `wget` command with -O option

-O option is used with `wget` command to store the downloaded file with
different name. The following command will download the file, google-chrome-
stable_current_amd64.deb with the name, chrome.deb.
$ wget –O chrome.deb https://dl.google.com/linux/direct/
google-chrome-stable_current_amd64.deb

Conclusion

The uses of different options of `wget` command are explained in this tutorial
by using different examples. If the user facing any problem to use `wget`
command for downloading any file, then this tutorial will help them to solve
the problems.


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
