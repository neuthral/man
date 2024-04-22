





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


bc to Perform Advanced Arithmetic Operations in BASH

2 years ago
by Usama_Azad
Basic Calculator, also known as ‘bc,’ is a Linux command-line utility used to
perform advanced arithmetics and algebra in bash scripts. It provides many
different mathematical functions like sine, cosine, tangent, natural logarithm
in bash. Bash can’t perform advanced arithmetic operations, like comparing
floats; that’s where bc comes in handy. The ‘bc’ command was preceded by ‘dc’
(Desk Calculator), a UNIX utility. In this tutorial, we will use the ‘bc’
command to perform advanced arithmetic operations.

Performing Basic Arithmetic Operations

Simple arithmetic operations like addition, subtraction, division, and
multiplication can be performed using the ‘bc’ command. The syntax for applying
simple binary operators in bash using the ‘bc’ command is as follows.
[email protected]:~$ echo “<num1> <operator> <num2>” | bc
In this section, we will use the ‘bc’ command to perform simple arithmetic
operations.
[email protected]:~$ num1=2.35322 5

[email protected]:~$ num2=1.223353

[email protected]:~$ echo “$num1+$num2” | bc

3.576578

[email protected]:~$ echo “$num1-$num2” | bc

1.129872

[email protected]:~$ echo “$num1*$num2” | bc

2.878824

[email protected]:~$ echo “$num1/$num2” | bc

1
In the above example, while performing division, we got the result without
decimal points. To get the result up to ‘n’ decimal points, we have to set the
scale value to ‘n’ as shown in the following example.
[email protected]:~$ echo “scale=10; $num1/$num2” | bc

1.9235862420
Alternatively, we can use the ‘-l’ flag and the ‘bc’ command to get decimal
output.
[email protected]:~$ echo “$num1/$num2” | bc -l

1.92358624207403750184
The ‘bc’ command can also be used to perform modulus division and calculate the
power of a number in bash scripts.
[email protected]:~$ echo “10%4” | bc

2

[email protected]:~$ echo “10^2” | bc

100

Performing Advanced Arithmetic Operations

So far, we have used the ‘bc’ command to perform some basic arithmetic
operations like addition, subtraction, multiplication, etc., now; in this
section, we will use the ‘bc’ command to perform some advanced arithmetic
operations. We will discuss how we can use comparison operators, logical or
boolean operators, advanced mathematical functions, and conditional statements
in bash using the ‘bc’ command.

Comparison Operators

Comparison operators take two numbers, compare them and then return 1 or 0
depending upon the comparison. If the comparison is true, then the result is
TRUE(1); otherwise, it is FALSE(0). Following are some examples of comparison
operators.

* num1 > num2: This comparison will return 1 if the num1 is greater than the
  num2.
* num1 < num2: The result will be 1 if the num1 is less than the num2.
* num1 <= num2: The result will be 1 if the num1 is less than or equal to the
  num2.
* num1 >= num2: The result will be 1 if the num1 is greater than or equal to
  the num2.
* num1 == num2 : The result will be 1 if the num1 is equal to the num2.
* num1 != num2: The result will be 1 if both the numbers are not equal.

Following are some examples of comparison operators used along with the ‘bc’
command.
[email protected]:~$ echo “5==5” | bc

1

[email protected]:~$ echo “4!=4” | bc

0

[email protected]:~$ echo “2>5” | bc

0

[email protected]:~$ echo “4<=4” | bc

1

Boolean Operators

Boolean or Logical operators are used in conditional statements to perform some
logical decisions. Following are the three basic logical operators.

* stat1 && stat2: This will return 1 if both the statements are non-zero.
* stat1 || stat2: This will return 1 if any of the statements is non-zero.
* ! stat: This will return 1 if the statement is non-zero and vice versa.

The following examples illustrate how logical operators are used with the ‘bc’
command.
[email protected]:~$ echo “-5 && 0” | bc

0

[email protected]:~$ echo “-1 || 0” | bc

1

[email protected]:~$ echo “! 0” | bc

1

Conditional Statements

Conditional statements are used to execute specific commands depending upon the
condition applied. The applied condition in the conditional statement involves
logical and comparison operators. Following is the example of conditional
statements with the ‘bc’ command.
[email protected]:~$ a=15

[email protected]:~$ b=20

[email protected]:~$ echo ‘ if(a>b) print “a is greater” else print “b is
greater” ‘ | bc -l

b is greater
In the above example, the statement checks if a is greater than b or not. If a
is greater than b, it will print “a is greater”; otherwise, it will print “b is
greater.” We can apply any condition using boolean and comparison operators in
the above example.

Mathematical Functions

The ‘bc’ command also provides some built-in mathematical functions which we
can use without defining them. Following are some essential functions used with
the ‘bc’ command in bash.

* s(x): returns sine of x where x is in radians
* c(x): returns cosine of x where x is in radians
* a(x): returns arctangent of x and the result is in radians
* sqrt(x): returns square root of x. It causes runtime error when x is negative
* l(x): returns natural log of the x.

These functions can be used with the ‘bc’ command, as shown in the following
examples.
[email protected]:~$ pi=3.1415

[email protected]:~$ echo “s($pi/2)” | bc -l

1

[email protected]:~$ echo “c($pi/2)” | bc -l

0

[email protected]:~$ echo “a(1)” | bc -l

0.7854
The square root of a number can be calculated in bash using the ‘bc’ command,
as shown in the following figure.
[email protected]:~$ echo “sqrt(4)” | bc -l

2
While trying to calculate the square root of a negative number, the shell will
throw a runtime error.
[email protected]:~$ echo “sqrt(-2)” | bc -l

Runtime error (func=(main), adr=4): Square root of a negative number
The Natural Logarithm of a number can be calculated in bash using the ‘bc’
command as follows.
[email protected]:~$ echo “l(2)” | bc -l

.69314718055994530941

Conclusion

While writing automation scripts in bash, sometimes we need advanced
mathematical functions and logical operators to execute commands. The ‘bc’
command provides many advanced mathematical functions and operators to perform
high-level arithmetic calculations. This tutorial discussed using the ‘bc’
command to perform advanced arithmetic operations in bash.


About the author


Usama Azad

A security enthusiast who loves Terminal and Open Source. My area of expertise
is Python, Linux (Debian), Bash, Penetration testing, and Firewalls. I’m born
and raised in Wazirabad, Pakistan and currently doing Undergraduation from
National University of Science and Technology (NUST). On Twitter i go by
@UsamaAzad14
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
