





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Obtain a Bash Substring After a Specified Character

2 years ago
by Aqsa_Yasin
In programming, a string is a series of characters, whether as a precise
constant or some sort of variable. The characters contained within a string can
be any number, digit, or special character. Keywords can be used to obtain a
substring after certain characters, and all keywords work the same. Some
examples of keywords include the following:

* Cut
* Awk
* Sed

This article provides several examples to improve your understanding of the
concept of obtaining a substring after a certain character.
To follow the examples provided in this tutorial, first, log into your Linux
system and open the terminal. Next, create a new file with the name “input.sh.”

Example 1: Using the Cut Keyword

Open the file “input.sh” from the home directory, and write the following code
in the file. In our first example, we will define a string named “string” with
some value in it having some characters and numbers. We will use the keyword
“cut” in this code, followed by “-d,” to obtain the substring of the particular
string. After that, we will provide the exact character in inverted commas as
“-“ so that the substring will be searched after this special character.
Here, it is important to understand the main idea of substring formation. You
must remember how to include the keyword “f” when using the “cut” command. The
keyword “f” can be used in various ways to create a substring, so let us look
at this particular method.
-f2: text after the first special character “-“ and before the next “-“
This means that it should display the substring “bar” because it is located
after the first “-“ character and before the next “-“ character.
After running this bash file, we obtained the substring “bar,” as we expected.
Now, we will check the same example for the “-f2-“ keyword. Update the file, as
below.
-f2-: the text following the first special character “-“ regardless of whether
there are numerous “-“ characters.
This implies that it will display the substring “bar-123” because it is located
after the first “-“ character, regardless of whether any “-“ characters exist.
After executing this bash file, we obtained the substring “bar-123,” as it is
located after the first “-“ character.
We will now take the same condition, with little changes to the string and
characters. We have defined the new string “str” and assigned it a different
value. In this example, “i” is the special character to be searched from the
original string, and from this character onward, we will create a substring. In
this case, we have used:
-f2: to create a substring following the first special character “i” and before
the next character “i.”
This implies that it should display the substring “ltEff=str” because it is
located after the first “i“ character.
When the file runs, a substring will be obtained before the next “i” and after
the first “i.”
You can try this method with the same line of string, as shown in the image
below:
It will display the same result as above.
Now, we will use the “cut” keyword with little change to the “f” condition in a
single line. We will use “f1” in this case to change the outcome of the
substring. We are using:
-f1: to create a substring before the first special character “i.”
This infers that it should display the substring “GenF” because it is located
before the special character “i.”
The output below is as expected.
Here, we are using the same example with little change. We have been using the
old method for it.
The result of this script is the same as above.
Next, taking the same previous example, we use the “cut” keyword, while
changing the keyword “f.” Here, we will use “f3” to change the outcome of the
substring, and we are using:
-f3: to create a substring after the next special character “i.”
This indicates that it should show the substring “ng.-01234” because it is
located after the next special character “i.”
We will run the same code using the Bash command. You can see the new result
below:

Example 2: Using the Awk Keyword

Open the file “input.sh” and write the appended code in the file. Here, we have
declared an echo statement with the string “foo-bar-123” using the “awk”
keyword. The print term is followed by the “-F-“ keyword. This will create a
substring after the next special character, which is “123,” and print it. There
is no need to define the special character in this case.
The following is the output “123” that was mentioned above.

Example 3: Using the Sed Keyword

In this example, we will update the same file with the code provided below. In
this case, the keyword “sed” is used instead of “cut” or “awk.”
This code will display a similar output to that of the previous example.

Example 4: Using Special Characters

In the next example, we will update the same file with the code provided below.
Here, we will define three strings: “string,” “searchstr,” and “temp.” We have
“${string%$searchstr*}” in the code. The “%” will search for the value of the
variable “searchstr,” which is “and,” and will remove everything after this
special variable from the original string. The remaining text will be saved in
the variable “temp.” Now, the variable “temp” will be printed, along with the
text “This is a new string.”
If we execute the above code, the original string will be printed first; then,
the new substring will be printed.
Taking the same example with a small update, we will use the “#*” string so
that everything following the value of “searchstr,” which is “and,” will be
inserted into variable “temp.”
When you check it in Bash, you will see that the old string will print first.
After that, since “it will be removed” is a new value of variable “temp,” that
is why it will be printed at the next line first, along with the text “This is
a new string.”

Conclusion

If you want to obtain a substring from any string using some special character
in it, you can do so by utilizing the methods provided above.


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
