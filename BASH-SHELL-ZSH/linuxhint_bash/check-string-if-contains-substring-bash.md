





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Check If a String Contains a Substring in Bash

1 year ago
by Chrysanthus_Forcha
The question is, how to check if a string contains a substring in Bash. The
answer is: use Pattern Matching. This gives rise to another question, which is:
what is Pattern Matching? Well, a phrase in a sentence has certain
characteristics. That is why it differs from other phrases in the same sentence
or in other sentences. The characteristics can be coded as a pattern. In that
way, a particular phrase in a string can be identified. This article explains
how to identify a particular substring in a larger string, replace the
substring matched with another substring, and locate any substring in a larger
string by index. However, before diving into the explanations, one has to
recall the different ways a string is established in Bash.

String by Escaping Spaces

A string can be constructed by replacing each space with the space escape
sequence, ‘\ ’; as in:
myVar=Tourism\ in\ Egypt\ is\ one\ of\ the\ country\'s\ leading\ economic\
industries.
echo $myVar
The output is:
Tourism in Egypt is one of the country’s leading economic industries.
Note: the apostrophe also used the space escape sequence.

String by Single Quotes

Does the programmer have the time to be escaping all the spaces in a string?
No. Therefore, using two single quotes to delimit a string is better; such as:
myVar='Tourism in Egypt is one of the country'\''s leading economic
industries.'
A single-quoted string does not allow the expansion (replacing with its effect)
of any escape sequence. Fortunately, if two strings are coded next to one
another, they will be taken as one string. An escape sequence can be inserted
in-between, as done above. The escape sequence would be expanded. So the output
becomes:
Tourism in Egypt is one of the country’s leading economic industries.

String by Double Quotes

With double quotes, escape sequences are not expanded as well, but variables
are expanded. The following code illustrates this:
myVar=Tourism\ in\ Egypt\ is\ one\ of\ the\ country\'s\ leading\ economic\
industries.
echo $myVar
The output is:
Tourism in Egypt is one of the country’s leading economic industries.
Note: the apostrophe also used the space escape sequence.
In this article, the main type of string considered is the string in single
quotes.

Regular Expression FundamentalsRegex

Consider this string:
“This world is not really our home.”
Let “world” be the substring of interest. Then, the large string (whole string)
is called the target string or simply, the target. The ‘world’ in quotes is
called the regular expression or simply, regex. The content, world, is the
pattern, in this case.

Simple Matching

In the following code, if the word ‘world’ is found in the target, we would say
the word has been matched.
str="This world is not really our home."
reg='world'
if [[ $str =~ $reg ]]; then
    echo found
else
    echo not found
fi
=~ , which is the assignment operator followed by ~ , is called the binding
operator. The condition checks if the pattern is matched in the target string.
If a substring corresponding to the pattern is found in the target, the echo
statement displays “found”. If it is not found, the echo statement echoes “not
found”. The output for this code is:
found
As the pattern, world, is found in the target. Note that the delimiting space
after [[ and before ]] has been maintained.

Pattern

In the above code, ‘world’ in quotes is the regex while world itself is the
pattern. This is a straightforward pattern. However, most patterns are not that
simple. A pattern is a characterization of a substring to be found. And so, the
Bash pattern uses certain metacharacters. A metacharacter is a character about
other characters. For examples, Bash Pattern uses the following metacharacters:
^ $ \ . * + ? ( ) [ ] { } |
A regular expression can also be typed in the condition double brackets. But it
does not have to be in quotes. So, in this case, it is literally, a pattern.

Character Classes


Square Brackets

The output of the following code is “found”, meaning a match took place:
str='The cat came into the chamber.'
if [[ $str =~ [cbr]at ]]; then
    echo found
fi
The pattern, [cbr]at has matched “cat”, which begins with ‘c’, and which
continues and ends with “at”. “[cbr]at” means, match ‘c’ or ‘b’ or ‘r’ followed
by “at”.
The output of the following code is “found”, meaning a match took place:
str='The bat came into the chamber.'
if [[ $str =~ [cbr]at ]]; then
    echo found
fi
The pattern, [cbr]at has matched “bat”, which begins with ‘b’, and which
continues and ends with “at”. “[cbr]at” means, match ‘c’ or ‘b’ or ‘r’ followed
by “at”.
The output of the following code is “found”, meaning a match took place:
str='The rat came into the chamber.'
if [[ $str =~ [cbr]at ]]; then
    echo found
fi
The pattern, [cbr]at has matched “rat”, which begins with ‘r’, and which
continues and ends with “at”.
In the above code samples, the programmer does not know if “cat” or “bat” or
“rat” exist in the target string. But, he knows that the substring begins with
either ‘c’ or ‘b’ or ‘r’, then continues and ends with “at”. Square brackets in
a pattern allow different possible characters to match one character at a
position relative to others in the target. So, square brackets contain a set of
characters, of which one is matched for a substring. Finally, it is the
complete substring that is matched.

Range of Characters

In the above code [cbr] is a class. Even if ‘c’ or ‘b’ or ‘r’ corresponds to a
single character, if “at” that follows immediately does not match, the pattern
will not match anything.
Well, there are certain ranges that will form a class. For example, 0 to 9
digits form the class, [0-9] with 0 and 9 included. Lowercase ‘a’ to ‘z’ forms
the class [a-z] with ‘a’ and ‘z’ included. Uppercase ‘A’ to ‘Z’ forms the class
[A-Z] with ‘A’ and ‘Z’ included. From a class, it is one of the characters that
would match one character in the string.
The following code produces a match:
if [[ 'ID8id' =~ [0-9] ]]; then
    echo found
fi
This time the target is a literal string in the condition. 8, which is one of
the possible numbers within the range, [0-9], has matched 8 in the string,
‘ID8id’. The above code is equivalent to:
if [[ 'ID8id' =~ [0123456789] ]]; then
    echo found
fi
Here, all the possible numbers have been written in the pattern, so there is no
hyphen.
In the following code, a match is obtained:
if [[ 'ID8iD' =~ [a-z] ]]; then
    echo found
fi
The match is between lowercase ‘i’ of the range, [a-z], and lowercase ‘i’ of
the target string, ‘ID8iD’.
Remember: the range is a class. The class can be part of a bigger pattern. So
in a pattern, text can be in front and/or after the class. The following code
illustrates this:
if [[ 'ID8id is the identifier' =~ ID[0-9]id ]]; then
    echo found
fi
The output is: found. ‘ID8id’ from the pattern has matched ‘ID8id’ in the
target string.

Negation

Matching is not obtained from the following code:
if [[ '0123456789101112' =~ [^0-9] ]]; then
    echo found
else
    echo not found
fi
The output is:
not found
Without ^ in front of the range, within the square brackets, zero of the range
would have matched the first zero of the target string. So, ^ in front of a
range (or optional characters) negates the class.
The following code produces a match because the condition reads: match any non-
digit character anywhere in the target:
if [[ 'ABCDEFGHIJ' =~ [^0-9] ]]; then
    echo found
else
    echo not found
fi
So the output is: found .
[^0-9] means a non-digit, so [^0-9] is the negation of [0-9] .
[^a-z] means a non-lowercase letter, so [^a-z] is the negation of [a-z] .
[^A-Z] means a non-uppercase letter, so [^A-Z] is the negation of [A-Z] .
Other negations are available.

The Period (.) in the Pattern

The period (.) in the pattern matches any character including itself. Consider
the following code:
if [[ '6759WXY.A3' =~ 7.9W.Y.A ]]; then
    echo found
fi
The output of the code is “found” because the other characters match. One dot
matches ‘5’; another dot matches ‘X’; and the last dot matches a dot.

Matching Alternation

Consider this sentence for a target string:
“The cage has birds of different types.”
Somebody may want to know if this target has “pigeon” or “peacock” or “eagle”.
The following code can be used:
str='The cage has peacocks of different types.'
if [[ $str =~ pigeon|peacock|eagle ]]; then
    echo found
else
    echo not found
fi
The output is, found. The alternation metacharacter, | has been employed. There
can be two, three, four and more alternatives. What has matched in this code is
‘peacock’.

Grouping

In the following pattern, parentheses have been used to group characters:
a stage (dancer)
The group here is “a stage dancer” surrounded by the metacharacters ( and ) .
(dancer) is a subgroup, while “a stage (dancer)” is the whole group. Consider
the following:
“The (dancer is awesome)”
Here, the subgroup or substring is, “dancer is awesome”.

Substrings with Common Parts

A stakeholder is a person with an interest in a business. Imagine a business
with a website, stake.com. Imagine that one of the following target strings are
in the computer:
“The website, stake.com is for the business.”;
“There is the stakeholder.”;
“The stakeholder works for stake.com.”;
Let any of these strings be the target. The programmer may want to know if
“stake.com” or “stakeholder” is in whatever target string. His pattern would
be:
stake.com|stakeholder
using alternation.
“stake” has been typed twice in the two words. This can be avoided by typing
the pattern as follows:
“stake(.com|holder)”
“.com|holder” is the subgroup in this case.
Note: the use of the alternation character in this case. “stake.com” or
“stakeholder” will still be searched. The output of the following code is
“found”:
str='The website, stake.com is for the business.'
if [[ $str =~ stake(.com|holder) ]]; then
    echo found
fi
The substring matched here is “stake.com”.

The BASH_REMATCH Predefined Array

BASH_REMATCH is a predefined array. Assume that a pattern has groups. The whole
group matched, goes into the cell for index 0 of this array. The first subgroup
matched, goes into the cell for index 1; the second subgroup matched, goes into
the cell for index 2, and so on. The following code shows how to use this
array:
str='The stage dancer has come.'
if [[ $str =~ stage\ (dancer) ]]; then
    echo found
fi

for i in ${!BASH_REMATCH[@]}; do
    printf "${BASH_REMATCH[i]}, "
done
echo
The output is:
found
stage dancer, dancer,
The whole group is “stage dancer”. There is only one subgroup, which is
“dancer”.
Note: the space in the pattern has been escaped.

Upper/Lower Case Independence Matching

Matching, as explained above, is case-sensitive. Matching can be done
independently of the case. This is illustrated in the following code:
shopt -s nocasematch

str="We like good music."
if [[ $str =~ GoOd ]]; then
    echo found
fi

shopt -u nocasematch
The output is: found. The pattern is, GoOd. The substring matched is ‘good’.
Note how the nocasematch option has been enabled at the beginning of the code
segment and disabled at the end of the code segment.

Length of a String

The syntax to obtain the length of a string is:
${#PARAMETER}
Example:
str="We like good music."
echo ${#str}
The output is: 19.

String Reduction

The syntaxes for string reduction are:
${PARAMETER:OFFSET}
${PARAMETER:OFFSET:LENGTH}
where the counting for OFFSET begins from zero.
The following example shows how to remove the first 11 characters of a string:
str="I always dance to good music."
echo ${str:10}
The output is:
ance to good music.
Counting for LENGTH, begins from the next character. The following code shows
how a portion within the string can be allowed:
str="I always dance to good music."
echo ${str:10:6}
The output is:
ance t
The first 11 characters were removed; the next 6 characters were allowed, and
the rest of the characters were automatically removed.

Search and Replace

When a substring is found, it can be replaced with another substring. The
syntaxes for this are:
var=${PARAMETER/PATTERN/REPLACEMENT}
var=${PARAMETER//PATTERN/REPLACEMENT}
var=${PARAMETER/PATTERN}
var=${PARAMETER//PATTERN}
For the first syntax with single forward slash, only the first match is
replaced. Example:
str='There is a rat, a bat and a cat, in the chamber.'
ret=${str/[cbr]at/big cow}
echo $str
echo $ret
The output is:
There is a rat, a bat and a cat, in the chamber.
There is a big cow, a bat and a cat, in the chamber.
For the second syntax with double forward slashes, all occurrences of the match
are replaced. Example:
str='There is a rat, a bat and a cat, in the chamber.'
ret=${str//[cbr]at/big cow}
echo $str
echo $ret
The output is:
There is a rat, a bat and a cat, in the chamber.
There is a big cow, a big cow and a big cow, in the chamber.
For the third syntax with single forward slash, there is no replacement for the
first and only match.
Also, the first substring found is deleted. Example:
str='There is a rat, a bat and a cat, in the chamber.'
ret=${str/[cbr]at}
echo $str
echo $ret
For the fourth syntax with double forward slashes, there is no replacement for
all the matches. Also, all the substrings found are deleted. Example:
str='There is a rat, a bat and a cat, in the chamber.'
ret=${str//[cbr]at}
echo $str
echo $ret
The output is:
There is a rat, a bat and a cat, in the chamber.
There is a , a and a , in the chamber.

Conclusion

In order to check if a string has a substring in Bash, Pattern Matching has to
be used. Pattern Matching does not only take place in the condition double
brackets, [[ . . . ]]. It can also take place in parameter expansion, with its
${. . .}. With parameter expansion, it is possible to obtain a substring by
indexes.
What has been presented in this article are the most critical points in Pattern
Matching. There are more! However, what the reader should study next, is
Filename Expansion.


About the author


Chrysanthus Forcha

Discoverer of mathematics Integration from First Principles and related series.
Master’s Degree in Technical Education, specializing in Electronics and
Computer Software. BSc Electronics. I also have knowledge and experience at the
Master’s level in Computing and Telecommunications. Out of 20,000 writers, I
was the 37th best writer at devarticles.com. I have been working in these
fields for more than 10 years.
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
