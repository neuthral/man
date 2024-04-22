





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash print array with newlines

1 year ago
by Aqsa_Yasin
An array is a container containing the same data type items, either integer
type or float type. We can deal with arrays by performing several operations on
them. One commonly used Delima is to break the array and print each word on a
new line. This feature is discussed in today’s article. To understand this
concept, you need to access a Ubuntu terminal to perform bash-related terms on
Ubuntu. We have covered the topic from simplest to critical samples for the
understanding of the user.

Example 1

In this example, take a variable and assign the value to it. The value is a
long string. To have the result of the string in new lines, we will assign the
variable’s value to an array. To ensure the number of elements present in the
string, we will print the number of elements using a respective command.
S a=”I am a student. I like programming”

$ arr=( ${a} )

$ echo “arr has ${#arr[@]} elements.”
You will see that the resultant value has displayed the message with the
element numbers. Where the ‘#’ sign is used to count only the number of words
present. [@] shows the index number of the string elements. And the “$” sign is
for the variable.
To print each word on a new line, we need to use the keys “%s’\n”. ‘%s’ is to
read the string till the end. At the same time, ‘\n’ moves the words to the
next line. To display the content of the array, we will not use the “#” sign.
Because it only brings the total number of the elements present.
$ printf “’%s’\n” “${arr[@]}”
You can observe from the output that each word is displayed on the newline. And
each word is quoted with a single quote because we have provided that in the
command. This is optional for you to convert the string without single quotes.

Example 2

Usually, a string is broken into an array or single words by using tabs and
spaces, but this usually leads to many breaks. We have used another approach
here, which is the use of IFS. This IFS environment deals with showing that how
a string is broken and converted into small arrays. IFS has a default value of
“ \n\t”. This means that space, a new line, and a tab can pass the value into
the next line.
In the current instance, we will not use the default value of IFS. But instead,
we will replace it with a single character of newline, IFS=$’\n’. So if you use
space and tabs, it will not cause the string to break.
Now take three strings and store them in the string variable. You will see that
we have already written the values by using tabs to the next line. When you
take print of these strings, it will form a single line instead of three.
$ str=” I m a student

I like programming

My fav language is .net.”

$ echo $str
Now it’s time to use IFS in the command with the newline character. At the same
time, assign the values of the variable to the array. After declaring this,
take a print.
$ IFS=$’\n’ arr=( ${str} )

$ printf “%s\n” “${arr[@]}”
You can see the result. That shows that each string is displayed individually
on a new line. Here the whole string is treated as a single word.
One thing is to be noted here: after the command is terminated, the default
settings of IFS are again reverted.

Example 3

We can also limit the values of the array to be displayed on every newline.
Take a string and place it in the variable. Now convert it or store it in the
array as we did in our previous examples. And simply take the print using the
same method as described previously.
Now notice the input string. Here we have used double quotes on the name part
two times. We have seen that the array has stopped displaying on the next line
whenever it encounters a full stop. Here full stop is used after the double-
quotes. So each word will be displayed on separate lines. The space between the
two words is treated as a breaking point.
$ x=( name=” Ahmad Ali But”. I like reading. “fav subject=Biology”)

$ arr=( ${x} )

$ printf “%s\n” “${arr[@]}”
As the full stop is after “Butt”, so the breaking of the array is stopped here.
“I” was written without any space between the full stop, so it is separated
from the full stop.
Consider another example of a similar concept. So the next word is not
displayed after the full stop. So you can see that only the first word is
displayed as a result.
$ x=(name=”shawa”. “fav subject”=” English”)

Example 4

Here we have two strings. Having 3 elements each inside the parenthesis.
$ array1=(apple banana peach)

$ array2=(mango orange cherry)
Then we need to display the contents of both strings. Declare a function. Here,
we used the keyword “typeset” and then assigned one array to a variable and
other arrays to another variable. Now we can print both arrays respectively.
$ a() {

Typeset –n firstarray=$1 secondarray=$2

Printf ‘%s\n’ 1st: “${firstarray[@]}”

Printf ‘%s\n’ 2nd: “${secondarray[@]}” }
Now to take print of the function, we will use the function’s name with both
string names as declared earlier.
$ a array1 array2
It is visible from the result that each word from both arrays is displayed on a
new line.

Example 5

Here an array is declared with three elements. To separate them on new lines,
we used a pipe and a space quoted with double-quotes. Each value of the array
of the respective index acts as input for the command after the pipe.
$ array=(Linux Unix Postgresql)

$ echo ${array[*]} | tr “ “ “\n”
This is how the space works in displaying each word of an array on a new line.

Example 6

As we already know, the working of “\n” in any command shifts the entire words
after it to the next line. Here is a simple example to elaborate on this basic
concept. Whenever we use “\” with “n” anywhere in the sentence, it leads to the
next line.
$ printf “%b\n” “All that glitters is \not gold”
So the sentence is halved and shifted to the next line. Moving towards the next
example, “%b\n” is replaced. Here a constant “-e” is also used in the command.
$ echo –e “hello world! I am \new here”
So the words after “\n” are shifted to the next line.

Example 7

We have used a bash file here. It is a simple program. The purpose is to show
the printing methodology used here. It is a “For loop”. Whenever we take print
of an array through a loop, this also leads to the breakage of the array in
separate words on newlines.
For the word in $a

Do

Echo $word

done
Now we will take print from the command of a file.

Conclusion

There are several ways to align your array data on the alternative lines
instead of displaying it on a single line. You can use any of the given options
in your codes to make them effective.


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
