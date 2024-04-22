





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Arrays In-Depth

1 year ago
by Chrysanthus_Forcha
In Bash, an array can be an indexed array or an associative array. An indexed
array is a list whose items are numbered beginning from zero. An associative
array is a list where strings have replaced the numbers. Assume a pen, an
exercise book, a textbook, a ruler, $42, and a pencil on a study table. These 6
items can be written as a list, as follows:

  1. pen
  2. exercise book
  3. textbook
  4. ruler
  5. 42
  6. pencil

This is an example of an indexed array. There are 6 items, but the items have
been numbered from zero to 5. Numbering this way is indexing. Index counting in
Bash begins from zero and not 1.
Each of these products is manufactured from some main material. A list of the
main material, followed by its finished product, is:
ink => pen
soft paper => exercise book
hard paper => textbook
plastic => ruler
special paper => 42
wood => pencil
This is an example of an associative array. It is not enough to just type these
arrays in a Bash file. Either of the different types of arrays has to be coded.
The coding of an indexed array is similar to the coding of an associative
array. However, there are small but important differences. This article gives
an in-depth look into Bash arrays.
Article Content

* Indexed_Array
* Associative_Array
* Conclusion


Indexed Array

Creating an Indexed Array
One way to create the above-indexed array is as follows:
arr=(pen 'exercise book' "textbook" ruler 42 pencil)
Here, arr is the name of the array. The programmer could have given some other
name. Spaces separate the different items in the array list. If an item
consists of more than one word, it is typed in single or double-quotes. The
index for the pen is 0; the ‘exercise book’ index is 1; the index for
“textbook” is 2; the index for ruler is 3; the index for 42 is 4; the index for
pencil is 5.
Another way of creating the above array begins as follows:
arr[2]="textbook"
That is, the array is created, beginning with any item in the list. ‘2’ in the
square brackets is known as a subscript. The other elements can be included
later, as follows:
arr[0]=pen
arr[1]='exercise book'
arr[3]=ruler
arr[4]=42
arr[5]=pencil
Note that in the inclusion, the item of index 2 has not been repeated.
Another way of creating the above array is as follows:
declare -a arr
Here, “declare” is a reserved word. ‘-a’ means indexed array. “arr” is the name
of the programmer’s choice. All the elements can then be included as follows:
arr[0]=pen
arr[1]='exercise book'
arr[2]="textbook"
arr[3]=ruler
arr[4]=42
arr[5]=pencil
This is inclusion by assignment. Remember, when any value is assigned to a
variable, there should be no space between the assignment operator, = and the
variable or the value.

Referencing Indexed Element

The syntax to reference an element is:
${name[subscript]}
Where name is the name of the array, such as arr. Subscript is an integer
(number).

Positive Indices

Index counting normally begins from zero. In the following code, the values of
the elements are read and displayed:
arr=(pen 'exercise book' "textbook" ruler 42 pencil)

for ((i=0; i < 6; ++i)); do
    echo ${arr[i]}
done
The output is:
pen
exercise book
textbook
ruler
42
pencil
Six elements are beginning from index zero to index 5. So, the iteration is
done 6 times and not 5 times.

Negative Indices

Negative indices can be used to access elements. In this case, -1 refers to the
last element; -2 refers to the last-but-one element; -3 refers to the element
before the last-but-one element, and so on. So, for the above array, -6 refers
to the first element. The following code illustrates this:
arr=(pen 'exercise book' "textbook" ruler 42 pencil)

for ((i=-1; i >= -6; --i)); do
    echo ${arr[i]}
done
The output is:
pencil
42
ruler
textbook
exercise book
pen
The display is in reverse order.

Displaying all the Elements in Indexed Array

To display all the elements, ${name[*]} or ${name[@]} can be used. In these
expressions, * or @ is in the place of the index. And with that, instead of
returning the values of elements, the values of elements present in the array
are returned. The following code illustrates this:
declare -a arr
arr[1]='exercise book' arr[3]=ruler arr[5]=pencil
echo ${arr[@]}
echo ${arr[*]}
The output is,
exercise book ruler pencil
exercise book ruler pencil
Notice that @ and * used in this way are synonyms. There is a problem with the
output: the phrases are separated by spaces and cannot be distinguished. The
following code should separate the phrases with commas:
declare -a arr
arr[1]='exercise book' arr[3]=ruler arr[5]=pencil
IFS=,
echo "${arr[@]}"
echo "${arr[*]}"
The output is now:
exercise book ruler pencil
exercise book, ruler, pencil
IFS means Internal Field Separator. It has been assigned a comma. Note the use
of double quotes for ${arr[@]} and ${arr[*]} in the echo commands. Commas have
been included for the * subscript and not for the @ subscript. There is still
another problem: in the second output line, where commas have been employed,
spaces have not been displayed. So, @ and * are not synonyms all the time.
However, it is possible to separate with comma and space – see below.

Displaying Indices of Indexed Array

The expression, ${!name[@]} or ${!name[*]} returns the indices of an array as a
list, separated by spaces. Note the use and position of the exclamation sign
(!). The following code shows the use of these expressions:
arr[1]='exercise book' arr[3]=ruler arr[5]=pencil

echo ${!arr[@]}
echo ${!arr[*]}
The output is:
1 3 5
1 3 5

Length of Indexed Array

The length of the array is given by:
${#name[subscript]}
Where name is the name such as arr, that the programmer gave to the array; the
subscript is the highest index (length – 1) for the element whose value is set.
Note the use and position of the symbol, #. The following code illustrates
this:
arr=(pen 'exercise book' "textbook" ruler 42 pencil)

echo ${#arr[5]}
The output is 6. Even if some or all of the lower elements are not present, the
length would still be highest_index + 1. The following code illustrates this:
declare -a arr

arr[3]=ruler
arr[5]=pencil

echo ${#arr[5]}
The output is still 6, even though no element is there, for index 0, index 1,
index 2, and index 4.

Number of Elements of Indexed Array

As seen above, the number of elements in the array can be less than the array’s
length. This is because the values of some elements below the last element have
not been created or have been unset. The expression gives the number of
elements that are set in an indexed array, ${#arr[@]} or ${#arr[*]}, as shown
in the following code:
arr[1]='exercise book' arr[3]=ruler arr[5]=pencil

echo ${#arr[@]}
echo ${#arr[*]}
The output is:
3
3

Displaying only Indexed Array Set Elements

An index element assigned a value is set, while that which is not assigned a
value is unset. The following code displays only the values that are set:
arr[1]='exercise book' arr[3]=ruler arr[5]=pencil

for ((i=0; i < ${#arr[5]}; ++i)); do
    if [ ! -z "${arr[i]}" ]; then
        printf "${arr[i]}, "
    fi
done
echo
The output is:
exercise book, ruler, pencil,
Note how the unset elements have been identified and eliminated from the
iteration in the condition. Also note that in the condition, ${arr[i]} is in
double-quotes as "${arr[i]}", in order that values containing spaces can be
printed. The printf command is similar to the echo command but does not add a
new line after displaying. It has been possible to separate the values at the
output, with a comma and space, in one line. The last echo would cause the next
output to go to the next line.
A simpler form of the above code is as follows:
arr[1]='exercise book' arr[3]=ruler arr[5]=pencil

for i in ${!arr[@]}; do
    printf "${arr[i]}, "
done
echo
The output is the same. Note the expression for the list after the reserved
word, in. This expression returns the list of indices. So there is no need for
the if-condition here.

Setting and Unsetting Indexed Elements and its Array

Any indexed element that has not been assigned a value is unset. An indexed
element that has a value assigned to it is set. Now, an element may be
intentionally unset, as the following script shows:
arr[1]='exercise book' arr[3]=ruler arr[5]=pencil

unset arr[3]

for i in ${!arr[@]}; do
    printf "${arr[i]}, "
done
echo
The output is:
exercise book, pencil,
“ruler” has not been displayed. The syntax to unset an element is:
unset arrayName[subscript]
The syntax to remove or unset the entire array is:
unset arrayName
or
unset arrayName[@]
or
unset arrayName[*]
In the following code, the whole array is unset:
arr=(pen 'exercise book' "textbook" ruler 42 pencil)

unset arr

echo "${arr[*]}"
The output is nothing (an empty line) because the whole array has been unset.

Associative Array

As indicated above, an example of an associative array written on paper, is:
ink => pen
soft paper => exercise book
hard paper => text book
plastic => ruler
special paper => 42
wood => pencil
There are 6 elements, each consisting of a key/value pair. For the first
element, “ink” is the key and “pen” is the value; for the second element, “soft
paper” is the key and “exercise book” is the value; and so on.

Creating an Associative Array

One way to create the above array is as follows:
declare -A arr=([ink]=pen [soft paper]='exercise book' [hard paper]="text book"
[plastic]=ruler [special paper]=42 [wood]=pencil)
Here, arr is the name of the array. The programmer could have given some other
name. Spaces separate the different elements in the array list. If a value
consists of more than one word, it is typed in single or double-quotes. A key
can consist of more than one word. There are 6 key/value pairs in this coded
associative array. A key is placed in square brackets. The value is assigned to
the key, with the assignment operator. ‘-A’ means associative array, and it
should be there.
Another way of creating the above array begins as follows:
declare -A arr
Here, “declare” is a reserved word. ‘-A’ means associative array (while ‘-a’
means indexed array). “arr” is the name of the programmer’s choice. Elements
can then be included as follows:
declare -A arr

arr[soft paper]='exercise book'
arr[plastic]=ruler
arr[wood]=pencil
All the elements (6) should not necessarily be included at the same time. The
rest can be added later. This is adding by assignment. Remember, when any value
is assigned to a variable, there should be no space between the assignment
operator, = and the variable or the value.

Referencing Associative Array Element

The syntax to reference an associative array element is:
${name[subscript]}
Where name is the name of the array, such as arr. Subscript is the key in text
form. In the following code, the values of the elements are read and displayed:
declare -A arr=([ink]=pen [soft paper]='exercise book' [hard paper]="textbook"
[plastic]=ruler [special paper]=42 [wood]=pencil)

echo ${arr[ink]}
echo ${arr[soft paper]}
echo ${arr[hard paper]}
echo ${arr[plastic]}
echo ${arr[special paper]}
echo ${arr[wood]}
The output is:
pen
exercise book
textbook
ruler
42
pencil

Displaying all the Values in Associative Array

To display all the values, ${name[*]} or ${name[@]} can be used. In these
expressions, * or @ is in the place of the key. And with that, instead of
returning the values of the elements, the values of elements present in the
array are returned. The following code illustrates this:
declare -A arr

arr[soft paper]='exercise book' arr[plastic]=ruler arr[wood]=pencil

echo ${arr[@]}
echo ${arr[*]}
The output is,
pencil exercise book ruler
pencil exercise book ruler
The order of values at the output does not have to correspond to the order in
the associative array. Notice that @ and * used in this way are synonyms. There
is a problem with the output: the phrases are separated by spaces and cannot be
distinguished. The following code separates the phrases with commas:
declare -A arr

arr[soft paper]='exercise book' arr[plastic]=ruler arr[wood]=pencil
IFS=,
echo "${arr[@]}"
echo "${arr[*]}"
The output is now:
pencil exercise book ruler
pencil, exercise book, ruler
IFS means Internal Field Separator. It has been assigned a comma. Note the use
of double quotes for ${arr[@]} and ${arr[*]} in the echo commands. Commas have
been included for the * subscript and not for the @ subscript. There is still
another problem: in the second output line, where commas have been employed,
spaces have not been displayed. So, @ and * are not synonyms all the time.
Well, it is possible to separate with comma and space – see below.

Displaying All Keys of Associative Array

The expression, ${!name[@]} or ${!name[*]} returns the keys of an array as a
list, separated by spaces. Note the use and position of the exclamation sign
(!). The following code shows the use of these expressions:
declare -A arr

arr[soft paper]='exercise book' arr[plastic]=ruler arr[wood]=pencil

echo ${!arr[@]}
echo ${!arr[*]}
The output is:
wood soft paper plastic
wood soft paper plastic
The order of the keys of the associative array does not have to be the same as
declared in the array.

Number of Elements of Associative Array

The expression gives the number of elements that are set in an associative
array, ${#arr[@]} or ${#arr[*]}, as shown in the following code:
declare -A arr

arr[soft paper]='exercise book' arr[plastic]=ruler arr[wood]=pencil

echo ${#arr[@]}
echo ${#arr[*]}
The output is:
3
3
Note the use and position of the symbol, #.

Displaying only Associative Array Set Elements

A key element assigned a value is set, while that which is not assigned a value
is unset. The following code displays only the values that are set:
declare -A arr

arr[ink]=pen
${arr[soft paper]}; arr[soft paper]='exercise book'
${arr[hard paper]}
arr[plastic]=ruler
${arr[special paper]}
arr[wood]=pencil

for key in "${!arr[@]}"; do
    printf "${arr[$key]}, "
done
echo
The output is:
pencil, exercise book, pen, ruler,
Again, the output positioning is not in the order that was coded. Note that “$
{!arr[@]}” is in double-quotes so that values containing spaces can be printed.
Note that in ${arr[$key]}, key is preceded by $. The printf command is similar
to the echo command but does not add a new line after displaying. It has been
possible to separate the values at the output, with a comma and space, in one
line. The last echo would cause the next output to go to the next line.

Setting and Unsetting Associative Array Elements and its Array

Any key element that has not been assigned a value is unset. A key element that
has a value assigned to it is set. Now, an element may be intentionally unset,
as the following script shows:
declare -A arr

arr[soft paper]='exercise book' arr[plastic]=ruler arr[wood]=pencil

unset arr[plastic]

for key in "${!arr[@]}"; do
    printf "${arr[$key]}, "
done
echo
The output is:
pencil, exercise book,
“ruler” has not been displayed. The syntax to unset an element is:
unset arrayName[key]
The syntax to remove or unset the entire associative array is:
unset arrayName
or
unset arrayName[@]
or
unset arrayName[*]
In the following code, the whole array is unset:
declare -A arr=([ink]=pen [soft paper]='exercise book' [hard paper]="text book"
[plastic]=ruler [special paper]=42 [wood]=pencil)

unset arr

echo "${arr[*]}"
The output is nothing (an empty line) because the whole array has been
unsetted.

Displaying the Values of an Associated Array

Displaying the Values of an Associated Array
declare -A arr=([ink]=pen [soft paper]='exercise book' [hard paper]="text book"
[plastic]=ruler [special paper]=42 [wood]=pencil)

for value in "${arr[@]}"; do
    echo $value
done
The output is:
pencil
42
exercise book
textbook
pen
ruler
Again, the order in which the values are coded in an associative array does not
have to be the order in which they are displayed. Note that @ has been used
instead of * for the list variable. Also, double quotes have been used for the
list variable.

Conclusion

An array is a list, either numbered or keyed. When the array is numbered, it is
an indexed array. When the values are located by keys, it is an associative
array. With the indexed array, numbering begins from zero. In computing, the
array has to be coded. The programmer needs to know how to create the array. He
needs to know how to add elements to the array and delete elements from the
array. He needs to be able to determine the number of elements in the array.
And he needs to know how to delete the array.


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
