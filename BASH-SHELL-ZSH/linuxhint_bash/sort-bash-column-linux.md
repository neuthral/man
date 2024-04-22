





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How to Sort in Linux Bash by Column

1 year ago
by John_Otieno
The sort command available in Linux allows users to perform sorting operations
on a file or an input. The sort command is handy when we want to get an ordered
output of a file ascending, descending, or custom-defined sort order.  By
default, the sort command does not alter the original file unless the output is
redirected back to the file.
This article covers how to use the sort command to perform sorting operations
on specific columns in a file.

Basic Usage

The sort command is simple to use and very useful in daily Linux operations.
The general syntax of the command is as:
$ sort [options] file
The options you pass to the command modifies how the file is sorted and the
specific conditions to sort the target file. You can omit the options to use
the default sorting parameters.
By default, the sort command:

* Sorts the alphabets in ascending order.
* Letters come after numerical values
* Assigns higher precedence to lowercase letters than to uppercase letters.

For example, to sort a file without options:
$ sort treks.txt
Once we run the sort command against the file, we get the information sorted in
alphabetical order (ascending).
NOTE: Numerical values take precedence as from the example above.

Sort Command Options

You can use the following options in conjunction with the raw command to modify
how the values are sorted.

* -n – sorts in numerical values.
* -h – compares human-readable numbers such as 1k, 1G
* -R – sort in random order but group the identical keys.
* -r – sort the values in reverse (descending order).
* -o – save ouput to a file
* -c – check if the input file is sorted; do not sort if true.
* -u – show unique values only.
* -k – sort the data via a specific key (useful when sorting columnar data).

Those are some popular options you can tweak to get the best-sorted result. For
more options, check the manual.

How to Sort In Linux Bash By Numerical Values


How to Sort In Linux Bash By Reverse Order

To sort input in reverse order, we use the -r flag. For example:
$ sort -r treks.txt
The command above will sort in ascending alphabetical order (numerical values
first) and reverse order.

How to Sort In Linux Bash by Column

Sort allows us to sort a file by columns by using the -k option. Let us start
by creating a file with more than one column. In sort, we separate a column by
a single space.
In the example file below, we have six columns.
To sort the captains’ file above by their century, we can specify the -
k followed by the column number as:
$ sort -k 5 captains.txt
Once we specify the column to sort the data, the sort command will try to sort
the values in ascending order. In the example above, the command sorts the
values from the earliest century to the latest.
To sort by the first name, set the sort column as 1:
$ sort -k 1 captains.txt

How to Save Sort Output to a File

To save the sorted output to a file, we can use the -o option as:
$ sort -k 5 -o captains_century captains.txt
The command above will sort the captains.txt file by the 5th column and save
the result to the captains_century.txt file.

Conclusion

That is the end of this tutorial on the sort command in Linux. We covered the
basics of using the sort command to get the most out of your sorted data. Feel
free to explore how you can use the sort command.


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
