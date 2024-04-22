





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash OR Operator

2 weeks ago
by Prateek_Jangid
Bash contains various types of logical operators to simplify the script’s
operation. Logical operators like OR perform a Boolean (a type of expression
that evaluates whether a value is true or false) OR operation. This logical OR
operator is represented as “||” in Bash and joins two or more compound
conditions to form a compound condition. As a beginner, it is good to
understand the OR logical operators to create complex scripts easily. In this
tutorial, we will explain everything about the Bash OR operator.

Bash OR Operator

The OR operator takes two operands (logical expressions) and returns true if
either of the operands is true; otherwise, it returns false. In Bash scripts,
the OR operator is used through double pipes. The following is the truth table
of the Bash logical OR operator which helps you to understand everything
better:
Let’s take an example where we create a script that gives a specific result
after entering a particular number. For example, for college admission, any
person should be 18 years or more to be admitted to college. We put two
conditions – first, if the candidate’s age is equal to 18 years and second, if
their age is over 18 years. It asks you to proceed if either condition is true.
However, if both conditions are false, it tells you that your age is invalid.
Output:
In the previous example, you can see that we used an OR logical operator in our
script using pipes with square brackets. You can also use an OR operator in
Bash using double square brackets. The syntax is as follows:
[[ operand _1 ||operand_2 || operand_3 ………. || operand_n ]]
Output:
Through both types of syntax, you can see that you get the same output. In this
way, you can use any two of the two methods according to your convenience.

-O Logical Operator

You can also use the -o flag for the OR operator to replace the double pipe.
This flag also works similarly, and it returns a true statement if any of the
conditions is true. Otherwise, it displays a false statement. Its syntax is
something like this:
[operand _1 -o operand_2 -o operand_3………. -o operand_n]
In the following example, we will see which character is a vowel and which is
consonant through the OR operator:
Output:
In this way, you can also use the OR operator through the -o flag.

Conclusion

This is all about the OR logical operator which you can use in the Bash script.
Many Bash users believe that the OR logical operator and -o logical operator is
different, but it is not. These two are the same, but the only difference is
that there is a specific way to use both, as shown in the given examples. Using
both methods and running them in the terminal give the same output.


About the author


Prateek Jangid

A passionate Linux user for personal and professional reasons, always exploring
what is new in the world of Linux and sharing with my readers.
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
