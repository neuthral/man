




















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash jq command

4 years ago
by Fahmida_Yesmin
JSON data are used for various purposes. But JSON data can’t be read easily
from JSON file by using bash script like other normal files. jq tool is used to
solve this problem.jq command works like sed and awk command, and it uses a
domain specific language for working with JSON data. jq is not a built-in
command. So, you have to install this command for using it. How you can install
and apply jqcommand for reading or manipulating JSON data is shown in this
tutorial.


jq installation

Run the following command to install jq on Ubuntu.
$ sudo apt-get install jq

Reading JSON data

Suppose, you have declared a JSON variable named JsonData in the terminal and
run jq command with that variable to print the content of that variable.
$ JsonData='[{"Book":"PHP 7"}, {"Publication":"Apress"},
{"Book":"React 16 Essentials"},{"Publication":"Packt"} ]'
$ echo "${JsonData}" | jq '.'

Reading JSON data with –c option

-c option uses with jq command to print each JSON object in each line. After
running the following command, each object of JsonData variable will be
printed.
$ echo "${JsonData}" | jq -c  '.[]'

Reading a JSON file

jq command can be used for reading JSON file also. Create a JSON file named
Students.json with the following content to test the next commands of this
tutorial.

Students.json

[
{
"roll": 3,
"name": "Micheal",
"batch": 29,
"department": "CSE"
},
{
"roll": 55,
"name": "Lisa",
"batch": 34,
"department": "BBA"
},
{
"roll": 12,
"name": "John",
"batch": 22,
"department": "English"
}
]
Run the following command to read Students.json file.
$ jq ‘.’ Students.json

Reading JSON file with ‘|’

You can use ‘|’ symbol in the following way to read any JSON file.
$ cat Students.json   | jq '.'

Reading single key values

You can easily read any particular object from a JSON file by using jq command.
In Students.json, there are four objects. These are roll, name, batch, and
department. If you want to read the value of departmentkey only from each
record then run jq command in the following way.
$ jq '.[] | .department' Students.json

Reading multiple keys

If you want to read two or more object values from JSON data then mention the
object names by separating comma (,) in the jq command. The following command
will retrieve the values of name and department keys.
$ jq '.[] | .name, .department' Students.json

Remove key from JSON data

jq command is used not only for reading JSON data but also to display data by
removing the particular key. The following command will print all key values of
Students.json file by excluding batch key. map and del function are used in jq
command to do the task.
$ jq 'map(del(.batch))' Students.json

Mapping Values

Without deleting the key from JSON data, you can use map function with jq
command for various purposes. Numeric values of JSON data can be increased or
decreased by map function. Create a JSON file named Number.json with the
following content to test the next commands.
[ 40,34,12,67,45]
Run the following command to add 10 with each object value of Numbers,json.
$ jq 'map(.+10)' Numbers.json
Run the following command to subtract 10 from each object value of
Numbers,json.
$ jq 'map(.-10)' Numbers.json

Searching values by index and length

You can read objects from JSON file by specifying the particular index and
length. Create a JSON file named colors.json with the following data.
["Red","Green","Blue","Yellow","Purple"]
Run the following command to read two values starting from the third index of
colors.json file.
$ jq '.[2:4]' colors.json
You can specify the length or starting index to read data from JSON file. In
the following example, the number of data value is given only. In this case,
the command will read four data from the first index of colors.json.
$ jq '.[:4]' colors.json
You can specify the starting point only without any length value in jq command
and the value can be positive or negative. If the starting point is positive
then the index will count from the left side of the list and starting from
zero. If the starting point is negative then the index will count from the
right side of the list and starting from one. In the following example, the
starting point is -3. So, the last three values from the data will display.
$ jq '.[-3:]' colors.json
When you will work with JSON data and want to parse or manipulate data
according to your requirements then jq command will help you to make your task
easier.


About the author


Fahmida Yesmin

I am a trainer of web programming courses. I like to write article or tutorial
on various IT topics. I have a YouTube channel where many types of tutorials
based on Ubuntu, Windows, Word, Excel, WordPress, Magento, Laravel etc. are
published: Tutorials4u_Help.
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
