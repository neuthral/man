





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Base64 Encode and Decode From Command Line

2 years ago
by Karim_Buzdar
Encoding is the process used to convert data in a format required for effective
transmission or storage. In contrast, decoding is opposite to the encoding
method which converts the encoded data back to its original format. Base64 is
the encoding process where the binary data is converted into ASCII. Base64
encoding is mostly required to avoid the transmission problems that occur when
binary data is transmitted to text-based systems which cannot handle the binary
data properly. As a result, the information is lost or corrupted during
transmission.
Some of the uses of encoding are:

* Data compression
* Data hiding
* Transmission of data in another format

For encoding data, Base64 uses only alphabet, number and = symbol. For
instance, c2FtcGxlCg== is a valid encoded data while b?HV3.Zh2J== is not a
valid encoded data.
In this article, we will explain how to use the base64 command to encode and
decode the data in a string or a file.
We have performed the commands on Ubuntu 20.04 Focal Fossa system. However, you
can also run the same commands on other Linux distributions. For running the
commands, we have used the command line Terminal application, which can be
accessed using the Ctrl+Alt+T keyboard shortcut.

Base64 Syntax

Here is the syntax for encoding using Base64:
base64 [OPTION] [FILE]

Options

Some of the command-line options that can be used with base64 command are:
-d or --decode
Use this option to decode a file or a string.
--help
Use this option to display help regarding the usage of base64.
-i, --ignore-garbage
Use this option while decoding to ignore non-alphabet characters
--version
Use this option to display version information

Encoding String

You can easily encode a string using the base64 command. For instance, to
encode a sample text “Welcome to Linux” to base64, the command would be:
$ echo “Welcome to Linux” | base64
This command will encode the text in the string using base64 and print the
encoded text to standard output as shown in the following screenshot
You can also save the encoded output to a file rather than printing to standard
output using the redirection operator (>). The following command will encode
the text and save the output to a file named “encodedfile.txt:
$ echo “Welcome to Linux” | base64 > encodedfile.txt
To view the encoded file, you can use the cat command:
$ cat encodedfile.txt

Decoding String

You can also decode the base64 encoded text using the –decode or -d option. For
instance to decode base64 encoded text “V2VsY29tZSB0byBMaW51eAo=”, the command
would be:
$ echo “V2VsY29tZSB0byBMaW51eAo=” | base64 --decode
This command will decode the base64 encoded text and print the original text on
the standard output as shown in the following screenshot.
You can also save the decoded output to a file rather than printing to standard
output using the redirection operator (>). The following command will decode
the encoded text and save the original text to a file named “decodedfile.txt:
$ echo “V2VsY29tZSB0byBMaW51eAo=” | base64 –decode > decodedfile.txt

Encoding Text File

The base64 command can also be used to encode a text file. For instance, to
encode a text file named “testfile.txt”, the command would be:
$ base64 testfile.txt
This command will encode the specified text file and print its encoded form on
the standard output as shown in the following screenshot.
You can also save the encoded output to a file rather than printing to standard
output using the redirection operator (>). The following command will convert
the text in the file using base64 and save the output to another file named
“encodedfile.txt:
To view the encoded file, you can use the cat command:
$ cat encodedfile.txt

Decoding Text File

To decode an encoded text file, use the –decode or -d option. For instance to
decode base64 encoded text file “encodedfile.txt”, the command would be:
$ base64 -d encodedfile.txt
This command will decode the base64 encoded text file and print the original
text on the standard output as shown in the following screenshot.
You can also save the decoded output to a file rather than printing to standard
output using the redirection operator (>). The following command will decode
the encoded text and save the original text to a file named “decodedfile.txt
which can be later viewed using the cat command.
$ base64 -d encodedfile.txt > decodedfile.txt

Encoding User Input

Using the base64 encoding, we can encode any user-provided data. For this
purpose, we will need to create a script that will take user input, encode it
using base64 encoding, and print the encoded data on standard output.
Create a script “test.sh” with the following code:
#!/bin/bash
# Print message to ask for input
echo "Provide Some data to encode"
# Save the input to a variable named “data”
read data
# Encode using base64 encoding and save the output to a variable “encod_data”
encod_data=`echo -n $data | base64`
# Print encoded output
echo "Encoded text is : $encod_data"
Run the script as follows:
$ ./test.sh
After running the script, you will be asked to input the data that you want to
encode. Type some data and press Enter, and you will receive the encoded output
on the screen.

Validating User key

Now let’s see an example of base64 decoding. We will use the base64 decoding to
check user validity. To do so, we will create a script that will ask the user
for a key. Then it will match the input key with the predefined key, which will
be first decoded by base64 decoding. If the key entered by the user matches
with the predefined key, it will print “You have entered a valid key” message,
otherwise, you will see “The key you have entered is not valid “printed on the
screen.
Create a script “test1.sh” with the following code:
#!/bin/bash
# Print message to ask for input
echo "Enter your key"
# Save the key provided by the user to a variable named "key"
read key
# Decode the encoded key (QWJjMTIzCg) and save the output to a variable named
“orig_key”
orig_key=`echo 'QWJjMTIzCg==' | base64 --decode`
# Compare the key entered by the user with the decoded key
if [ $key == $orig_key ]; then
#if key matches, print this:
echo "You have entered a valid key"
else
#if key does not match, print this:
echo "The key you have entered is not valid"
fi
Run the script as follows:
$ ./test1.sh
After running the script, you will be asked for the key. Type the key and press
Enter. If the entered key matches with the predefined decoded key, you will
receive the ” You have entered a valid key” message, otherwise “The key you
have entered is not valid ” message will be printed on the screen.
This is how you can use the base64 to encode and decode a string or a file from
the command line. The results can be either printed on the standard output or
save in a file. However, remember that encoding is not similar to encryption,
and one can easily reveal the encoded data, so it is not recommended to use
encoding for the transmission of sensitive data.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
