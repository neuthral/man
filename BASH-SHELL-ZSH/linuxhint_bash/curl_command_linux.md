





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Use cURL Command in Linux

6 months ago
by David_Adams
ThecURL function is to ease file transfer between devices. It is a very
friendly method to download and share files from the console. It was even
incorporated by Microsoft in 2017 as a tool for Windows users to transfer files
from the command line.

cURL Features


* Supported protocols include DICT, FILE, FTP, FTPS, GOPHER, HTTP, HTTPS, IMAP,
  IMAPS, LDAP, LDAPS, POP3, POP3S, RTMP, RTSP, SCP, SFTP, SMB, SMBS, SMTP,
  SMTPS, TELNET, and TFTP
* Authentication and encryption
* Proxy implementation
* Resume interrupted transfers

While focusing only on a few widely used protocols, this tutorial describes how
to implement all features previously listed. All steps described below include
screenshots. Thus, making it easy for all users to understand and follow them.

How to Install cURL in Linux

To begin with, install cURL by running the following command for Debian-based
Linux distributions (Including Ubuntu):
sudo apt install curl
To install cURL on CentOS or Fedora Linux distributions, use the following
command:
yum install curl

All About Downloading Files Using cURL

The first command shows how to download a file using cURL, keeping the original
file name.
To do it, run cURL and add the -O parameter followed by the file path. The
proper syntax is shown below, where <File address> must be replaced with the
full URL or path of the file to download:
curl -O <File address>
The syntax is shown in the example below, in which I downloaded the robots.txt
file from the LinuxHint site:
curl -O https://linuxhint.com/robots.txt
You can download multiple files using cURL; just add a -O flag followed by each
file you want to download, as shown in the following example in which the
robots.txt file is fetched from linuxhint.com, and a logo is fetched from the
site named argexchanger:
Curl -O https://linuxhint.com/robots.txt -O https://argexchanger.com/wp-
content/uploads/2022/02/Logo-4-850x113.png
The command shown in the previous screenshot is long, while the following
syntax is:
curl -O <https://URL.COM/FILE> -O <https://URL.COM/FILE2> -O <https://URL2.COM/
FILE3>
The previous flag (-O with upper case) saves the file keeping the original
name. That’s the most widely used flag when using cURL.
By default, cURL downloads files in the working directory. You also can define
a custom name or path for the file by implementing the -o flag (Lower case)
followed by the name or path you want to define.
In the following example, I download the file robots.txt from Linux Hint, but I
save it as CustomName, where CustomName is arbitrary and can include the file
extension:
curl https://linuxhint.com/robots.txt -o CustomName
In the following screenshot, I used the -o flag to define a custom name and a
custom path for the file stored in the test subdirectory of the home directory
under the name CustomName:
curl https://linuxhint.com/robots.txt -o ~/test/CustomName
Another useful cURL feature is the -C- flag to resume interrupted downloads. In
the following screenshot, I showed how I resume a download previously
interrupted by executing cURL followed by flags -C-, -O and the target,
curl -C- -O https://ftp.gnu.org/gnu/nano/nano-6.2.tar.gz
cURL also supports transferring files through proxy servers.
To implement a proxy, you need to add the -x flag followed by the proxy address
and port. The proper syntax is:
curl -x <ProxyIP>:<ProxyPort> -O <File URL/Path>
Where <ProxyIP> must be replaced with the proxy IP address or host, <ProxyPort>
must be replaced with the proxy port, and <File URL/Path> with the file
address.
In the following example, I downloaded the robots.txt file using the proxy with
IP address 8.213.128.41 through port 80:
curl -x 8.213.128.41:80 -O https://linuxhint.com/robots.txt

Uploading Files Using cURL in Linux

The previous section described how to download files in Linux using cURL. The
current section explains how to upload files, both through HTTP and FTP.
Uploading files through FTP without credentials (Anonymous) using cURL is
pretty simple. Just use the -T flag followed by the file you want to upload and
the FTP address.
The syntax is:
curl -T <Path/To/File> <FTP-Server>
Using credentials doesn’t make the task harder. You can define a username only,
and you will be required to fill in the password during the connection process.
This option is better than typing the password in the command to avoid a plain
text password.
To upload a file to an FTP server requiring login, use the -u flag followed by
the username. Some server configurations like the one I’m using requires
including the server host or IP address after the username, as shown in the
screenshot below, in which the -u flag is used to define the user and host (
[email protected]) and the -T flag is used to define the file to upload
(zippedfile.zip).
After executing the following syntax, you will be required to type the
password.
Note: Replace [email protected] with your actual username and replace ftp://
argexchanger.com with your actual FTP server.
curl -u linuxhint@argexchanger.com -T zippedfile4.zip  ftp://argexchanger.com
You also can include the password in the command, avoiding being required to
type the password after running the command. The syntax is the same as shown
above. You do not need additional flags; just add a colon followed by the
password as shown in the screenshot below, where YourpasswordHere is the
password:
curl -u linuxhint@argexchanger.com:YourpasswordHere -T zippedfile4.zip ftp://
argexchanger.com
To finish this tutorial, let’s see how to upload files through the HTTP
protocol. For this purpose, I will use the https://transfer.sh free service,
which allows you to upload files using HTTP.
The flag used in this example is –upload-file followed by the file you want to
upload. In this case, a file named linuxhintfile and the HTTP server are shown
in the following image:
curl --upload-file linuxhintfile https://transfer.sh/linuxhintfile
By learning all the cURL commands explained previously, you will be able to use
this tool productively.

Conclusion:

As you can see, using the cURL command is pretty easy. cURL is a command line
but user-friendly tool anyone dealing with consoles must be able to use. This
command is especially useful because it is cross-platform and can be found on
Unix like macOS and Microsoft Windows operating systems. This is excellent for
fetching and sharing files with only a command execution. You can use free FTP
and HTTP file-sharing services to test all instructions explained in this
article.
Thank you for reading our tutorial on cURL. I hope it was useful for you. Keep
reading Linux Hint for more Linux professional tutorials.
curl


About the author


David Adams

David Adams is a System Admin and writer that is focused on open source
technologies, security software, and computer systems.
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
