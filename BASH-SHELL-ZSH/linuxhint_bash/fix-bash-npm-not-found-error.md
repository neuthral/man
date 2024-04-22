





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How Do I Fix Bash npm Not Found?

9 months ago
by Sidratul_Muntaha
If you’re working with JavaScript and Node.js, you’re already familiar with
npm. The term npm refers to two things. More on the official_Node.js
documentation.

* An online repository for publishing open-source Node.js projects.
* A command-line utility to manage Node.js packages, manage versions and
  dependencies.

Whenever you install Node.js, it installs the npm package manager by default.
For some reason, however, you may be facing the issue that bash isn’t
recognizing npm as a valid command.
In this troubleshooting guide, we’ll have a look at possible steps you can take
to troubleshoot the error. I’ll be using Ubuntu for the demonstration. However,
the key principles will apply to any other Linux distro.

Bash: npm: command not found

Bash is the default shell on most Linux distros. When we run a command on the
terminal, it goes to Bash. The command is then interpreted and executed.
However, if the command is looking for a tool that Bash doesn’t recognize, it
will show the error.
As the output suggests, Bash can’t find the command “npm” related to any Bash
alias or tool. We can deduce a couple of possible scenarios:

* The npm isn’t installed.
* js isn’t installed.
* Value of PATH (or related environment variable) changed.
* Permission issues.
* An old version of Node.js was installed.


Fresh Node.js installation

Our very first solution involves re-installing Node.js and all of its
components from scratch. A corrupted installation or configuration can cause
such an issue in many cases. We’ll remove the existing installation, configure
the Node.js dedicated repo, and make a fresh Node.js installation.
Removing older versions of Node.js
If you have an old version of Node.js installed, then it’s strongly recommended
to upgrade to the latest stable (current or LTS) release. Old software is often
full of bugs and vulnerabilities. A big chunk of cyber-attacks happens because
old software is not updated/patched.
First, remove Node.js using your default package manager. For Ubuntu, APT is
the package manager. Run the following command to remove Node.js and all of its
components:
$ sudo apt autoremove --purge nodejs npm node
Next, run the following commands to remove any residue from the system.
$ sudo rm -rf /usr/local/bin/npm
$ sudo rm -rf /usr/local/share/man/man1/node*
$ sudo rm -rf /usr/local/lib/dtrace/node.d
$ sudo rm -rf ~/.npm
$ sudo rm -rf ~/.node-gyp
$ sudo rm -rf /opt/local/bin/node
$ sudo rm -rf opt/local/include/node
$ sudo rm -rf /opt/local/lib/node_modules
$ sudo rm -rf /usr/local/lib/node*
$ sudo rm -rf /usr/local/include/node*
$ sudo rm -rf /usr/local/bin/node*
Installing the latest Node.js
Our primary goal is to verify that your system has the latest version of
Node.js installed. We already have an in-depth guide on installing_Node.js_and
npm_on_Ubuntu.
In short, run the following commands to set the official Node.js repo for
Ubuntu. When writing this article, the latest current version is Node.js v17.x,
and the latest LTS version is v16.x. Per the recommendation of the Node.js
official website, we’ll be installing the LTS version:
$ curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
Now, install Node.js:
$ sudo apt install nodejs -y
Now, verify if Bash now recognizes npm as a proper command.
$ npm help
If the process is successful, then you’ll get the npm help page. Otherwise, the
problem will persist.

Reset value of PATH

PATH is an important environment variable that many parts of the system rely
on. It tells the shell (and the system) where to look for certain programs.
Whenever we run any command, the shell (Bash, in most cases) searches for the
command in the locations described by PATH. If it’s not found, then it will not
recognize the command, even if the tool is installed properly.
To learn more about the PATH variable, check out this guide on how_to_change
the_PATH_in_Linux.
To see the value of the PATH variable, run the following command:
$ echo $PATH
Alternatively, you can use the following sed command to print the PATH output.
It will put every unique entry in a new line.
$ sed 's/:/\n/g' <<< "$PATH"
Is there any inconsistency in the PATH variable? There will be multiple paths
listed in the PATH variable in most cases. Try setting the PATH variable to its
default state.
$ export PATH=$(getconf PATH)
After fixing the PATH variable, check if Bash can find npm now.
$ npm help
If it fixed the issue, consider manually setting the PATH variable using the
bashrc file. Learn more about exporting_PATH_in_bashrc. In short, add the
following lines to the bashrc file.
$ export PATH=$(getconf PATH)
$ export PATH:$PATH: /usr/local/sbin:/usr/local/bin:/usr/sbin:/sbin
Here,

* The first line sets the value of PATH to its default.
* The second line adds some additional locations to look for binaries. It’s
  optional but recommended for most distros.

Verify if the update was successful.
$ echo $PATH
If you’re using a portable version of Node.js, you also have to make sure that
the binary location is also included in the PATH variable. Otherwise, Bash will
fail to recognize the binary.

Final thoughts

This troubleshooting guide demonstrated some solutions to fix the issue where
Bash cannot find the npm binary. Note that these steps are for general
troubleshooting. If your problem persists after following them, you should seek
expert help. There are massive communities like Stackexchange that can help you
with your situation.
Happy computing!


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
