




















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Convert Hexadecimal to Decimal in Bash

4 years ago
by Fahmida_Yesmin
Four types of number systems are popular in computer systems. These are
Decimal, Binary, Octal and Hexadecimal. The binary system is 2 based and all
arithmetic calculations are done by computer in Binary system. It uses only two
digits, 0 and 1 for calculation. The number system that we use for general
calculation is decimal system which is 10 based. 0 to 9 numbers are used in the
decimal system for calculation. The octal number system is 8 based and
represented by 0 to 7 digits. The hexadecimal number system is 16 based and it
uses 0 to 9 and A to F characters to represents the number. You can easily
convert one number to another number system using the bash script. How you can
convert Hexadecimal (hex) number to Decimal number in Bash is shown in this
tutorial using various examples.


Example-1: Using obase, ibase and bc

One of the simple ways to convert any number system to another number system is
to use ibase, obase and bc. Create a bash file named hextodec1.shand add the
following code. According to this example, a hex number will be taken as input
and converted into the decimal number based on the value of obase and ibase.
Here, obase is set to 10 for converting decimal number, ibase is set to 16 to
take the input number as hex number and `bc` command is used for conversion.
#!/bin/bash
echo "Type a hex number"
read hexNum
echo -n "The decimal value of $hexNum="
echo "obase=10; ibase=16; $hexNum" | bc
Output:
Run the script with bash command and give any hexadecimal number as input to
find out the decimal value.
$ bash hextodec1.sh

Example-2: Using ibase, command line argument and bc

Create a bash file named hextodec2.shand add the following code. In this
example, the input value has to give in the command line argument, which will
be read by [email protected] Here, just ibase with 16 value is used to convert
hex to the decimal number. 
#!/bin/bash
echo -n "The decimal value of [email protected]="
echo "ibase=16; [email protected]"|bc
Output:
Run the script with bash command, file name and a hexadecimal number as command
line argument. Here, FF is given as command line argument which is taken as hex
value.
$ bash hextodec2.sh FF

Example-3: using printf method

Another option for converting hex to the decimal number is printf. ‘%d’format
specifier is used in printf method to convert any number to decimal number.
Create a bash file named hextodec3.shand add the following code. According to
this script, a hex number will be taken as input and it is used in printfmethod
with %dto print the decimal value.
#!/bin/bash
echo "Type a hex number"
read hexNum
printf "The decimal value of $hexNum=%d\n" $((16#$hexNum))
Output:
Run the script with bash command and give any hexadecimal number as input to
find out the decimal value.
$ bash hextodec3.sh

Example-4: using double brackets

There is another way to convert hex to the decimal number without using ibase,
obase and bc or printf method. You can use double brackets expression with 16
base to convert hex to the decimal number. Create a bash file named
hextodec4.shand add the following code. Here, echo command will take the number
as hex and print the output in the decimal number system.
#!/bin/bash
echo "Type a hex number"
read hexNum
echo $(( 16#$hexNum ))
Output:
Run the script with bash command and give any hexadecimal number as input to
find out the decimal value.
$ bash hextodec4.sh

Example-5: Converting the list of hexadecimal numbers

Suppose, you have a text file named ‘hexList.txt’ that contains the following
list of hex numbers.
HexList.txt
AB05
FF
ABCD
ACCD
BED
Create a bash file named hextodec5.shand add the following code to convert each
hex value of hexList.txt into the decimal value. Here, obase, ibase, and bc are
used for conversion. while loop is used to read each hex value from the text
file, convert to decimal value and print.
#!/bin/bash
while read number
do
echo -n "The decimal value of $number(Hex)="
echo "obase=10; ibase=16; $number" | bc
done < hexList.txt
Output:
Run the script with bash command. There are five hex values in the text file
and the output shows five decimal values after conversion.
$ bash hextodec5.sh
This tutorial shows multiple ways to convert hex to decimal values using the
bash script. You can follow any of the ways for your conversion purpose. You
can also convert other number systems using the scripts mentioned in this
tutorial just by changing the base value.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
