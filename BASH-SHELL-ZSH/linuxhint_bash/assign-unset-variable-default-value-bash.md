





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Assign Default Value if Variable Unset

8 months ago
by Sidratul_Muntaha
In Bash programming, variables play a vital part in transforming the script to
a modern standard. Variables are named symbols representing a string or numeric
value. Check out this in-depth_guide_on_Bash_variables for more info.
When creating a Bash variable, it must have a value. However, we can use some
tricks to set a default value if the variable is not set (or null). This guide
will demonstrate how to do just that.

Default shell variable values


Method 1 – Setting variable value (if unset)

Let’s get started with the following demonstration. Run the following command:
$ echo $country
The command will return nothing as the value of the country wasn’t set in the
first place. If the value of the variable is unset, using the following
technique, we can assign a value.
$ echo ${country=Greenland}
Here, Bash will check if the variable country has any value stored. As the
variable wasn’t set before, it will assign the value “Greenland” to it.

Method 2 – Setting variable value (if unset)

The next method will be similar but involves a different syntax. Have a look at
the following example:
$ echo ${country:-Greenland}
Here,

* Does the variable country have a value?

  o If yes, then print the value.
  o If no, then use the default value “Greenland”.


Basically, we’re setting a default value that will be used when the variable is
not set or have a null value.

Method 3 – Assigning default value to empty variable

This section will showcase how to assign the default value to a variable if the
variable is empty. The command structure is as follows.
$ {<variable>:=<default_value>
Let’s implement it in an example.
$ echo ${country:=Greenland}
Here,

* Is the variable country empty?

  o If yes, then assign the value “Greenland”.
  o If no, then no new value is assigned.


We can also demonstrate it using the following commands. Run them one by one:
$ echo ${country:=Greenland}

$ country=Iceland

$ echo ${country:=Greenland}

$ unset country

$ echo ${country:=Greenland}
Here,

* Command 1: As the variable country isn’t set, it will assign the default
  value “Greenland”.
* Command 2: The country value is updated to “Iceland”.
* Command 3: The variable country already contains the value “Iceland”, so
  “Greenland” not assigned.
* Command 4: Clears the content of the variable country.
* Command 5: Prints “Greenland” as country doesn’t have any value (unset from
  the last step).


Final thoughts

This brief guide showcased how to assign a default value if a Bash variable was
not set or assigned no value. This technique can be useful in various
situations, for example, handling errors when trying to access undefined
variables.
Check out our Bash_programming section for more tutorials on various Bash
concepts with examples. If you’re new to Bash programming, check out this
excellent Bash_scripting_tutorial_for_beginners.
Happy Computing!


About the author


Sidratul Muntaha

Student of CSE. I love Linux and playing with tech and gadgets. I use both
Ubuntu and Linux Mint.
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
