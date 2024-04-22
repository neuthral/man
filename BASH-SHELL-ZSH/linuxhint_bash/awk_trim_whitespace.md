





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Awk Trim Whitespace

3 weeks ago
by Karim_Buzdar
“When working in the IT industry, you can come across thousands of files
containing a lot of lines of code or huge amounts of data. Though the data
itself could be a contributing factor to the file size, whitespaces also
compound the size greatly. With the increased file size, you could run into
issues when storing these files or transferring them to your colleagues. So,
it’s imperative that you remove them to better control the file size, but
first, let’s take a look to understand them in detail.”

What is a Whitespace?

Whitespace is the space between two printable characters. It can either be
within a horizontal line or vertically separating lines. In other words, space
between words, any blank lines, the nbsp tag along with tabs can be considered
as whitespaces. The blank spaces at the start and/or at the end of the lines
are also considered whitespaces.
In order to preserve data sanity, programmers end up writing code which is
responsible for removing these whitespaces when storing data. The following
cases can prompt the removal of whitespaces:

* Reformatting/refactoring source code
* Clean up data
* Simplify any command-line outputs
* Reduce file size

It is possible to manually remove whitespaces if there are a handful of lines
of data in the file. But, when the file contains hundreds of lines, it can
become very difficult to remove them manually. To overcome this, we can employ
the many command-line tools available to us, e.g., sed, cut, tr, and awk. Out
of these, awk is the more powerful command. Let’s explore it further.

What is Awk?

Awk is a very powerful scripting language used for data manipulation and report
generation. The awk command is the abbreviation of the first initials of each
of the three creators Aho, Weinberger, and Kernighan. Awk empowers its users to
define variables, strings, numeric functions and arithmetic operators, as well
as create formatted reports, among many others.
In this article, we will explore using the awk command for trimming whitespaces
from your files. After going through the guide, you’ll know how to:

* Trim all whitespaces in any file.
* Trim both the leading and trailing whitespaces.
* Trim all leading whitespaces.
* Trim all trailing whitespaces.
* Replace multiple spaces with a single space.

The scenarios demonstrated in this article are performed on Ubuntu 22.04 Jammy
Jellyfish system. These commands are also executable on other distributions as
well.

Sample File

For this guide, we will be using a text file named “asd.txt”. The placeholder
contents of the sample file look like this:
Now, let’s begin.

How to View All the Whitespaces in Your File?

To understand whitespaces better, let’s first see how we can identify
whitespaces in a file. For this, you need to pipe the output from the cat
command through the tr command as such:
$cat asd.txt | tr “ ” “*” | tr “\t” “&”
This command will replace spaces with asterisks and tabs spaces with the
“&”symbol. As soon as this executes, you will be able to see all the
whitespaces in your file as such:
Now let’s explore the usage of the awk command.

Trimming All Whitespaces

For our first scenario, we remove all the whitespaces from our sample file. To
achieve this, we need to pipe the output of the cat command to the awk command
as such:
$ cat asd.txt | awk '{ gsub(/ /,""); print }'
Here:

* gsub stands for global substitution, used for substituting whitespaces.
* The double forward slashes (/ /) represent the whitespace.
* “” the double quotation marks are used to trim the strings.

So, with the above command, we are substituting all whitespaces (/ /) with
nothing (“”). With the output from the command above, you can see that all the
whitespaces have been removed.

Trimming Leading and Trailing Whitespaces From Your Document

From the last output, we can see that the whitespaces have been removed,
leaving behind tabs and empty lines. We can update the command used in the last
example to take care of the leading and trailing whitespaces along with tabs as
such:
$cat asd.txt | awk '{ gsub(/^[ \t]+|[ \t]+$/, ""); print }'
Using elements from the earlier command, you can verify that the leading and
trailing whitespaces have been removed.
$cat asd.txt | awk '{ sub(/^[ \t]+|[ \t]/, ""); print }' | tr " " "*" |
tr "\t" "&"
Here are the commands you can use to remove these spaces separately,
respectively.

Removing Only Leading Whitespaces

$cat asd.txt | awk '{ sub(/^[ \t]+/, ""); print }'

Removing Only Trailing Whitespaces

$cat asd.txt | awk '{ sub(/[ \t]+$/, ""); print }'

Bonus: Replace Multiple Spaces With a Single Space

In order to replace multiple spaces with a single one or nothing, you can use
the awk command as such:
$cat asd.txt | awk '{ gsub(/[ ]+/,””); print }'
Using the tr command, we can see that the whitespaces have been removed.

Conclusion

So, with these demonstrations, we have explored various ways where we can use
the awk command to trim the whitespaces. Removing them could come in handy for
various reasons.
If you run into any issues using it, feel free to reach out to us using the
comments section below, and we’ll be happy to help.


About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
