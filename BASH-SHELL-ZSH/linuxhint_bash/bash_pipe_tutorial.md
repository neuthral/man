





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash pipe tutorial

3 years ago
by Nicholas_Shellabarger
Your instructor says, “If you put this vertical bar after a command it will
pass the message on to the next.” So, you go ahead and type until reaching a
silent halt before reaching your pointer finger across the keyboard hovering
above the enter key. You breathe and …Time is up! But that doesn’t mean you
don’t have time for a good old bash pipe tutorial, right?
There is always time for pipes. The white rabbit can wait.
Pipes (or pipelines) are one of those things that you learn to use intuitively
through the idiomatic use cases that we know and love but never come around to
fully understand. Lucky enough, today is a good day to dive into the depth of
pipes, don’t you think?
Heads up, in writing this article, I got better at pipes. Hopefully, you do
too.

What are pipes?

A pipe is an enclosed medium that allows flow from one end to another. In the
real-world pipes are used to convey matter, mostly liquid such as water or gas
such as smoke but sometimes convey a mixture of liquid and solids. In a Linux
environment, a pipe is a special file that connects the output of one process
to the input of another process. In bash, a pipe is the | character with or
without the & character. With the power of both characters combined we have the
control operators for pipelines, | and |&.
As you could imagine, stringing commands together in bash using file I/O is no
pipe dream. It is quite easy if you know your pipes.
So, before you start killing it with pipes in bash, see how pipelines can help
you get more done shell script with less code. Read on.

Pipelines

According to the bash_manual_section_on_pipelines_(3.2.2_Pipelines), A pipeline
is a sequence of one or more commands separated by one of the control operators
‘|’ or ‘|&’. That means every command is a pipeline whether or not you use its
pipeline control operators.
When we strip away all of the options in the format for a pipeline:
[time [-p]] [!] command1 [ | or |& command2 ] …
We get:
command1 …
What do you know? We’ve been using pipelines in bash all this time without
knowing. Well, now you know. Anyways, let’s see how we can start to use
pipelines for real with time –p ! and | or &|.

Facts about pipes


* Pipeline time
  A pipeline may begin with time, which reports runtime statistics after
  completion of the pipeline
* Pipeline portable time
  time accepts the option -p for improved portability of runtime statistics,
  replacing tab with single space and converting time to seconds with no unit,
  the output format specified by POSIX
* Pipeline operators and implicit redirection
  By default, only standard output of commands on the left-hand side of the
  operator | is connect to commands on the other side. To have standard error
  connected as well the &| operator may be used. However, it is simply
  shorthand for 2>&1|, which redirects standard error to standard error before
  the pipeline operator.
* List precedence in pipelines
  If the command on the left-hand side of the pipeline operator is a list (
  { command1; command2; …} or (command1;command2;…)), the pipeline waits for
  the list to complete
* Pipeline behavior under lastpipe
  Commands in a pipeline are executed in subshells unless the lastpipe shopt is
  enabled. If lastpipe is enabled, the command on the far-right side is
  executed as a command belonging to the current shell. See Test lastpipe in
  Tests.
* Custom time format
  time output may be customized using the bash variable TIMEFORMAT. See Test
  time format in Tests.
* Pipeline behavior under pipefail
  By default, all commands in the pipeline are executed without regard of the
  exit status of commands on to the left and the exit status of the right-most
  command is return. However, if pipefail is enabled, the pipeline will
  terminate abruptly if any of its commands returns a non-zero exit status.
  Also, the pipeline exit status will be that of the last command exited with a
  non-zero exit status.


How to use pipes by example

As mentioned in What are pipes, bash has two control operators for pipelines,
namely | and |&. That is the groundwork. Let’ go into how to use pipes.

Using | pipes

This is the standard pipeline that most bash programmers have touched sometime
or another. It only passes standard output right, down the pipeline.
#!/bin/bash
## test-pipeline-standard
## version 0.0.1 - initial
##################################################
upper() { { local str ; read str ; }
echo error in upper 1>&2
echo ${str^^}
}
lower() { { local str ; read str ; }
echo error in lower 1>&2
echo ${str,,}
}
test-pipeline-standard() {

echo ${@} | lower | upper
}
##################################################
if [ ! ]
then
true
else
exit 1 # wrong args
fi
##################################################
test-pipeline-standard ${@}
##################################################
## generated by create-stub2.sh v0.1.2
## on Tue, 23 Jul 2019 13:28:31 +0900
## see <https://github.com/temptemp3/sh2>
##################################################
Source: test-pipeline-standard.sh
Commands
bash test-pipeline-standard.sh Big
Output
error in lower
error in upper
BIG

Using |& pipes

This is the non-standard pipeline that most bash programmers seldom touch. It
implicitly redirects standard error to standard output and proceeds as in the
standard pipeline.#!/bin/bash
## test-pipeline-time2
## version 0.0.1 – initial
##################################################
func() { read -t ${t} input
time -p {
echo ${input-1} 1>&2
sleep 1
echo $(( ${input-1} + 1 ))
}
}
test-pipeline-time2() {
t=0 ; time echo 1 | func | func | func
t=1 ; time echo 1 | func | func | func
t=2 ; time echo 1 | func | func | func
t=3 ; time echo 1 | func | func | func
t=4 ; time echo 1 | func | func | func
}
##################################################
if [ ${#} -eq 0 ]
then
true
else
exit 1 # wrong args
fi
##################################################
test-pipeline-time2
##################################################
## generated by create-stub2.sh v0.1.2
## on Tue, 23 Jul 2019 22:13:53 +0900
## see <https://github.com/temptemp3/sh2>
#!/bin/bash
## test-pipeline-nonstandard
## version 0.0.1 - initial
##################################################
shopt -s expand_aliases
alias handle-nonstandard-pipepline-error='
{
case ${str} in
error*) {
echo ${str} 1>&2
echo exiting ${FUNCNAME} ... 1>&2
} ;;
*) {
payload
} ;;
esac
}
'
upper() { { local str ; read str ; }
payload() {
echo ${str^^}
}
handle-nonstandard-pipepline-error
}
lower() { { local str ; read str ; }
_
payload() {
echo ${str,,}
}
handle-nonstandard-pipepline-error
}
test-pipeline-nonstandard() {
echo pipeline with error in lower
_() { echo error in lower 1>&2 ; }
echo ${@} |& lower |& upper
echo " "
echo pipeline without error in lower
_() { true ; }
echo ${@} |& lower |& upper
}
##################################################
if [ ! ]
then
true
else
exit 1 # wrong args
fi
##################################################
test-pipeline-nonstandard ${@}
##################################################
## generated by create-stub2.sh v0.1.2
## on Tue, 23 Jul 2019 13:28:31 +0900
## see <https://github.com/temptemp3/sh2>
##################################################
Source: test-pipeline-nonstandard.sh
Commands
bash test-pipeline-nonstandard.sh Big
Output
pipeline with error in lower
error in lower
exiting upper ...

pipeline without error in lower
BIG

Using pipes with time

Timing pipelines can be tricky at times especially when commands on the right-
hand side don’t depend on input from the left-hand side. In this case, commands
are executed in parallel. In the following example pipeline timing is affected
timing parameters.
#!/bin/bash
## test-pipeline-time2
## version 0.0.1 - initial
##################################################
func() { read -t ${t} input
time -p {
echo ${input-1} 1<&2
sleep 1
echo $(( ${input-1} + 1 ))
}
}
test-pipeline-time2() {
t=0 ; time echo 1 | func | func | func
t=1 ; time echo 1 | func | func | func
t=2 ; time echo 1 | func | func | func
t=3 ; time echo 1 | func | func | func
t=4 ; time echo 1 | func | func | func
}
##################################################
if [ ${#} -eq 0 ]
then
true
else
exit 1 # wrong args
fi
##################################################
test-pipeline-time2
##################################################
## generated by create-stub2.sh v0.1.2
## on Tue, 23 Jul 2019 22:13:53 +0900
## see <https://github.com/temptemp3/sh2>
##################################################
Source: test-pipeline-time2.sh
Output:
1
1
1
real 1.02
user 0.01
sys 0.01
real 1.02
user 0.01
sys 0.00
2
real 1.03
user 0.00
sys 0.01

real    0m1.070s
user    0m0.045s
sys     0m0.045s
1

real 1.02
user 0.00
sys 0.01
real 1.02
user 0.00
sys 0.00
1
real 1.02
user 0.00
sys 0.01

real    0m2.065s
user    0m0.015s
sys     0m0.061s
1
real 1.02
user 0.01
sys 0.00
2

real 1.03
user 0.01
sys 0.00
1
real 1.03
user 0.00
sys 0.01

real    0m3.067s
user    0m0.045s
sys     0m0.030s
1
real 1.02
user 0.03
sys 0.01
2
real 1.02
user 0.00
sys 0.01
3
4
real 1.03
user 0.00
sys 0.01

real    0m3.112s
user    0m0.045s
sys     0m0.045s
1
real 1.01
user 0.00
sys 0.01
2
real 1.01
user 0.00
sys 0.01
3
4
real 1.02
user 0.00
sys 0.01

real    0m3.088s
user    0m0.000s
sys     0m0.060s

Using pipes with !

Pipelines can be leveraged to implement certain control logic if an expected
behavior is known. Such is the case pipelines with commands that fail and
pipefail set on. In the following example we show how to exit a loop if all
commands succeed.
#!/bin/bash
## test-pipeline-negation2
## version 0.0.1 - initial
##################################################
func() {
echo -n ${1} 1>&2
test ! $(( RANDOM % 10 )) -eq 0
return
}
test-pipeline-negation2() {
set -o pipefail
local -i i=1
while :
do
! func $(( ${i} % 10 )) | func $(( ( i + 1 ) % 10 )) | func $(( ( i - 1 ) % 10
)) && break
i+=1
done
}
##################################################
if [ ${#} -eq 0 ]
then
true
else
exit 1 # wrong args
fi
##################################################
time test-pipeline-negation2
##################################################
## generated by create-stub2.sh v0.1.2
## on Wed, 24 Jul 2019 13:20:10 +0900
## see <https://github.com/temptemp3/sh2>
##################################################
Source: test-pipelines-mixed.sh
bash test-pipeline-negation2.sh
Output:
120231342453564
real    0m0.202s
user    0m0.000s
sys     0m0.091s

Using mixed pipes

In practice, pipelines are often mixed up.  In the following example, we mix it
up handling non-standard pipeline errors, producing a nice banner, and finish
up with a list of all the errors that came up.
#!/bin/bash
## test-pipelines-mixed
## version 0.0.1 - initial
##################################################
shopt -s expand_aliases
alias handle-nonstandard-pipepline-error='
{
case ${str} in
error*) {
echo ${str} on line $(( RANDOM % LINENO )) >> ${temp}-error-log # handle error
payload
} ;;
*) {
payload
} ;;
esac
}
'
## see also test-pipeline-nonstandard.sh
banner() {
cat << EOF
205f20202020202020202020202020202020202020202020205f20202020
2020202020202020202020202020202020205f5f5f5f5f200a7c207c5f20
5f5f5f205f205f5f205f5f5f20205f205f5f207c207c5f205f5f5f205f20
5f5f205f5f5f20205f205f5f7c5f5f5f202f200a7c205f5f2f205f205c20
275f2060205f205c7c20275f205c7c205f5f2f205f205c20275f2060205f
205c7c20275f205c207c5f205c200a7c207c7c20205f5f2f207c207c207c
207c207c207c5f29207c207c7c20205f5f2f207c207c207c207c207c207c
5f29207c5f5f29207c0a205c5f5f5c5f5f5f7c5f7c207c5f7c207c5f7c20
2e5f5f2f205c5f5f5c5f5f5f7c5f7c207c5f7c207c5f7c202e5f5f2f5f5f
5f5f2f200a2020202020202020202020202020202020207c5f7c20202020
20202020202020202020202020202020207c5f7c2020202020202020200a
EOF
}
decode() {
xxd -ps -r
}
func() { read str
payload() {
banner | decode
}
handle-nonstandard-pipepline-error
}
test-pipelines-mixed() {
local temp
temp=$( mktemp )
banner > ${temp}-banner
for row in $( seq $( cat ${temp}-banner | wc -l ) )
do
{ echo error in ${FUNCNAME} 1>&2 ; } |& func | sed -n "${row}p"
done
echo =error-log=
cat ${temp}-error-log | head -n 3
echo ...
}
##################################################
if [ ${#} -eq 0 ]
then
true
else
exit 1 # wrong args
fi
##################################################
test-pipelines-mixed
##################################################
## generated by create-stub2.sh v0.1.2
## on Wed, 24 Jul 2019 13:43:26 +0900
## see <https://github.com/temptemp3/sh2>
##################################################

bash test-pipelines-mixed.sh
Output
_                       _                      _____

| |_ ___ _ __ ___  _ __ | |_ ___ _ __ ___  _ __|___ /

| __/ _ \ '_ ` _ \| '_ \| __/ _ \ '_ ` _ \| '_ \ |_ \

| ||  __/ | | | | | |_) | ||  __/ | | | | | |_) |__) |

\__\___|_| |_| |_| .__/ \__\___|_| |_| |_| .__/____/

|_|                     |_|

=error-log=
error in test-pipelines-mixed on line 21
error in test-pipelines-mixed on line 7
error in test-pipelines-mixed on line 31
...

Tests

It is good practice to write tests to ensure that your code is going to behave
the way it was intended. Here we have a list of tests which you are welcome to
run yourself.

* Test lastpipe – compare pipelines with and without lastpipe enabled
* Test negation – negate the exit status of pipelines
* Test time – time pipeline
* Test time format – customize pipeline runtime statistics
* Test pipefail – run pipelines with pipefail enabled


Test lastpipe

Here is a simple test showing how enabling lastpipe affects the expected
behavior of pipelines in bash. That is, you may opt to allow the last command
in the pipeline to be executed in the current shell using lastpipe.
#!/bin/bash
## test-pipelines-lastpipe
## version 0.0.1 - initial
##################################################
func2() {
x=0
}
func() {
x+=1
}
test-pipelines-lastpipe() {
x=0
func | func | func | func
echo ${x}
func2 | func | func | func
echo ${x}
func | func2 | func | func
echo ${x}
func | func | func2 | func
echo ${x}
func | func | func | func2
echo ${x}
echo enabling lastpipe ...
shopt -s lastpipe
func | func | func | func
echo ${x}
func2 | func | func | func
echo ${x}
func | func2 | func | func
echo ${x}
func | func | func2 | func
echo ${x}
func | func | func | func2
echo ${x}
}
##################################################
if [ ${#} -eq 0 ]
then
true
else
exit 1 # wrong args
fi
##################################################
test-pipelines-lastpipe
##################################################
## generated by create-stub2.sh v0.1.2
## on Sun, 21 Jul 2019 21:28:54 +0900
## see <https://github.com/temptemp3/sh2>
##################################################
Source: test-pipelines-lastpipe.sh
bash test-pipelines-lastpipe.sh
Output
0
0
0
0
0
enabling lastpipe ...
01
011
0111
01111
0
Note that in the case that lastpipe is enabled, changes made in the last
command of the pipeline may persist. That is if we update a variable, its value
will accessible in the current shell outside of the pipeline.

Test negation

Here is yet another test showing how negation works on pipelines in bash. Note
that every time func is called we append a ‘1’ to the variable x. The return
status always 1. However, we can change it to 0 using negation.
#!/bin/bash
## test-pipeline-negation
## version 0.0.1 - initial
##################################################
func2() {
x=0
}
func() {
x+=1
false
}
test-pipeline-negation() {
func
echo exit status: ${?}
echo x: ${x}
echo negating function ...
! func
echo exit status: ${?}
echo x: ${x}
}
##################################################
if [ ${#} -eq 0 ]
then
true
else
exit 1 # wrong args
fi
##################################################
test-pipeline-negation
##################################################
## generated by create-stub2.sh v0.1.2
## on Mon, 22 Jul 2019 13:36:01 +0900
## see <https://github.com/temptemp3/sh2>
##################################################
Source: test-pipeline-negation.sh
bash test-pipeline-negation.sh
Output:
exit status: 1
x: 1
negating function ...
exit status: 0
x: 11

Test time

Here we want to show how to time a pipeline. In the example below, we time a
function that takes 1-2 seconds to complete and negate its exit status the
second time calling it.
#!/bin/bash
## test-pipeline-time
## version 0.0.1 - initial
##################################################
func() {
x+=1
sleep 1
sleep $(( RANDOM % 2 ))
false
}
test-pipeline-time() {
time func
echo -e "exit status: ${?} \nx: ${x}"
time ! func
echo -e "exit status: ${?} \nx: ${x}"

}
##################################################
if [ ${#} -eq 0 ]
then
true
else
exit 1 # wrong args
fi
##################################################
test-pipeline-time
##################################################
## generated by create-stub2.sh v0.1.2
## on Mon, 22 Jul 2019 13:49:57 +0900
## see <https://github.com/temptemp3/sh2>
##################################################
Source: test-pipeline-time.sh
bash test-pipeline-time.sh
Output:
real    0m1.063s
user    0m0.000s
sys     0m0.060s
exit status: 1
x: 1

real    0m2.064s
user    0m0.015s
sys     0m0.076s
exit status: 0
x: 11

Test time format

Here we show how to customize pipeline time output. In the example below, in
addition to showing the default and portable behavior, we create a custom
TIMEFORMAT, which removes precision and ads CPU usage.
#!/bin/bash
## test-time-format
## version 0.0.1 - initial
##################################################
test-time-format() {
echo "timing sleep 1 (default behavior) ..."
time sleep 1
echo "timing sleep 1 (portable) ..."
time -p sleep 1
echo "timing sleep 1 (custom) ..."
TIMEFORMAT=$'\nreal\t%0R\nuser\t%0U\nsys\t%0S\ncpu\t%P'
time sleep 1
}
##################################################
if [ ${#} -eq 0 ]
then
true
else
exit 1 # wrong args
fi
##################################################
test-time-format
##################################################
## generated by create-stub2.sh v0.1.2
## on Mon, 22 Jul 2019 21:12:31 +0900
## see <https://github.com/temptemp3/sh2>
##################################################
Source: test-time-format.sh
bash test-time-format.sh
Output:
timing sleep 1 (default behavior) ...
real    0m1.017s
user    0m0.015s
sys     0m0.000s
timing sleep 1 (portable) ...
real 1.02
user 0.01
sys 0.00
timing sleep 1 (custom) ...
real    1
user    0
sys     0
cpu     1.46

Test pipefail

Here we show how lastpipe affects the exit status returned by a pipeline. In
the example below, the exit status of a pipe is 0 if none of the commands
returns a non-zero exit status. Otherwise, all pipelines return a non-zero exit
status between 1 and 5.
#!/bin/bash
## test-pipefail
## version 0.0.1 - initial
##################################################
func2() {
echo ${x}
x=0
}
func() {
test ! $(( RANDOM % 3 )) -eq 0 || return ${1}
}
test-pipefail() {
shopt -s lastpipe
set -o pipefail
declare -i x=0
func 1 | func 2 | func 3 | func 4 | func 5 ; echo ${?}
func 1 | func 2 | func 3 | func 4 | func 5 ; echo ${?}
func 1 | func 2 | func 3 | func 4 | func 5 ; echo ${?}
func 1 | func 2 | func 3 | func 4 | func 5 ; echo ${?}
func 1 | func 2 | func 3 | func 4 | func 5 ; echo ${?}
}
##################################################
if [ ${#} -eq 0 ]
then
true
else
exit 1 # wrong args
fi
##################################################
test-pipefail
##################################################
## generated by create-stub2.sh v0.1.2
## on Mon, 22 Jul 2019 21:31:47 +0900
## see <https://github.com/temptemp3/sh2>
##################################################
Source: test-pipefail.sh
bash test-pipefail.sh
Output
3
3
3
0
3


About the author


Nicholas Shellabarger

A developer and advocate of shell scripting and vim. His works include
automation tools, static site generators, and web crawlers written in bash. For
work he tools with cloud computing, app development, and chatbots. He codes in
bash, python, or php, but is open to offers.
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
