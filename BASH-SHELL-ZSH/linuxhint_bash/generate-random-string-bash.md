





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Generate Random String in Bash

1 year ago
by John_Otieno
A random string represents a series of alphanumeric characters that have no
particular pattern. Although there is no absolute random string because their
generation uses mathematical logic, random strings can be unique.
In this tutorial, we shall look at various ways we can generate random strings
in bash. This functionality can be useful when creating usernames, passwords,
or seed data.

Method 1: md5 Hash

The very first method we can use to generate a random string in bash is md5
checksums. Bash has the $RANDOM variable, which produces a random number. We
can pipe this value to md5sum to get a random string.
To illustrate:
echo $RANDOM | md5sum | head -c 20; echo;
996e405cb0cdd2e10299
The $RANDOM variable is always random. As a result, the md5 checksum produces
is always random.

Method 2: UUID

You can also use the kernel UUID generator in /proc/sys/kernel/random/uuid.
This will give you will get a unique hexadecimal value that you can convert to
a random string using the sed and head command:
For example:
cat /proc/sys/kernel/random/uuid | sed 's/[-]//g' | head -c 20; echo;
c23174ce6fa149498fc7

Method 3: Pseudo devices

You have heard the phrase, “Everything in Linux is a file.” One of the concepts
that make this statement true is the ability to express devices as files.
Files located in /dev are known as pseudo devices; they act as bridges between
the kernel and the hardware. One of the files in this directory is the uradom
file.
The urandom file provides an interface to access the kernel random number
generator. Hence, we can use it to generate a random string as illustrated
below:
cat /dev/urandom | tr -dc '[:alpha:]' | fold -w ${1:-20} | head -n 1
qGswsbBusuztUEKXhiHu
We pipe the output of urandom to tr, which generates alphanumeric values and
then folds the values to the width of up to 20 characters. Finally, we get one
lined string with head -n.
To get multiple values at once, change the value of head -n to the number of
lines required.
cat /dev/urandom | tr -dc '[:alpha:]' | fold -w ${1:-20} | head -n 5
POzxNTvFtNQqjzgJFwou
RaZpkKDCWIvzAxaCraMu
BldZwyUIYWZPFnMiMETl
CxVFKmAoGBEZysLqzORo
YoXTcgLzXdnoEzoMwmFa

Method 4: Base64

You can also use the base64 utility to generate a random string. For example,
using the $RANDOM variable, we can do:
echo $RANDOM | base64 | head -c 20; echo
MTM2ODEK

Method 5: OpenSSL Pseudo Random Bytes

OpenSSL rand command allows you to generate random bytes based on the type
specified. These types include base63 and hex values.
For example:
openssl rand -hex 20
1dba62137447861b2b2eb81e5886fa98d021007b
Or use base64 as:
openssl rand -base64 21
i05hHQeajBZcZerx/FtPtJH4XYUd

Conclusion

In closing, bash provides various utilities you can use to generate random
strings. Therefore, all you need to do is combine various tools and develop a
clever way to get random strings that suit your needs.


About the author


John Otieno

My name is John and am a fellow geek like you. I am passionate about all things
computers from Hardware, Operating systems to Programming. My dream is to share
my knowledge with the world and help out fellow geeks. Follow my content by
subscribing to LinuxHint mailing list
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
