





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Understanding Associative Arrays in Linux Bash with Examples

3 years ago
by Karim_Buzdar
Associative arrays are an abstract data type that can be considered as
dictionaries or maps. How they differ from other arrays is that they hold the
key-value pairs where the keys can be arbitrary and user-defined strings
instead of the usual index numbers. Associate arrays have two main properties:

* Each key in the array can only appear once. You can think of it as a unique
  ID for a user in a list.
* A value can appear more than once in an array. For example, two persons in a
  list can have the same name but need to have different user IDs.

In this article, we will explain how you can declare and initialize associative
arrays in Linux bash. We will further elaborate on the power of the associative
arrays with the help of various examples.
We have run the examples mentioned in this article on a Debian 10 Buster
system. However, you can easily replicate on almost all Linux distros.

Verifying the Pre-requisites

For using Associative Arrays on Linux Bash, your GNU Bash version has to be
equal to or higher than version 4. Open your Linux Terminal by accessing it
through the Application Launcher search. Then enter the following command to
check your installed version of bash:
$ bash --version
My current bash version is 5.0.3 so I am good to go. In case your bash version
is less than 4, you can upgrade bash by running the following command as sudo:
$ sudo apt-get install --only-upgrade bash

Declaring an Associative Array and Initialize It

Declaring an Associative array is pretty simple in bash and can be be done
through the declare command:
$ declare -A “ArrayName”
In our example, we will be declaring an array variable named sampleArray1 as
follows:
$ declare -A sampleArray1
The next step is to initialize the required values for your array. In our
example, we want to have an array where values are a few country names and the
keys are their relevant country name abbreviations. Here, we will feed the
array values, one by one as follows:
$ ArrayName[key]=Value
Example:
$ sampleArray1[CHN]=China
$ sampleArray1[JPN]=Japan
$ sampleArray1[KOR]=Korea
$ sampleArray1[TWN]=Taiwan
$ sampleArray1[TH]=Thailand
A quick alternative is to declare and initialize an array in a single bash
command as follows:
$ declare -A ArrayName=( [key1]=Value1 [key2]=Value2 [Key3]=Value3…. )
Here is how we can declare and initialize our mentioned array, alternatively,
as follows:
$ declare -A sampleArray1=( [CHN]=China [JPN]=JAPAN [KOR]=Korea [TWN]=Taiwan
[TH]=Thailand )
Now we will present some examples that will elaborate on what all you can do
with Associative Arrays in bash:

Example1: Accessing the array keys and values

In this example we will explain how you can:

* Print a value against a key
* Print all array keys at once
* Print all array values at once

And,

* Print all the key-value pairs at once

Print
You can print a value against a keyby using the following command syntax:
$ echo ${ArrayName[keyName]}
Here is how we can access a country’s full name by providing the country’s name
abbreviation, from our sampleArray1:
$ echo ${sampleArray1[CHN]}
$ echo ${sampleArray1[TWN]}
If you are interested in printing all keys of your associative array, you can
do so using the following syntax:
$ for key in "${!ArrayName[@]}"; do echo $key; done
The following command will print all country name abbreviations from my
sampleArray1 by
using a for loop:
$ for key in "${!sampleArray1[@]}"; do echo $key; done
Another alternative to printing all keys from the array is by using parameter
expansion. The following command will print all keys in the same line:
$ echo "${!sampleArray1[@]}"
If you are interested in printing all the array values at once, you can do so
by using the for loop as follows:
$ for val in "${ArrayName[@]}"; do echo $val; done
The following command will print all full country names stored in my
sampleArray1:
$ for val in "${sampleArray1[@]}"; do echo $val; done
Another alternative to printing all values from the array is by using parameter
expansion. The following command will print all values in the same line:
$ echo "${sampleArray1[@]}"
The next useful example will print all the key-value pairsat once by using the
for loop as follows:
$ for key in "${!sampleArray1[@]}"; do echo "$key is an abbreviation for
 ${sampleArray1[$key]}"; done
You can, of course, make this information retrieval more useful in your complex
and meaningful bash scripts.

Example 2: Counting Array items

The following command can be used to count and print the number of elements in
your associative array:
$ echo "${#ArrayName[@]}"
The output of the following command shows that I have five items in my
sampleArray1:
$ echo "${#sampleArray1[@]}"

Example 3: Adding new data in Array

If you want to add an item to an array after you have already declared and
initialized it, this is the syntax you can follow:
$ ArrayName+=([key]=value)
In my example, I want to add another country along with its county name
abbreviation so I will use the following command:
$ sampleArray1+=([AL]=Alabama)
Echoing the array values now suggests that the new country is added to my
array:
$ echo "${sampleArray1[@]}"

Example 4: Deleting Item from Array

By unsetting an entry from the associative array, you can delete it as an array
item. This is the unset syntax use can use in order to do so:
$  unset ArrayName[Key]
In my example, I want to remove the key-value pair “AL-Alabama” from my array
so I will unset the “AL” key in my command:
$  unset sampleArray1[AL]
Echoing the array values now suggests that the AL-Alabama key-value is now
removed from my array:
$ echo "${sampleArray1[@]}"

Example 5: Verifying If an item exists in the array

By using the if condition in the following manner, you can verify if an item is
available in your associative array or now:
$ if [ ${ArrayName[searchKEY]+_} ]; then echo "Exists"; else echo "Not
available"; fi
For example, if I check if the recently deleted AL-Alabama item exists in my
array, the following message will be printed:
$ if [ ${sampleArray1[AL]+_} ]; then echo "Exists"; else echo "Not available";
fi
If I check for an item that exists, the following result will be printed:
$ if [ ${sampleArray1[JPN]+_} ]; then echo "Exists"; else echo "Not available";
fi

Example 6: Deleting an Array

You can delete an Associative Array from your bash memory by using the unset
command as follows:
$ unset ArrayName
By using the following simple command, I will delete my sampleArray1 from the
memory:
$ unset sampleArray1
Now, when I try to print all the array values through the following command, I
get none.
$ echo "${sampleArray1[@]}"
By using these examples in your Linux bash scripts, you can use the power of
the associative arrays to achieve a solution to many complex problems.


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
