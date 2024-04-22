





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


Bash Error Handling

3 years ago
by Nicholas_Shellabarger
There are no try … catch blocks in bash for exception and error handling to
say. So, how do you even start to handle errors in a way that none will escape
and wreak havoc in the background hidden by silent a foreground that only
appears okay.
Finally, there is a definitive guide for bash error handling.  I have outlined
the foundation needed to handle any error in bash.


Error handling in bash the hard way

Knowing how to use exit codes, options such as errexit, and traps allow you to
create robust scripts and better handle errors in bash.

Exit codes

Handling errors based on exit codes is the standstill method for detecting
failure in a command. This is especially true in the case of external commands.
Curl_in_bash is a good example of how to handle errors based on known error
codes. Unlike user-defined functions, you can expect external command errors
codes to be well documented.
${?} holds the exit code of the last command executed before any given line. An
exit code of 0 means the command executed without any issues. Otherwise,
something went wrong.
Commands
COMMAND
case {?} in
0) {
true # ok
} ;;
*) {
false # something went wrong
}
In fact, you could get away with bash error handling using only exit codes. You
could try until you find a lazier solution. At least that is what any person
would do after writing a few conditionals to handle errors based on error
codes.
With error code you have a way to test if a command was successful or not.
What if you just want your bash script to die in the case that something goes
wrong to minimize the damage caused by a script with errors?
That is where exit on error shows its precautious face.

Exit on error

Exit on error unarguably the most useful feature enabling error detection and
handling that bash programmers don’t start out with.
Enter minefield.sh
Script
#!/bin/bash
## minefield
## version 0.0.1 - initial
##################################################
minefield() {
a00075e82f2d59f3bd2b4de3d43c6206e50b93bd2b29f86ee0dfcb0012b6
25ea27311a7503bd1698e2a111b5b61556f0495e84e09e098af281a0fc66
39e62a385ca44b4bff58fb759b90c3f076fc2b0313e1d467d91984ea7965
3517b2d1e5f9367c74c33c8a65749d3081a6f67da3567f408350289a60dc
46ceb1b167a3cb71b90e96c1af5921bd241893d2bac18b56e93e70d43836
66382963ecf70b1a664442262330a9a4d30b81076b1a2240019ee9c601b1
4c88bc34634f9824daaaac2ca30f6c19bfb99cac9dcecd3cc1a30cc1e4c6
bf75042e3ee312b4be98415841b3646ec3134cd549a25920c0628be11771
c773f4e37b25a85b93124c6aec58b3e900b354bc8eff976b4da5835e2e44
f7bc8317c368fb61350f1533f88173cb5d6f5f3f78323e2ee82d15e31480
8b9f871c11a42282a7b68d7217708cf7a7554c4845a0f790bcf2b4b91f69
c112ec610a54191aa3f6911dca73ea25ff987303cd5d57444ed6c9c2f815
c310549929221426de23021ca1282d6cfc88169d0f0724d5b3a3069ca6c5
54f362952413a46cfb9d3768caacc56781a02c47d2012b47fa25f54a9641
1053161b6d05e1bcc3b08138d104d0cbef87cce54b19bb1f6f45ab99f283
737364653dd1f7db292fd773b600bc6f6da8b28a10f0461befa59dac1436
0fe9041a7ceb82b7fd307a6b53c09ad2234e889386d6b05b34fdf28d58ae
4237033b6fe610e1b7e9f5b64503c3b82442604b888b40a6401e2a87390e
43ced3824a2613ed0a8f684155baae5a4877b59be188845d692f8cb88626
e9887620c9ab503ab3d550e0e8464482cb244d590483a88b9068695ecc16
09f16eec806c3eef20775ef8071e56c9a190ab46eb32cbc8322c037265f2
9fad2c9ee63acd67b2ede0dc2a33d5079e805e91b78f34c23d11bb7858cd
b05043267e1e9b029ee06a29f18cdbbc79d9ff51758df378422e2d48f714
d583894c014cb662ac69e7bcea19bab555eeacccd390c4900485e936d532
1d7ff7e61a7c9208d401fcd64d4f6db14bf27c08316990145c6309bb457e
fed43e657352a318331436d70168439b187106de19db544a63203ea32fd9
1396bdde706d44dbc57d2ed2f8bafe4dfc2095d0aa9666b40d24b5ce1810
339c4403a396950d2dd2c6096aac47faa35cb261e87709ddbf14b8a2cd4b
968a582cc42a5aec7547067eb4cbd1656fd537d0d1f779d0739e12dfdefb
0d8210092ffcf3f15b86a2b391e27ac9f9999c2a924b3116ffdfa939d48d
202f8e3b90eec4c0c9eed6a5b0a2a481884ba12ebc1f5d77ecf7067a3d2d
035efaee367ae2ada5c88565dad5296c6830ab81c1a27a9f298f07d243da
878c245d100239424a92732aed3288b016fc3b6de668a95a87e61d74393e
08097e063f318d20accf4952c65cca51399087f20f1737a006a3b8588e1a
f022f3a3b4c3f2bf35d2888fe62fc026954c193a78d419da6f92a0e059b4
aee037ed522d9c1c27b9610781cb502bdaa1a7c17816b8b546f5199f6260
6799cbfbf0a3ae5f3b2b21c65abdf1e11a8055d9c12858fe88308fd3b5b1
d61a115fb88542b02c888cb2325a6adc7473cd9308ca5d8368f5eccaf946
5c534aaf1a13c5e2b721230096b641ded14379f52038728908ba23b4f7a1
ce60c9c739115e72baf51ca840b956b4edfefa8e6709cd379f0b0d5be068
fc4bdd73841954d95a38cbf4dea42814b39dba5cbb6d74c2319c8ddab86b
7007acee1e3fa94a56c4ad6a233dfee5dac2e5b68963b917b9677ebf7a12
ed4201c85ec976c313aad671a9b2a1bbd9e637e00ad980d0ab9ad343f5ae
e36a95c20fc2f307bcfc1bd081ceb1ca28340b263924e7d31337d75a78ee
b79dc0eedd74a34e4f05e613b275686f96ae32982e351c040637a614b376
565acca108f821c99e33707a023379ef922e35b326081313207da19d8a73
621ffcf4a7360a0647c2e6c9dd33496b1f048be5a5b4e7e9edf9fad06faa
008545958e2544af6f645fb0d188baa0f61aeebf77e7fd78545fbe3d9313
a65ed288ca87b0d41da534fa3e388138f0e78b0f494db0d0b7496745f83c
a9314c0e4d988089db2e389ac0d23cb2e123269a826a19052fa955184b98
85e026c5592197cd37377dd8c4052f1c86add447125db7d4c60010f7a42e
9b8b550a88d2e5f61fe924925e982299d01c7670ebcda5c94b39860513c2
44061da41147978c5d023722c839626fa522b546e998a148f22b61b851f2
154ded671a1dab8350d8d48afccf9a8103eacf18067e203cb7270877fe9f
8e87618811f9311c0b7898fb4a716216434ebc6ee296afcdcf5d60b069a1
cfd5e3a86594fa56b8523c7102669742d7b6fea07550f37bdab67542c637
a703575a24117adbc86a0daaccc7cb7cd313e6c7931d606fc3300b069a62
44d588bab5b9d8c4f32c6fbe3a89a4e87a17db7df2802024cf0b66104460
2055f71f4820bba44a4c86334c5dff744730df82ad9f7463522a618fa1c7
561fff72366db9b918ac4c3cca86505163341a8e453774835e01495baf55
cf9abf6f54fcf2f8f8a2d7e2f1b716ebf8842772639adfb0b878fbd353bd
5295839f9806053498970cd093b39a09db0b06cb87a9b30861946f71287b
2cc3ace9cf26fb75cb594d07924cdfb806b6cacda40de6dc0998c960ba62
8006a6099065659be1d89bb8c2100569bd3f6d808968fa13a0208873da4e
f1b62a2914c9fb9514ca5bcc8eddfbea54b12869fd1deb3f9eab9fd4d654
7546db28931bee8ff44ad0f359775e95a1aeac6e752a3b35b9410932ed09
66d307a834a1301f6622d249a98e99eb03bac2a569bbb3440cc6d8e7cc07
9416d2616e2ee126b41fc5d350c33a036baa704aef70b01ace7fee2c62ff
a480ec6141c9a2afc0f9fb2849570a69dba07dcfa70f8c78d11f61a2043f
c81d3c3a594ec9f2d05bc9fb2514dd176cb9b16a712643a5a2808e33d8fa
cb2faa622a38fab3d72e5eafe012912e8bed3ed5930f61c40c65df6fe644
80d71eb9b825686e801cb27ade3ac2bf89ea63005f12d7c0ad51cd36d0f7
6101821d0196ded179d90ad3e6601fcd46f11723adf30ce4c14b6495f94d
d827422bd413386c10e118ee26fda1b27eda25bb93fc3dec5eda84771218
8a6da66d1f6104bb565b7000439f4660b46f32d987e3890f4ddf56098dd2
}
##################################################
if [ ${#} -eq 0 ]
then
true
else
exit 1 # wrong args
fi
##################################################
minefield
##################################################
## generated by create-stub2.sh v0.1.2
## on Mon, 24 Jun 2019 22:26:39 +0900
## see <https://github.com/temptemp3/sh2>
##################################################
As you would expect, this is what happens when you try to run the script.
Command line
bash minefield.sh
Output
minefield.sh: line 6:
a00075e82f2d59f3bd2b4de3d43c6206e50b93bd2b29f86ee0dfcb0012b6:
command not found
minefield.sh: line 7:
25ea27311a7503bd1698e2a111b5b61556f0495e84e09e098af281a0fc66:
command not found
minefield.sh: line 8:
39e62a385ca44b4bff58fb759b90c3f076fc2b0313e1d467d91984ea7965:
command not found
minefield.sh: line 9:
3517b2d1e5f9367c74c33c8a65749d3081a6f67da3567f408350289a60dc:
command not found
minefield.sh: line 10:
46ceb1b167a3cb71b90e96c1af5921bd241893d2bac18b56e93e70d43836:
command not found
minefield.sh: line 11:
66382963ecf70b1a664442262330a9a4d30b81076b1a2240019ee9c601b1:
command not found
minefield.sh: line 12:
4c88bc34634f9824daaaac2ca30f6c19bfb99cac9dcecd3cc1a30cc1e4c6:
command not found
minefield.sh: line 13:
bf75042e3ee312b4be98415841b3646ec3134cd549a25920c0628be11771:
command not found
minefield.sh: line 14:
c773f4e37b25a85b93124c6aec58b3e900b354bc8eff976b4da5835e2e44:
command not found
minefield.sh: line 15:
f7bc8317c368fb61350f1533f88173cb5d6f5f3f78323e2ee82d15e31480:
command not found
minefield.sh: line 16:
8b9f871c11a42282a7b68d7217708cf7a7554c4845a0f790bcf2b4b91f69:
command not found
minefield.sh: line 17:
c112ec610a54191aa3f6911dca73ea25ff987303cd5d57444ed6c9c2f815:
command not found
minefield.sh: line 18:
c310549929221426de23021ca1282d6cfc88169d0f0724d5b3a3069ca6c5:
command not found
minefield.sh: line 19:
54f362952413a46cfb9d3768caacc56781a02c47d2012b47fa25f54a9641:
command not found
minefield.sh: line 20:
1053161b6d05e1bcc3b08138d104d0cbef87cce54b19bb1f6f45ab99f283:
command not found
minefield.sh: line 21:
737364653dd1f7db292fd773b600bc6f6da8b28a10f0461befa59dac1436:
command not found
minefield.sh: line 22:
0fe9041a7ceb82b7fd307a6b53c09ad2234e889386d6b05b34fdf28d58ae:
command not found
minefield.sh: line 23:
4237033b6fe610e1b7e9f5b64503c3b82442604b888b40a6401e2a87390e:
command not found
minefield.sh: line 24:
43ced3824a2613ed0a8f684155baae5a4877b59be188845d692f8cb88626:
command not found
minefield.sh: line 25:
e9887620c9ab503ab3d550e0e8464482cb244d590483a88b9068695ecc16:
command not found
minefield.sh: line 26:
09f16eec806c3eef20775ef8071e56c9a190ab46eb32cbc8322c037265f2:
command not found
minefield.sh: line 27:
9fad2c9ee63acd67b2ede0dc2a33d5079e805e91b78f34c23d11bb7858cd:
command not found
minefield.sh: line 28:
b05043267e1e9b029ee06a29f18cdbbc79d9ff51758df378422e2d48f714:
command not found
minefield.sh: line 29:
d583894c014cb662ac69e7bcea19bab555eeacccd390c4900485e936d532:
command not found
minefield.sh: line 30:
1d7ff7e61a7c9208d401fcd64d4f6db14bf27c08316990145c6309bb457e:
command not found
minefield.sh: line 31:
fed43e657352a318331436d70168439b187106de19db544a63203ea32fd9:
command not found
minefield.sh: line 32:
1396bdde706d44dbc57d2ed2f8bafe4dfc2095d0aa9666b40d24b5ce1810:
command not found
minefield.sh: line 33:
339c4403a396950d2dd2c6096aac47faa35cb261e87709ddbf14b8a2cd4b:
command not found
minefield.sh: line 34:
968a582cc42a5aec7547067eb4cbd1656fd537d0d1f779d0739e12dfdefb:
command not found
minefield.sh: line 35:
0d8210092ffcf3f15b86a2b391e27ac9f9999c2a924b3116ffdfa939d48d:
command not found
minefield.sh: line 36:
202f8e3b90eec4c0c9eed6a5b0a2a481884ba12ebc1f5d77ecf7067a3d2d:
command not found
minefield.sh: line 37:
035efaee367ae2ada5c88565dad5296c6830ab81c1a27a9f298f07d243da:
command not found
minefield.sh: line 38:
878c245d100239424a92732aed3288b016fc3b6de668a95a87e61d74393e:
command not found
minefield.sh: line 39:
08097e063f318d20accf4952c65cca51399087f20f1737a006a3b8588e1a:
 command not found
minefield.sh: line 40:
f022f3a3b4c3f2bf35d2888fe62fc026954c193a78d419da6f92a0e059b4:
command not found
minefield.sh: line 41:
aee037ed522d9c1c27b9610781cb502bdaa1a7c17816b8b546f5199f6260:
command not found
minefield.sh: line 42:
6799cbfbf0a3ae5f3b2b21c65abdf1e11a8055d9c12858fe88308fd3b5b1:
command not found
minefield.sh: line 43:
d61a115fb88542b02c888cb2325a6adc7473cd9308ca5d8368f5eccaf946:
command not found
minefield.sh: line 44:
5c534aaf1a13c5e2b721230096b641ded14379f52038728908ba23b4f7a1:
command not found
minefield.sh: line 45:
ce60c9c739115e72baf51ca840b956b4edfefa8e6709cd379f0b0d5be068:
command not found
minefield.sh: line 46:
fc4bdd73841954d95a38cbf4dea42814b39dba5cbb6d74c2319c8ddab86b:
command not found
minefield.sh: line 47:
7007acee1e3fa94a56c4ad6a233dfee5dac2e5b68963b917b9677ebf7a12:
command not found
minefield.sh: line 48:
ed4201c85ec976c313aad671a9b2a1bbd9e637e00ad980d0ab9ad343f5ae:
command not found
minefield.sh: line 49:
e36a95c20fc2f307bcfc1bd081ceb1ca28340b263924e7d31337d75a78ee:
command not found
minefield.sh: line 50:
b79dc0eedd74a34e4f05e613b275686f96ae32982e351c040637a614b376:
command not found
minefield.sh: line 51:
565acca108f821c99e33707a023379ef922e35b326081313207da19d8a73:
command not found
minefield.sh: line 52:
621ffcf4a7360a0647c2e6c9dd33496b1f048be5a5b4e7e9edf9fad06faa:
command not found
minefield.sh: line 53:
008545958e2544af6f645fb0d188baa0f61aeebf77e7fd78545fbe3d9313:
command not found
minefield.sh: line 54:
a65ed288ca87b0d41da534fa3e388138f0e78b0f494db0d0b7496745f83c:
command not found
minefield.sh: line 55:
a9314c0e4d988089db2e389ac0d23cb2e123269a826a19052fa955184b98:
command not found
minefield.sh: line 56:
85e026c5592197cd37377dd8c4052f1c86add447125db7d4c60010f7a42e:
command not found
minefield.sh: line 57:
9b8b550a88d2e5f61fe924925e982299d01c7670ebcda5c94b39860513c2:
command not found
minefield.sh: line 58:
44061da41147978c5d023722c839626fa522b546e998a148f22b61b851f2:
command not found
minefield.sh: line 59:
154ded671a1dab8350d8d48afccf9a8103eacf18067e203cb7270877fe9f:
command not found
minefield.sh: line 60:
8e87618811f9311c0b7898fb4a716216434ebc6ee296afcdcf5d60b069a1:
command not found
minefield.sh: line 61:
cfd5e3a86594fa56b8523c7102669742d7b6fea07550f37bdab67542c637:
command not found
minefield.sh: line 62:
a703575a24117adbc86a0daaccc7cb7cd313e6c7931d606fc3300b069a62:
command not found
minefield.sh: line 63:
44d588bab5b9d8c4f32c6fbe3a89a4e87a17db7df2802024cf0b66104460:
command not found
minefield.sh: line 64:
2055f71f4820bba44a4c86334c5dff744730df82ad9f7463522a618fa1c7:
command not found
minefield.sh: line 65:
561fff72366db9b918ac4c3cca86505163341a8e453774835e01495baf55:
command not found
minefield.sh: line 66:
cf9abf6f54fcf2f8f8a2d7e2f1b716ebf8842772639adfb0b878fbd353bd:
command not found
minefield.sh: line 67:
5295839f9806053498970cd093b39a09db0b06cb87a9b30861946f71287b:
command not found
minefield.sh: line 68:
2cc3ace9cf26fb75cb594d07924cdfb806b6cacda40de6dc0998c960ba62:
command not found
minefield.sh: line 69:
8006a6099065659be1d89bb8c2100569bd3f6d808968fa13a0208873da4e:
command not found
minefield.sh: line 70:
f1b62a2914c9fb9514ca5bcc8eddfbea54b12869fd1deb3f9eab9fd4d654:
command not found
minefield.sh: line 71:
7546db28931bee8ff44ad0f359775e95a1aeac6e752a3b35b9410932ed09:
command not found
minefield.sh: line 72:
66d307a834a1301f6622d249a98e99eb03bac2a569bbb3440cc6d8e7cc07:
command not found
minefield.sh: line 73:
9416d2616e2ee126b41fc5d350c33a036baa704aef70b01ace7fee2c62ff:
command not found
minefield.sh: line 74:
a480ec6141c9a2afc0f9fb2849570a69dba07dcfa70f8c78d11f61a2043f:
command not found
minefield.sh: line 75:
c81d3c3a594ec9f2d05bc9fb2514dd176cb9b16a712643a5a2808e33d8fa:
command not found
minefield.sh: line 76:
cb2faa622a38fab3d72e5eafe012912e8bed3ed5930f61c40c65df6fe644:
command not found
minefield.sh: line 77:
80d71eb9b825686e801cb27ade3ac2bf89ea63005f12d7c0ad51cd36d0f7:
command not found
minefield.sh: line 78:
6101821d0196ded179d90ad3e6601fcd46f11723adf30ce4c14b6495f94d:
command not found
minefield.sh: line 79:
d827422bd413386c10e118ee26fda1b27eda25bb93fc3dec5eda84771218:
command not found
minefield.sh: line 80:
8a6da66d1f6104bb565b7000439f4660b46f32d987e3890f4ddf56098dd2:
command not found
Fun. But would it be nice to stop after hitting the first mine? There is a way
to do that in bash, i.e. exit on error. Let’s try it again with errexit set on.
Command line
bash -e minefield.sh
Output
minefield.sh: line 6:
a00075e82f2d59f3bd2b4de3d43c6206e50b93bd2b29f86ee0dfcb0012b6:
 command not found
It’s important to note that with exit on error set, we would have to adjust our
coding style a little. For example, what if we want to handle the error of
something instead of falling back to exit? Here’s how to handle errors in bash
when exit on error is set.
Why change the way you code when using exit on error? Here’s why
Commands
oops() {
false
}
oops
test ! ${?} -eq 0 || {
echo Big mistake!
}
Output
(empty)
The script exited on the oops line. Oops.
Here are some options you may want to explore in order to workaround this
issue.

Option 1) Try to recover or execute a fallback routine

Commands
pothole() {
false # Leg stuck in a pothole
}
try-to-get-out-of-pothole() {
test $( RANDOM % 2 ) -eq 0
}
_() {
pothole || {
try-to-get-out-of-pothole || {
echo "Sorry, no luck getting out of pothole ..." 1>&2
false
}
}
}
Output
Sorry, no luck getting out of pothole …

Option 2) Exit but say something helpful first

Commands
mine() {
false # boom!
}
mine || {
echo "You stepped on a mine!" 1>&2
false
}
Output
You stepped on a mine!

Final notes on error handling when exit on error is set on

Within a bash script, you may use the set command to turn exit on error on, set
-e. For more details on errexit, see how_to_debug_bash_script.

Trap exit and error

Trap allows us to set commands to run in the event the shell receives a signal.
Signals have names called SIGNAL_SPECs. Some common signals for EXIT, ERROR,
DEBUG, and RETURN. More signals may be listed using the trap -l command.
Additionally, we may see what commands are associated with any given signal
using trap -p SIGSPEC.
For example, we may want to check what commands are associated with the ERR
signal. In that case, we could type a command line as follows.
trap -p ERR
If the output is empty, then no commands have been associated with the signal
using trap yet.
_() { echo oops ; }
trap _ ERR EXIT
Now if we print signal commands the result is no longer empty.
Command line
trap -p EXIT ERR
Output
trap -- '_' EXIT
trap -- '_' ERR
What this means is that _ is a command that will follow any EXIT or ERR signal.
Let’s see if _ is called by the trap.
Command line
false
Output
oops
Although the above example may seem trivial at first, it is exactly where you
would start to build a robust error handling function like error.sh.

Use AND and OR lists

AND and OR lists one of the primary constructs to implement error handling
logic.

The AND list

The AND list allows you to bind commands together in such a way that commands
will execute from the beginning of the list left to right only commands to the
left don’t fail.
LHS1 && LHS2 && LHS3
# false if any of the above commands fails, otherwise true

The OR list

The OR list allows you to specify a fallback if anything goes wrong on the
lefthand side.
LHS || {
fallback # tries to recover from a failure in LHS
}
It is important to note that exit on error will not occur if the end of
fallback does not return a nonzero exit code. The above example would be useful
if enabling potential recovery in the fallback. Conversely, if the intent of
the fallback is to act as a trap on an instance of the ERR signal, then
adjustments would be required as follows.
LHS || {
fallback # traps instance of ERR signal
false
}
The OR list allows you to order of command execution based on exit code.

Trigger your own errors

The best way to handle errors is to trigger your own using true and false.
true  # does nothing but may be a placeholder
false # should fire up an ERR signal
Suppose that we have everything set up and errexit is on.
handle-error() {
true
}
false || {
handle-error
false
}
Now we have everything we need to do error handling in bash. Here follow some
advice I have to handle errors in bash.

Error handling in bash the easy way

Error handling in bash isn’t inherently hard. Not reusing code and inventing
things you already know how to do, now that is hard. Here are some pointers
that I have to make handling errors easier.

Use boilerplate

Most of what is seen above for doing it the hard way can be put in your
boilerplate code. Exit on error functions to be called in traps, the works.
Whether you use your own boilerplate code for error handling in bash scripts,
or someone else’s, the point here is to have something you can call bash
boilerplate for error handling that you can simply slap on when it’s time to
get serious.
Here’s how my boilerplate looks when error handling is required.
. ${SH2}/error.sh # error handling
error "true" # show errors
# done

Be consistent

Code consistency in error handling reduces the chance of unintendedly failing
to handle an error. This is especially important when coding with errexit set
on.
The pattern I use for error handling in bash scripts is as follows.
Commands
commands || {
error "oops" "${FUNCNAME}" "{LINENO}"
false
}
Output
Error “oops”  on line number 7 in lucky-number

Expect code to fail

Everything expected to succeed fails, and everything expected to fail succeeds.
Error handling comes into handy when you know something will succeed eventually
but requires failure along the way.
while :
commands || { # success
break # out of loop
}
true # failure
done

Fallback once

Have a fallback and only allow it to be used once. For code with a known
exception, handle errors if recovery is possible, otherwise fallback.
As you may have guessed our fallback is to exit with a message telling users
where and what happened if any.

Hoard error logs

Record errors in a log file or database, whatever method you prefer. After all,
unless you are debugging_bash_scripts, you are not going to be around when a
bird flies into a ceiling fan. That is for sure.

Send out notifications

In addition to keeping a log of any errors that occur, I recommend sending out
error notifications. This may be adding to a channel on your Slack or simply
sending an email to yourself, whatever method distributes error records outside
of your logs.

Be lazy

It doesn’t matter who you are, after a couple of days of earnest error
handling, you realize that proactive error handling is lines of code better
spent elsewhere. If anything occurs, fix it then and there. Note that this only
works if you have a catchall and have been careful not to hide errors from
traps in conditional.

Bottom line

Bash doesn’t have bailout constructs try … catch blocks to handle exceptions
and errors.  That doesn’t mean you are helpless. There are plenty of ways to
code defensively such that errors or not left unchecked.
Happy coding and good luck error handling in bash.
Thanks.


About the author


Nicholas Shellabarger

A developer and advocate of shell scripting and vim. His works include
automation tools, static site generators, and web crawlers written in bash. For
work he tools with cloud computing, app development, and chatbots. He codes in
bash, python, or php, but is open to offers.
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
