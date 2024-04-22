





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How do I Sum a Column in AWK?

1 year ago
by Aqsa_Yasin
The AWK scripting language is a very powerful way of manipulating any provided
datasets while staying within a Linux environment. On any specific dataset, you
need to perform many statistical tests to extract useful information from it.
At times, you have a wide range of numbers present in a dataset, and you simply
need to calculate their total. Doing this manually might prove to be very
tedious depending upon the size of the dataset and the range to which these
numbers belong. Therefore, we must have a way of automating this task.
AWK eases this difficulty by providing us with simple commands with the help of
which we can sum up the values present in any given column of a specific
dataset. By running a single command, you can get their sum within a few
seconds. Therefore, the motivation of this article is to show you the method of
calculating the sum of a column in AWK in Ubuntu 20.04 by sharing different
examples with you.

How do I Sum a Column in AWK in Ubuntu 20.04?

We have formulated the following four examples to teach you how to sum a column
in AWK in Ubuntu 20.04. In all of these examples, our main goal will be to
calculate the sum of a column in AWK. However, all four scenarios will differ
slightly from each other.

Example # 1: Calculating the Gross Chocolate Prices:

Suppose a shopkeeper wants to calculate the total cost of single bars of
chocolates from different brands that he has in his store. For that, he simply
needs to sum up the prices of all the chocolates that are available in his
store. We will demonstrate this example using AWK, and for that, the text file
which we have created for our sample data is as follows:
In this text file named “ChocolatePrices.txt”, we have prices of the single
chocolate bars from five diverse brands.
Now, to calculate the gross chocolate price, the shopkeeper will have to
execute the command stated below:
$ cat ChocolatePrices.txt | awk ‘{ sum+=$2} END {print sum}’
In this command, the “cat” keyword will be used to read the data file.
“ChocolatePrices.txt” represents the name of the text file from which we have
to read the data. Then we have the “awk” keyword followed by the “sum”
expression that will actually calculate the sum from the second column of our
dataset, and then the “print” command will be used to display the results on
the terminal.
The gross chocolate price is 240, as shown in the following image:

Example # 2: Calculating the Gross Employee Salaries of all the Employees
Working within an Organization:

Suppose a business owner wants to calculate the total expense that he has to
bear due to giving salaries to all the employees working within his
organization. For that, he simply needs to sum up the wages of all the
employees. We will demonstrate this example using AWK, and for that, the text
file which we have created for our sample data is as follows:
In this text file named “EmployeeSalaries.txt”, we have the salaries of five
different employees working within a specific organization.
Now, to calculate the gross employee salaries, the business owner will have to
execute the command stated below:
$ cat EmployeeSalaries.txt | awk ‘{ sum+=$2} END {print sum}’
In this command, the “cat” keyword will be used to read the data file.
“EmployeeSalaries.txt” represents the name of the text file from which we have
to read the data. Then we have the “awk” keyword followed by the “sum”
expression that will calculate the sum from the second column of our dataset,
and then the “print” command will be used to display the results on the
terminal.
The gross employee salary is 220000 as shown in the following image:

Example # 3: Calculating the Gross Prices of all the Vegetables and Fruits
Present in a Grocery Store:

Suppose a retailer wants to calculate the total cost of all the vegetables and
fruits that he has in his grocery store. For that, he simply needs to sum up
the prices of all the fruits and vegetables that are available in his grocery
store. We will demonstrate this example using AWK, and for that, the text file
which we have created for our sample data is as follows:
In this text file named “GroceryStore.txt”, we have the prices of seven
different fruits and vegetables.
Now, to calculate the gross price of all the fruits and vegetables, the
retailer will have to execute the command stated below:
$ cat GroceryStore.txt | awk ‘{ sum+=$2} END {print sum}’
In this command, the “cat” keyword will be used to read the data file.
“GroceryStore.txt” represents the name of the text file from which we have to
read the data. Then we have the “awk” keyword followed by the “sum” expression
that will actually calculate the sum from the second column of our dataset, and
then the “print” command will be used to display the results on the terminal.
The gross price of the fruits and vegetables is 700, as shown in the following
image:

Example # 4: Calculating the Gross Utility Bills of a Specific Household:

Suppose a person wants to calculate the total money that he spends every month
on his utility bills. For that, he simply needs to sum up the utility bills of
all those services that he avails within his household. We will demonstrate
this example using AWK, and for that, the text file which we have created for
our sample data is as follows:
In this text file named “UtilityBills.txt”, we have the monthly bills of four
different household utilities.
Now, to calculate the gross utility bills of a specific household, the person
will have to execute the command stated below:
$ cat UtilityBills.txt | awk ‘{ sum+=$2} END {print sum}’
In this command, the “cat” keyword will be used to read the data file.
“UtilityBills.txt” represents the name of the text file from which we have to
read the data. Then we have the “awk” keyword followed by the “sum” expression
that will actually calculate the sum from the second column of our dataset, and
then the “print” command will be used to display the results on the terminal.
The gross utility bill of a specific household is 9700, as shown in the
following image:

Conclusion:

We wanted to highlight the method of calculating the sum of any given column in
AWK in Ubuntu 20.04. For that, we started with a brief justification of why we
need to calculate the sum of a column in the first place. Then, we explained
four different examples to you that serve the very same purpose in different
scenarios. After looking through these examples, it will be a piece of cake for
you to calculate the sum of a column from any desired dataset in AWK in Ubuntu
20.04.


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
