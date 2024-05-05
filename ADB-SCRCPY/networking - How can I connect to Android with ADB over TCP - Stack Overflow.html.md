[ Stack Overflow ](https://stackoverflow.com)

  1. Products 
  2. [Customers](https://stackoverflow.com/teams/customers)
  3. [Use cases](https://stackoverflow.com/teams/use-cases)

  1. [ Stack Overflow Public questions and answers ](https://stackoverflow.com/questions)
  2. [ Teams Private questions and answers for your team ](https://stackoverflow.com/teams)
  3. [ Enterprise Private self-hosted questions and answers for your enterprise ](https://stackoverflow.com/enterprise)
  4. [ Talent Hire technical talent ](https://stackoverflow.com/talent)
  5. [ Advertising Reach developers worldwide ](https://stackoverflow.com/advertising)

Loading…

  1.   2. [Log in](https://stackoverflow.com/users/login?ssrc=head&returnurl=https%3a%2f%2fstackoverflow.com%2fquestions%2f2604727%2fhow-can-i-connect-to-android-with-adb-over-tcp) [Sign up](https://stackoverflow.com/users/signup?ssrc=head&returnurl=%2fusers%2fstory%2fcurrent)
  3. ###  [current community](https://stackoverflow.com)

    * [ Stack Overflow  ](https://stackoverflow.com)

[help](https://stackoverflow.com/help) [chat](https://chat.stackoverflow.com)

    * [ Meta Stack Overflow  ](https://meta.stackoverflow.com)

###  your communities

[Sign
up](https://stackoverflow.com/users/signup?ssrc=site_switcher&returnurl=%2fusers%2fstory%2fcurrent)
or [log
in](https://stackoverflow.com/users/login?ssrc=site_switcher&returnurl=https%3a%2f%2fstackoverflow.com%2fquestions%2f2604727%2fhow-
can-i-connect-to-android-with-adb-over-tcp) to customize your list.

### [more stack exchange communities](https://stackexchange.com/sites)

[company blog](https://stackoverflow.blog)

  1. [ Home ](https://stackoverflow.com/)
  2.     1. Public
    2. [ Stack Overflow ](https://stackoverflow.com/questions)
    3. [ Tags ](https://stackoverflow.com/tags)
    4. [ Users ](https://stackoverflow.com/users)
    5. [ Jobs ](https://stackoverflow.com/jobs?so_medium=StackOverflow&so_source=SiteNav)
  3.     1. Teams

[ What’s this? ](javascript:void\(0\))

    2. [ Free 30 Day Trial  ](https://stackoverflow.com/teams "Stack Overflow for Teams is a private, secure spot for your organization's questions and answers.")

**Teams**

Q&A for Work

Stack Overflow for Teams is a private, secure spot for you and your coworkers
to find and share information.

[ Learn more ](https://stackoverflow.com/teams)

# [How can I connect to Android with ADB over
TCP?](https://stackoverflow.com/questions/2604727/how-can-i-connect-to-
android-with-adb-over-tcp)

[ Ask Question ](https://stackoverflow.com/questions/ask)

Asked 9 years, 11 months ago

Active [1 month ago](https://stackoverflow.com/questions/2604727/how-can-i-
connect-to-android-with-adb-over-tcp?lastactivity "2020-02-15 13:51:11Z")

Viewed 1.1m times

870

607

[](https://stackoverflow.com/posts/2604727/timeline "Timeline")

I am attempting to debug an application on a [Motorola
Droid](https://en.wikipedia.org/wiki/Motorola_Droid), but I am having some
difficulty connecting to the device via USB. My development server is a
Windows 7 64-bit VM running in
[Hyper-V](http://en.wikipedia.org/wiki/Hyper-V), and so I cannot connect
directly via USB in the guest or from the host.

I installed a couple of different USB-over-TCP solutions, but the connection
appears to have issues since the
[ADB](http://en.wikipedia.org/wiki/Android_Debug_Bridge) monitor reports
"devicemonitor failed to start monitoring" repeatedly. Is there a way to
connect directly from the client on the development machine to the daemon on
the device using the network instead of the USB connection or possibly another
viable options?

[android](https://stackoverflow.com/questions/tagged/android "show questions
tagged 'android'")
[networking](https://stackoverflow.com/questions/tagged/networking "show
questions tagged 'networking'")
[tcp](https://stackoverflow.com/questions/tagged/tcp "show questions tagged
'tcp'") [debugging](https://stackoverflow.com/questions/tagged/debugging "show
questions tagged 'debugging'")
[adb](https://stackoverflow.com/questions/tagged/adb "show questions tagged
'adb'")

[share](https://stackoverflow.com/q/2604727 "short permalink to this
question")

Share a link to this question

Copy link

|[improve this question](https://stackoverflow.com/posts/2604727/edit)

[edited Mar 16 '14 at 6:29](https://stackoverflow.com/posts/2604727/revisions
"show all edits to this post")

[](https://stackoverflow.com/users/63550/peter-mortensen)

[Peter Mortensen](https://stackoverflow.com/users/63550/peter-mortensen)

25.2k2121 gold badges9090 silver badges118118 bronze badges

asked Apr 9 '10 at 2:18

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAACe0lEQVRYhcWXTWsaURSG3ysTCSpkJoUISeposzU46dSuC/0BXfQPdNM/1S7abLJvoVl0XegijEzpQiItJiE6Y0i9RNAZB9QuwlzvOF9O/MgLgvdD3+ecOed6JdffvkwkRUVmdw9B+vv5o2e8rVbR1c4C9wZpcycP+6YTuLaxJSJl33RgfD9F6/QrBu1W7BdKhwq21ercAJKihq9VjpByB0lAkkBkdvewuZP3zW9siciVDqYASUGSQARlQaocgRACIexDY8fB2Bn65psnx5FmB+/es/d353UA0yy4teBGD8CfgbQoIf/qNfbfvEWu+CwEbPoK0915Hbc/f7AxnwU3egDTDKRFCZLyHFm5xBYfqllzYJqF0XDIogcAYZnGYeauJEXFyLY8PuTPpw8TflPSPl9UvhpI2udLB1g3RCDAOiF850Bcny+q2XPCBxDV28uU2y2hj2Ad5kBEDazD3AcglitIpdMrBZg9pBiAWK7gyYuXKzUPUuoxzQEg9ZjmACD0GnX0GnU2sew23FarkA4VNm6eHHs8hFX3vfvDxkPwWksbdrUz0N964FrolWwVEEEik8mE3QesjomRbSMnF9kG/n+BWK6g16gnqhP+7Oc1aLdAdc2bAaprGNk2sgXZdztyu4Uv2IfIMtro6hrsjgmAewSWacAy2gCA/tUFcnLJZ76QsWncG5uGZ54BdHWNTVK9hmyhCELIwuZWxwTVNRbcrATgPi08mUO76F9eIFcsIe6ciOvzsTOMrBkB8Ebviv7SkJWLsQUX1+fZpzIy+wUMrq9A9RqG/269AIN2ixUEL4dS9C+bkebzQhBCQkEEGhC9K6rX5gLgIaIUBPIf3zZJ4n7sLLsAAAAASUVORK5CYII='
width='32' height='32' />[](https://stackoverflow.com/users/312443/jdm)

[JDM](https://stackoverflow.com/users/312443/jdm)JDM

9,60944 gold badges1717 silver badges2222 bronze badges

  * 71

When connected via USB: `adb tcpip 5555`. Disconnect USB, view phone IP from
`Settings > About Phone > Status`. Now `adb connect 192.168.x.x` and that's
it. No tools, no software. Just Works. –
[andreszs](https://stackoverflow.com/users/161293/andreszs "2,263 reputation")
Feb 16 '15 at 18:06

  * 1

What Andrew said - these are the official instructions from Google's [android
developer website](http://developer.android.com/tools/help/adb.html#wireless),
no root necessary. Just worked on my non-rooted HTC One m8 (requires enabling
developer options, of course.). – [Jeff
Ward](https://stackoverflow.com/users/1026023/jeff-ward "9,533 reputation")
Apr 30 '15 at 6:32

  * If adb service runs at port 5037 then why does it locate devices in the range 5555 to 5585 ? – [Shivam Aggarwal](https://stackoverflow.com/users/5116129/shivam-aggarwal "624 reputation") Dec 3 '15 at 16:09

  * @Andrew Could I use an app such as [this](https://play.google.com/store/apps/details?id=at.bherbst.net&hl=en) to open and close the port without a computer on a Nexus 6 with no root access? I am concerned with the security issues that could arise from leaving port 5555 open when I am on a public network and not using my phone for developing. – [DaveTheMinion](https://stackoverflow.com/users/2941352/davetheminion "621 reputation") Apr 6 '16 at 18:23

  * 3

[2 methods - how to run android app over wifi - Simple
tutorial](https://androidride.com/how-to-run-android-app-over-wifi-android-
studio/) – [Athira Reddy](https://stackoverflow.com/users/11120516/athira-
reddy "115 reputation") May 2 '19 at 14:08

 |  show **6** more comments

##  36 Answers 36

[ Active](https://stackoverflow.com/questions/2604727/how-can-i-connect-to-
android-with-adb-over-tcp?answertab=active#tab-top "Answers with the latest
activity first") [ Oldest](https://stackoverflow.com/questions/2604727/how-
can-i-connect-to-android-with-adb-over-tcp?answertab=oldest#tab-top "Answers
in the order they were provided") [
Votes](https://stackoverflow.com/questions/2604727/how-can-i-connect-to-
android-with-adb-over-tcp?answertab=votes#tab-top "Answers with the highest
score first")

1

[2](https://stackoverflow.com/questions/2604727/how-can-i-connect-to-android-
with-adb-over-tcp?page=2&tab=votes#tab-top "Go to page 2") [
Next](https://stackoverflow.com/questions/2604727/how-can-i-connect-to-
android-with-adb-over-tcp?page=2&tab=votes#tab-top "Go to page 2")

1195

[](https://stackoverflow.com/posts/3623727/timeline "Timeline")

## Manual Process

### From your device, if it is rooted

According to [a post on xda-developers](http://forum.xda-
developers.com/showthread.php?t=623828&page=3), you can enable ADB over Wi-Fi
from the device with the commands:

    
    
    su
    setprop service.adb.tcp.port 5555
    stop adbd
    start adbd

And you can disable it and return ADB to listening on USB with

    
    
    setprop service.adb.tcp.port -1
    stop adbd
    start adbd

### From a computer, if you have USB access already (no root required)

It is even easier to switch to using Wi-Fi, if you already have USB. From a
command line on the computer that has the device connected via USB, issue the
commands

    
    
    adb tcpip 5555
    adb connect 192.168.0.101:5555

Be sure to replace `192.168.0.101` with the IP address that is actually
assigned to your device. Once you are done, you can disconnect from the adb
tcp session by running:

    
    
    adb disconnect 192.168.0.101:5555

You can find the IP address of a tablet in two ways:

_Manual IP Discovery:_

Go into Android's WiFi settings, click the menu button in the action bar (the
vertical ellipsis), hit _Advanced_ and see the IP address at the bottom of the
screen.

_Use ADB to discover IP:_

Execute the following command via adb:

    
    
    adb shell ip -f inet addr show wlan0

To tell the ADB daemon return to listening over USB

    
    
    adb usb

## Apps to automate the process

There are also several apps on Google Play that automate this process. A quick
search suggests
[adbWireless](https://play.google.com/store/apps/details?id=siir.es.adbWireless&hl=en),
[WiFi
ADB](https://play.google.com/store/apps/details?id=com.ttxapps.wifiadb&hl=en)
and [ADB
WiFi](https://play.google.com/store/apps/details?id=com.ryosoftware.adbw&hl=en).
All of these require root access, but _adbWireless_ requires fewer
permissions.

[share](https://stackoverflow.com/a/3623727 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/3623727/edit)

[edited Apr 3 '19 at 13:57](https://stackoverflow.com/posts/3623727/revisions
"show all edits to this post")

[](https://stackoverflow.com/users/1313233/rkachach)

[rkachach](https://stackoverflow.com/users/1313233/rkachach)

12k55 gold badges2828 silver badges4747 bronze badges

answered Sep 2 '10 at 3:59

<img
src='data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAIAAgAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8Aw/hprGg+M9P1iO68W2uqa/d8M8UDqIowASOVAU89Cc12l34r+Hnw80FdMvNMuNagjczGF7V/LkcJuLq5ARwB3UnB4615PP8As023xE0JdU8Ny3Fpd+YyTxzjy0uWJzuCjGznsBj+vjHh/U9d+CPjC90bxZFe6ONwaaCYyZ2ru2NEpOHXdyMZ3cjJr82eGpyvOm7uP2ba/f8A8A0qtxjFNbLQ+mLz9sTQ2e3srLwUiW2f3TSIcAdM8KcVh+OPi5ZeILR11Wztbdy2Y7a1Xc7egJ/wrgfG/hi7kv8A7V4bNhqEcikxSWlx5rKATnbjt7ds4JJBrnZ9J1e0gW2i06a51OCYrPKN4ZWIB24zxjn06mm6dKpGLScb/f8ApYy51s0fbHww+EWva146gvftjJbxIJo7FZNkU8pHyBjg4XJBJA7V8rft03niC+1cz+KL601e8tgttBY6VpgtrezbZuZGdy8jMrEqfmXJQnbxgfoH4d1a3+FMuoa5dq0q2tqscEWcj5E2oPxZj+lfAfxk1ez+IXjT7IL2SRGuG1LUZZV3KLkiRSqL6EOwPbO49jmcBVp4Omot3d390V/m9/IqtNRaUXseW/DTxKPAmlw3N3YT6lcCEyWME0pWJXcq3mhecupRQSNudig5HFeh/ALxlruvfFW7j1C2kjF6Wu3WdMYGPvc+vFZ2l+DDNNaSMDDpOnl5EFwfNijTP3QCQNue23oMV2eq/Few0M6tcGwW3eK3jtbW5jgKtJu4Y5wMDiuirVo4xTjT9523+e3Y3pKlKEpLXb5v1P/Z'
width='32' height='32' />[](https://stackoverflow.com/users/251050/brian)

[Brian](https://stackoverflow.com/users/251050/brian)Brian

15.9k33 gold badges2424 silver badges2626 bronze badges

  * 3

Do you need root access to do this? I seem to be able to run the commands
using terminal, but it doesn't actually seem to work... – [J
J](https://stackoverflow.com/users/425769/j-j "1,420 reputation") Jun 11 '11
at 4:28

  * 6

@ J J - Unfortunately, yes. Root required. –
[Kingsolmn](https://stackoverflow.com/users/549510/kingsolmn "1,768
reputation") Jun 11 '11 at 19:38

  * 178

For the second solution (`adb tcipip 5555` and `adb connect ...` there's no
root necessary. – [Ridcully](https://stackoverflow.com/users/61479/ridcully
"20,746 reputation") Feb 22 '12 at 6:58

  * 11

`adb tcpip <port>` still requires either `ro.kernel.qemu` property to be set
(running in emulator mode), `ro.secure` to be 0 (i.e. a rooted device), or
`ro.debuggable` and `service.adb.root` to be set to 1. `adbd` simply won't
open a TCP/IP connection if none of the above is met. See
[netmite.com/android/mydroid/system/core/adb/adb.c](http://www.netmite.com/android/mydroid/system/core/adb/adb.c)
`adb_main` parts about the `secure` variable. `adbd` on my unrooted 2.3.7
Android does not enter TCP/IP mode at all. –
[soulseekah](https://stackoverflow.com/users/482864/soulseekah "7,082
reputation") Oct 22 '12 at 9:03

  * 2

Great! Second solution really doesn't require root! – [Grzegorz
D.](https://stackoverflow.com/users/1635803/grzegorz-d "1,326 reputation") May
30 '13 at 20:43

 |  show **26** more comments

131

[](https://stackoverflow.com/posts/3740005/timeline "Timeline")

This is really simple if your phone is rooted.

Download a terminal emulator from [Google
Play](https://en.wikipedia.org/wiki/Google_Play) (there are lots that are
free). Make sure that your Android device is connected to your Wi-Fi and get
the **Wi-Fi** IP address. Open the terminal program and type:

    
    
    su
    setprop service.adb.tcp.port 5555
    stop adbd
    start adbd

Now go to your computer (assuming that you are using Windows) and create a
shortcut on the desktop for "cmd.exe" (without the quotations).

Right click on the cmd shortcut and choose `"Run as Administrator"`

Change to your `android-sdk-windows\tools` folder

**Type:**

    
    
    adb connect ***wifi.ip.address***:5555
    
    (example: adb connect 192.168.0.105:5555)

adb should now say that you are connected.

**Note:** if you are too fast to give the connect command it may fail. So try
at least two times five seconds apart before you say this doesn't work.

[share](https://stackoverflow.com/a/3740005 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/3740005/edit)

[edited Mar 16 '14 at 6:48](https://stackoverflow.com/posts/3740005/revisions
"show all edits to this post")

[](https://stackoverflow.com/users/63550/peter-mortensen)

[Peter Mortensen](https://stackoverflow.com/users/63550/peter-mortensen)

25.2k2121 gold badges9090 silver badges118118 bronze badges

answered Sep 18 '10 at 1:28

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAADPklEQVRYha1XP0wTURz+7riQnuRs1QBtE0MktSYaaNmIGxS0A2yODsAgHQy4iKMsLiYmwmC7yGgMrAxnBJmIEhUBJ0qBGLW0hBjxiq1Ceg74zrt3791Jet/2/rTfe999v9/7/YT576t6t78dBAMbE1j5uW2MR0J9mNyZBQuDjQkokoyhph7m+szeIh58nWGuRX1hpIJJiJmCCl3XjYVUMGnZONTUg5FQH5N8NNyPyZ1ZTO3O/Tf5RV8Yj1oG8Tx6F93+dkjZSh4LPz6CqNCpXEL81AWLCuSGRAlCTkDmyT4WecQXQqo5iW5/O0RBMOYlAMgUVHSdboPwdyEVTCK1lbYpAQDaUdlCTh9CEWULecQXwnDzdST8MQsxgQgARAUCogINRZShSLJtnkA7KkOrli1z09Ex9AbiNvIlLYuB3MSxAoC7CrSstPF4n4UmflvaQLqgYvlgEwD+HYDnBRY5/c1pctozAPC+lEO6oOLdQc5yoLpgqnOcDLYrRdw4d9VQIVh/Bq+1daabl0pZ1IsSLsvnmZ7oaGhFvSgBOnD/8zOkiyryh99s+4SnxZe6U5yz/vwkmNqdc8wToluc1wq3PCEC9mTjFTnvEGZPGSZ0i3MvDgHY84Rk3qSIMjXjLbSjsu3/jaFbnNcKbp5gkfOM4xW52XN1V273jjvFeUdDa03kv6qHjnlC0qplrMQeM388s7dYEzkAKJKM+Ood5tpgYwJ1n26eHWfdlHwWuj44KchNl0pZG/louP/YA05x6gWc8owRBbw49fIQgD3PWKKSFadegpVnjCEvTr0CL8+ILHLeA+UVudlzEu/h8SoT8gxNFBZiK6O6bRVAxBfEreYkvvzec3zPtWrZsW9oa2iBU98hsogftgxgOnoP1wJx1/fcrZ7IFFRUHfoOw4Tkxj2M8tmt7nfqG7KVPBb215AIxADY+w7JiZh1CF6ecKonMsUX6DI1JOaKWyRS0+QfDrYwvPnEMseq+83g9Q0blTxe7a8ZY3PFLbGIMwWVm7sJaOO51ROZomppy4gKhgd4xCxy+pu79Q0AkKvsYH5/Fb2BuEUFYbm0qfOIWeRmTO3OOb4ddGsf8YUwHR0zVHijreMPai/nYKebMGcAAAAASUVORK5CYII='
width='32' height='32' />[](https://stackoverflow.com/users/451164/norman)

[norman](https://stackoverflow.com/users/451164/norman)norman

1,31111 gold badge88 silver badges33 bronze badges

  * 6

This answer was better for me because it explained that which part should be
performed on the device and which on the computer. –
[Eduardo](https://stackoverflow.com/users/914874/eduardo "3,697 reputation")
Jul 14 '12 at 17:14

  * 5

**BEFORE** "adb tcpip 5555" **DO** "adb kill-server". **AFTER** "adb connect
192.168.0.101:5555" **DO** "adb devices" **OR** "adb shell" (connect doesn't
start shell). – [samis](https://stackoverflow.com/users/1105214/samis "5,460
reputation") Jul 25 '13 at 15:30

  * I tried `adb tcpip 5555` and then the other person executed `adb connect myIP:5555` on their PC. He could install an app to my phone but he could not debug it remotely. Is it possible to debug remotely? On my phone there was a dialog `waiting for debugger` forever. – [Angelina](https://stackoverflow.com/users/9188790/angelina "738 reputation") May 2 '19 at 11:37

  * Does this make the settings persistent across reboots ? – [Hritik](https://stackoverflow.com/users/2251364/hritik "406 reputation") Jul 20 '19 at 14:12

  * Does this work with ipv6 address via mobile internet? – [CaptainFreedom](https://stackoverflow.com/users/4007106/captainfreedom "87 reputation") Nov 27 '19 at 6:26

add a comment  |

91

[](https://stackoverflow.com/posts/28084202/timeline "Timeline")

  1. Connect device via USB and make sure debugging is working, then run:
    
        adb tcpip 5555
    adb connect <DEVICE_IP_ADDRESS>:5555

  2. Disconnect USB and proceed with wireless debugging.

  3. When you're done and want to switch back to USB debugging, run:
    
        adb -s <DEVICE_IP_ADDRESS>:5555

To find the IP address of your device, go to `Settings > Wi-Fi > Advanced > IP
Address` on your device or run `adb shell netcfg`.

No root required. Only one device can be debugged at a time.

See [this XDA post](http://forum.xda-
developers.com/showpost.php?p=7594419&postcount=9).

The `adb` command is located in the `platform-tools` folder of the Android
SDK.

[share](https://stackoverflow.com/a/28084202 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/28084202/edit)

[edited Jan 28 '15 at 5:29](https://stackoverflow.com/posts/28084202/revisions
"show all edits to this post")

<img
src='data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAIAAgAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+q/FfifTvAfhTVfEWrSeXp+m27XEpUZJAHCj3JwB7kV+Zfjz4tfG/wCMutvrWmy61Z6JNO0tjY2U7QQRRngDIK7uB9498kYzX6Y/EHwZbfEHwFr3hu7GYdSs5IM4ztcjKNjIzhgp/CvjuyTxlYWfhjQrLS7KLTobNbaeeRTujkjG12LbhgbgcDbnA9a8HEV5UUuVK77nq4DCwxLfPfTsbn7Lf7Rni+DxLpnw8+Itvc3Nzfs66dqlyS0wwpYRyPyJBwQGJ3ZIzkdPr6eIc18Z/BbRvFWrfEjQrjVpobyfTtU81ESJNscRR1k+ZQOB15z8yrz1B+zp25NOhWdWN3v5bHPjcOsPUtHZ99yxE5HRjXhX7Rem20Elo8EgtZbqOVmSOIEyMAQWAI5PzjOOenrXp+teK49HIjCGSUjt0FebePrlPF/hXU9P1EJcSbGuLORxtaOZRkBT1UsBtyP7x4OcV11sE8RTcb2fQywmM+qVlU3XU89/ZU1OKz8TXcNxNM26xcKZUEewK6AnaOg5A/GvpySaGbISQSEdQDk18nfDrw1qHhbxLLPIz+RNaPCwOMMGaNlz9Cr598V6lf6zcQxvcIwWZVLAr2qMNhHTp2nvqXjsSsRXc4baH//Z'
width='32' height='32'
/>[](https://stackoverflow.com/users/1690292/davidwroxy)

[davidwroxy](https://stackoverflow.com/users/1690292/davidwroxy)

91311 gold badge1212 silver badges3636 bronze badges

answered Jan 22 '15 at 8:31

[](https://stackoverflow.com/users/1858768/ribin-haridas)

[Ribin Haridas](https://stackoverflow.com/users/1858768/ribin-haridas)Ribin
Haridas

1,5901010 silver badges1717 bronze badges

  * 2

Actually, you can connect many devices at a time, if you follow the right
order. Just set the tcpip to 5555 individually for each phone, then issue the
connect command for each phone and voilá, they are all connected to adb. –
[andreszs](https://stackoverflow.com/users/161293/andreszs "2,263 reputation")
Feb 16 '15 at 18:53

  * Debugging is a bit slower if my phone is connected this way. Also, sometimes it falls asleep and that causes an immediate disconnect. – [Aron Lorincz](https://stackoverflow.com/users/1370376/aron-lorincz "1,537 reputation") Jul 21 '15 at 13:33

  * On some devices, the delay between _adb tcpip_ command and _adb connect_ command has to be very low otherwise it does not work. Also, for me it worked by doing `adb tcpip 5555 && adb connect <DEVICE_IP_ADDRESS>:5555` – [vhamon](https://stackoverflow.com/users/4419618/vhamon "418 reputation") Jul 24 '18 at 9:49

add a comment  |

60

[](https://stackoverflow.com/posts/16004613/timeline "Timeline")

Assume you saved adb path into your Windows environment path

  1. Activate debug mode in Android

  2. Connect to PC via USB

  3. Open command prompt type: `adb tcpip 5555`

  4. Disconnect your tablet or smartphone from pc

  5. Open command prompt type: `adb connect IPADDRESS` (IPADDRESS is the DHCP/IP address of your tablet or smartphone, which you can find by Wi-Fi -> current connected network)

Now in command prompt you should see the result like: connected to
xxx.xxx.xxx.xxx:5555

[share](https://stackoverflow.com/a/16004613 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/16004613/edit)

[edited Sep 16 '18 at
18:01](https://stackoverflow.com/posts/16004613/revisions "show all edits to
this post")

[](https://stackoverflow.com/users/2405040/shashank-agrawal)

[Shashank Agrawal](https://stackoverflow.com/users/2405040/shashank-agrawal)

17.8k77 gold badges5252 silver badges8686 bronze badges

answered Apr 14 '13 at 21:36

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAAEPklEQVRYhb2XXUhbZxjH/zmJxnY5Xexguyg6OrBzFNNBlXH0pBfFOnqxaLsP2PSmk2WZQ4RNo7GbdB1UzdhASowUqmDjzeiKejf6sZrUXri6fDjaLlFrB8Xuoq5fF53QPrtw77vzniTnuFX6QCC/8xzyPO/7/M//vLGoikTIERWuGhxq7sFnbW/ya54GLybHTwgsO5wYiwTz3uPeU49YdCIvS7kKfzfwIwaHoqiqqhV+uL0jlMW+ll40Nvn5dZ/vmMCHmnsAWPIyVEUiVZHok4/dNDNzlvShKhIF+3305MnjnMwiHOoiVZHo/r0VgYmIAp0HiNXRM/IVZqEvlqu4tgnWAGMionQ6Tqpi5Q1o2bK/bmt+DXzYg4+a33gqDcQuPwYAdHcdRCw6kcV8BPlGwa6zletZu91sBFpmwVat52eiARaBzgNZ/Ew0oF21ni1aH8g14/LySpSV7UL5a5WCRhYXfsXslQso2vScYf7OnWVDjcBsxul0nNzVVvK3v0XXrv5MC/Nz9OXh98hdbaWZmbOmee04cmnExrpq7wjBYpGg57Ky16G6PYhFJ7B9+07IW4rx04XTqHDVcKMyy/taegGA74TA65lxOh2n8GCAc2S0T9CNWd5II7bJ8RN8Jmw+Wu7wh1FQYIcsF/OxORxO2AuLOBvlhwYDggYePLz73zRARHSk5wNSFYkio300fmaIVMVKba37+ErM8kYagNlzfuPGVXJX27hPJBMxamvdR6oiUTIRM83rm9D7hKkGfjgdyjnPZCJGp0b7TPNmGpBkh5OrHwD0XFBgh+xwQh9rc95kmteGLDuzWVUkwbH0vBE+QLT2ZGhHwNiW9/n8hzfCB8ZO9WMo3M1XrmVraYnlCADMpaax+tcjzKWmoeXKqlqUvvwqHHIxfC29cLlqYC8sQm3d+9i27RUAMMzriwPAyPBR/t3mafDC5zvGLzx4eFdgroP/6QOeei889V6+s54GLz+yjUWC5hpYz3Nuln8qDSwtXcP5c9+jwlWDHeW7YS8swu7KvZi9ch6p5CVsef4Fw7xrl2qoAeF13NjkF2yzscmPF18qQUnpDuGEDACp5CWkUtPYvFk2zFsAobi+BrRuRUS0MJ/KMg8j1m+z1mgiOiPSRiadoEDnQUJba62Q+KL7XYHXoxFWLNeMswpnktTd9TY/FUNVJErEo/yG/XVbBWYvDVZUz9pirAEts5jPpOhw4B1yV1uFQ7ANAIZPfoWB4+f4WPSsFaaeZdkpCiwSFO5dXJjDyPDXmLp4BkQ5/gGwTuLxKb4DWg72++j+vRX+0bP2Ew510a1biwLni3Q6vnYqZg20frpXaIDxRmuAFWYasLGdiP9yEYn4FHKxkU8Axl7PIpNJYOTkUcSikwD+HQV/FwDA8vIS/lz5A6urjzjfvn0TQP53xW/XZw293r2nHt9+04LjA5/j95vXsyTwNxKH5Gar67EWAAAAAElFTkSuQmCC'
width='32' height='32'
/>[](https://stackoverflow.com/users/2255623/maplelover)

[MapleLover](https://stackoverflow.com/users/2255623/maplelover)MapleLover

65555 silver badges77 bronze badges

  * Thanks for sequence of steps and mentioning exactly when to disconnect PC. – [Manju](https://stackoverflow.com/users/1019498/manju "693 reputation") Oct 26 '19 at 15:29

add a comment  |

53

[](https://stackoverflow.com/posts/2605411/timeline "Timeline")

From `adb --help`:

    
    
    connect <host>:<port>         - Connect to a device via TCP/IP

That's a command-line option by the way.

You should try connecting the phone to your Wi-Fi, and then get its IP address
from your router. It's not going to work on the cell network.

The port is 5554.

[share](https://stackoverflow.com/a/2605411 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/2605411/edit)

[edited Mar 16 '14 at 11:07](https://stackoverflow.com/posts/2605411/revisions
"show all edits to this post")

[](https://stackoverflow.com/users/63550/peter-mortensen)

[Peter Mortensen](https://stackoverflow.com/users/63550/peter-mortensen)

25.2k2121 gold badges9090 silver badges118118 bronze badges

answered Apr 9 '10 at 6:14

<img
src='data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAIAAgAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A9p179orW7v4azeO7GG4stBEG+KS9PkOyyEJGxVsEqWZSGUAEdyK+eNX+O03j6O9umjur25OI4WtpsYIHLnqDz25Bya5rx/r+r6h8K9TfTY7oaNP5Fpb2s7OfJbzFIhKnoUKduOQR1NSfC3wJeaT8OraZ7gWerXJaRhcxkbBk4Tggj1/+tXFiKvOk3Gz2/wCCd2Hy/wBvV5FK8d7/AKD9R0LW7ptM1KGWLStTLRReUgJ3RPJ8wkbGScnOQBgDgdcw6r4du9Z025EWmpN9lumQz+eqGQgHJGSAQc/yrpobbxOuiQXTSx6nILlY87sfu8E5B74Ix1/GvSNB8MC38F6bHPGWkkgE7+aMOSw3fN7jOPwpYXmqNp9DHMsEsJKLjszmbjSNOvoW8Fwai9w1pIL54wm53hUo6bxkBd2AC2OScD253UtYFxqx0WUmCc/KjAgYXPUZ4OOhFfTWk6R8FoLVdKvdd1O81VYkjuNS0+8ukUEDjiMhCB2O05968I+P3wPvPA0kPi3StSbxt4Hdwx1GEKLyy5/5abQFcDoWAUjuO9ZYulOrJyi7o+ow0JYOMVVpShzbNppP0bIvCnhe81DXUAmY2MBE1xtyASCOcZwM9Mc9c8Yr1XUb9DEyjHK9M15h4A+ImkaTpl9bmWG3igtnv01YFixVVJeCZW5P3cggD7+OetP8OfESDxr4RtNetl2QXiMxjR9wjIYqRnAJGQe1dGClCK5XpJ/1/XzPFzuNf2t5xtFLT07/AH6H/9k='
width='32' height='32' />[](https://stackoverflow.com/users/88905/nathan)

[Nathan](https://stackoverflow.com/users/88905/nathan)Nathan

5,47788 gold badges4141 silver badges5353 bronze badges

  * 1

I had tried that with 5555-5558 and now 5554 and it it does not work for some
reason. Basically from a command line: adb kill-server adb connect
10.10.10.100:5554 with the result being * daemon not running. starting it now
* * daemon started successfully * unable to connect to 10.10.10.100:5554 I can
ping the ip of the device from the dev workstation. When the output states
"daemon started successfully" shouldn't it be referring to the daemon on the
device? Is it attempting to use the emulator possibly? How do I
ensure/validate the daemon is running on the device? thanks –
[JDM](https://stackoverflow.com/users/312443/jdm "9,609 reputation") Apr 9 '10
at 21:00

  * 2

you should first `adb tcpip port` as the default is debugging over usb. After
the latter you can connect `connect host:port` and it should work – [Aiden
Strydom](https://stackoverflow.com/users/929391/aiden-strydom "1,129
reputation") Mar 13 '13 at 10:27

  * "adb tcpip port" literally? that just returns the string "error: device not found" -- is there a typo? Or should I replace something here? – [BrainSlugs83](https://stackoverflow.com/users/398630/brainslugs83 "4,861 reputation") Aug 8 '13 at 17:46

  * 3

AHHH!! Figured it out, the default port number for CyanogenMod is 5555! NICE.
:D – [BrainSlugs83](https://stackoverflow.com/users/398630/brainslugs83 "4,861
reputation") Aug 8 '13 at 17:48

  * @Michael it might work on some cell networks, but their network configurations are basically black boxes -- you don't know when/if you're behind a firewall, if ports are being blocked, if NAT translation is going on, etc. – [BrainSlugs83](https://stackoverflow.com/users/398630/brainslugs83 "4,861 reputation") Sep 2 '13 at 22:21

 |  show **2** more comments

43

[](https://stackoverflow.com/posts/33334312/timeline "Timeline")

**For Windows users:**

**Step 1:**  
You have to enable Developer options in your Android phone.  
You can enable Developer options using this way.  
• Open Settings> About> Software Information> More.  
• Then tap “Build number” seven times to enable Developer options.  
• Go back to Settings menu and now you'll be able to see “Developer options”
there.  
• Tap it and turn on USB Debugging from the menu on the next screen.  

**Step 2:**

Open cmd and type adb.  
if you find that adb is not valid command then you have to add a path to the
environment variable.  

•First go to you SDK installed folder  
Follow this path and this path is just for an example.
D:\softwares\Development\Andoird\SDK\sdk\platform-tools\;
D:\softwares\Development\Andoird\SDK\sdk\tools;  
• Now search on windows system advanced setting  

• [](https://i.stack.imgur.com/XldFs.jpg)

Open the Environment variable.

[](https://i.stack.imgur.com/8FSeg.jpg)

then open path and paste the following path this is an example.  
You SDK path is different from mine please use yours.
D:\softwares\Development\Andoird\SDK\sdk\platform-tools\;  
D:\softwares\Development\Andoird\SDK\sdk\tools;  

[](https://i.stack.imgur.com/zrOWY.jpg)

**Step 3:**

Open cmd and type adb. if you still see that adb is not valid command then
your path has not set properly follow above steps.

[](https://i.stack.imgur.com/qjqE3.jpg)

Now you can **connect your android phone to PC.**

Open cmd and type adb devices and you can see your device. **Find you phone ip
address.  
**

[](https://i.stack.imgur.com/nEHrz.jpg)

Type:- adb tcpip 5555

[](https://i.stack.imgur.com/yzb0E.jpg)

Get the IP address of your phone

    
    
    adb shell netcfg

Now,

    
    
    adb connect "IP address of your phone"

Now run your android project and if not see you device then type again adb
connect IP address of your phone

[](https://i.stack.imgur.com/2tIbF.jpg)

[](https://i.stack.imgur.com/GW7IZ.jpg)

**For Linux and macOS users** :

Step 1: open terminal and install adb using

# sudo apt-get install android-tools-adb android-tools-fastboot

Connect your phone via USB cable to PC. Type following command in terminal  

    
    
    adb tcpip 5555

Using adb, connect your android phone ip address.

Remove your phone.

[share](https://stackoverflow.com/a/33334312 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/33334312/edit)

[edited Oct 31 '19 at
22:51](https://stackoverflow.com/posts/33334312/revisions "show all edits to
this post")

[](https://stackoverflow.com/users/3682839/tuxayo)

[tuxayo](https://stackoverflow.com/users/3682839/tuxayo)

77611 gold badge99 silver badges2020 bronze badges

answered Oct 25 '15 at 19:49

<img
src='data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/4QAqRXhpZgAASUkqAAgAAAABADEBAgAHAAAAGgAAAAAAAABHb29nbGUAAP/bAIQAAwICAwICAwMDAwQDAwQFCAUFBAQFCgcHBggMCgwMCwoLCw0OEhANDhEOCwsQFhARExQVFRUMDxcYFhQYEhQXFAEDBAQFBAUJBQUJFA0LDRQUFBIUFBQUFBQVFBQVDxQVERURExQVFRUQEw8VEA8NDRURFRUVEBIVEg4VFQ8NEBUP/8AAEQgAIAAgAwERAAIRAQMRAf/EABoAAAICAwAAAAAAAAAAAAAAAAYIBQcCAwT/xAApEAABAwIEBgIDAQAAAAAAAAABAgMEBREABhIhBwgiMUFRE4FhcpFC/8QAGwEAAQQDAAAAAAAAAAAAAAAABAECAwYABQf/xAAwEQABAwEFAwsFAAAAAAAAAAABAAIRAwQFEiExE4GxFBUiQUNRUmGRofAGMkJx8f/aAAwDAQACEQMRAD8AaUQ0RWA448Bt/kXxBjLjACXZCm2S5bI06KmwKzc+hjC1yVlSn3qYiJbkJ1JUAn2oWvgZxIWwYA7MFdIYWkXtYfnDZUwbCVSl88uRpMtuFNqioHyAKSZEZYbI/YAgfeLRzSHjFSdPtxVN5zrtEVG5eWaMahzQ5UZpLUyHMMnU+hvUw0CNGsazZRTsUhQB+98a02NzauyOsT8Kut03bbL3p7WkAwd7jE7gCjKm8xGRlUOHUJNVbpceRf4lTrJ12JBtYkeMCckqvqOptzI1Rl62GtcjGvtQ6JMSJImJjTrGn68lgvmR4cvdKc5Ujq9yQNsTi7rT4FVje1m8fFIhTuFkuQ0kilUNatgA5HJ2/mLabLVblj91Quge0cqV4pzq/wAPq69Qak2qM1qU8wtsFLTralFQKD5AvpPogjAuyIeTOa6ldN77OzNYw6QPSP6j/gNRMx8UGFPvP04USEktNM1bqbfcJGyEdzpturtew92TZ4Zc0kHvCd9S3868bC27yesEx5K6JfLnLktgtMZdG25bjOJANvBCsIKjhq8/Ny5ryYAZPKqlx+tMpUiLXKq+4q5Dja9QAt272+z4GC3Pee14JuLF+EblE0rLD+cA65mSW1V5zRC2mp4WbWB6bpKiAe9thsN/cWINP3TvCkfUdSMsBARFQXJtHacYi0qG6pNi5HjOjSFXA03SATbbt4BBO25pe14gmEOamIwSpbL+cEPPpiuGRS6gon5WFqcW4kC3UixsgEfg3294Y+g9pkEEbvdY4uywes6r/9k='
width='32' height='32' />[](https://stackoverflow.com/users/4643247/raghav-
thakkar)

[Raghav Thakkar](https://stackoverflow.com/users/4643247/raghav-thakkar)Raghav
Thakkar

28255 silver badges1111 bronze badges

add a comment  |

35

[](https://stackoverflow.com/posts/44460975/timeline "Timeline")

# From a computer on a non-rooted device

(Note that this can be done using a rooted device as well, but you can use a
shell on a rooted device which doesn't require a USB connection)

Firstly, open command prompt (CMD). If you use Android Studio or IntelliJ
there is a console included in there you can use.

If you have adb added to the path, you can skip the cd part.

* * *

If possible, open the SDK location, right click, and press "start command
prompt here". Not all have this option so you have to do this (/these)
commands as well:

Windows: change the drive (if applicable)

    
    
    D: 

And access the sdk and platform tools. Replace this path with your SDK
location:

    
    
    cd /sdk/path/here/platform-tools

Now you have access to the Android debug bridge.

* * *

With the device connected to the computer, do:

    
    
    adb tcpip <port> 
    adb connect <ip>:<port>

Where `<port>` is the port you want to connect to (default is `5555`) and
`<ip>` is the IP of the device you want to connect to.

Please note: `5555` is the default port and just writing the IP address
connects it. If you use a custom port you can at least improve the security a
bit. USB debugging over Wi-Fi can be abused, but only if the device is
connected to the computer who wants to abuse the device. Using a non-default
port at least makes it a bit harder to connect.

If you use a custom port, make sure to add it after the IP. Writing no port
connects to `5555` and if you didn't use that the connection will fail.

You can find the IP address of a device in two ways:

  * Depending on your device, the exact names may vary. Open settings and go to **About device** -> **Status** -> **IP address**

  * Use ADB to get the IP

From the console, do:

    
    
    adb shell ip -f inet addr show wlan0

* * *

And once you are finished with the connection, you can disconnect the device
from your computer by doing:

    
    
    adb disconnect <ip>:<port>

Or no IP to disconnect all devices. If you used a custom port, you **must
specify which port to disconnect from**. The default is 5555 here as well.

To disable the port (if that is something you want to do) you do this command
with the device connected:

    
    
    adb usb

Or you can restart the device to remove the tcpip connection

# From a computer on a rooted device

Firstly, you need access to the shell. You either connect the device using a
usb cable and use `adb shell` or download an app from Google Play, FDroid, or
some other source.

Then you do:

    
    
    su
    setprop service.adb.tcp.port <port>
    stop adbd
    start adbd

And to connect the device, you do as in the non-rooted version by doing `adb
connect <ip>:<port>`.

And if you want to disable the port and go back to USB listening:

    
    
    setprop service.adb.tcp.port -1
    stop adbd
    start adbd

* * *

You can also use an Android Studio plugin to do it for you (don't remember the
name right now), and for rooted users there's also the option of downloading
an Android app to set up the phone connection (adb connect is probably still
required).

Some phones have a setting in developer options (this applies to **some**
unrooted phones, though probably some rooted phones too) that allows for
toggling ADB over Wi-Fi from the device itself without root or a computer
connection to start it. Though there are few phones that have that

[share](https://stackoverflow.com/a/44460975 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/44460975/edit)

[edited Jun 6 '19 at 19:24](https://stackoverflow.com/posts/44460975/revisions
"show all edits to this post")

answered Jun 9 '17 at 14:58

[](https://stackoverflow.com/users/6296561/zoe)

[Zoe](https://stackoverflow.com/users/6296561/zoe)Zoe

19.7k1212 gold badges7777 silver badges109109 bronze badges

  * `adb shell ip -f inet addr show wlan0` Is the IP address and port support to be substituted in somewhere therE? – [Michael](https://stackoverflow.com/users/543873/michael "7,280 reputation") Jun 27 '17 at 0:38

  * not in that line. That is the shell-way to get the IP. Nothing in there should be replaced in that line – [Zoe](https://stackoverflow.com/users/6296561/zoe "19,692 reputation") Jul 25 '17 at 10:19

add a comment  |

33

[](https://stackoverflow.com/posts/7770525/timeline "Timeline")

I needed to get **both** USB and TCPIP working for
[ADB](http://en.wikipedia.org/wiki/Android_Debug_Bridge) (don't ask), so I did
the following (using directions others have posted from xda-developers)

Using `adb shell`:

    
    
    su
    #Set the port number for adbd
    setprop service.adb.tcp.port 5555
    
    #Run the adbd daemon *again* instead of doing stop/start, so there
    #are two instances of adbd running.
    adbd &
    
    #Set the port back to USB, so the next time ADB is started it's
    #on USB again.
    setprop service.adb.tcp.port -1
    
    exit

[share](https://stackoverflow.com/a/7770525 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/7770525/edit)

[edited Mar 16 '14 at 6:49](https://stackoverflow.com/posts/7770525/revisions
"show all edits to this post")

[](https://stackoverflow.com/users/63550/peter-mortensen)

[Peter Mortensen](https://stackoverflow.com/users/63550/peter-mortensen)

25.2k2121 gold badges9090 silver badges118118 bronze badges

answered Oct 14 '11 at 16:17

<img
src='data:image/png;base64,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'
width='32' height='32'
/>[](https://stackoverflow.com/users/864414/transistor1)

[transistor1](https://stackoverflow.com/users/864414/transistor1)transistor1

2,7452020 silver badges3939 bronze badges

  * Doesn't work: adbd not found. adbd is normally launched via start adbd. But maybe there's a script/executable in some folder? – [KrisWebDev](https://stackoverflow.com/users/2227298/kriswebdev "8,174 reputation") Aug 18 '13 at 8:30

  * 1

On my gnex, it's `/sbin/adbd`. That may vary by phone. Of course, you must be
rooted... If you're not rooted, you won't be able to access /sbin. –
[transistor1](https://stackoverflow.com/users/864414/transistor1 "2,745
reputation") Aug 18 '13 at 13:12

add a comment  |

32

[](https://stackoverflow.com/posts/14576927/timeline "Timeline")

To connect your tablet using TCP port. Make sure your system and device is
connected to same network.

  1. Open console _cmd.exe_
  2. Type `adb tcpip 5555`
  3. Go to _System - > Development option -> USB debugging_ \--> Uncheck it for TCPIP connection
  4. Type `adb connect 192.168.1.2` this is your device IP address
  5. Connected to 192.168.1.2

**Connected using port forward** Try to do port forwarding,

adb forward tcp:`<PC port>` tcp:`<device port>`

like:

> adb forward tcp:5555 tcp:5555.
>
> C:\Users\abc>adb forward tcp:7612 tcp:7612
>
> C:\Users\abc>adb tcpip 7612 restarting in TCP mode port: 7612
>
> C:\Users\abc>adb connect 10.0.0.1:7612
>
> connected to 10.0.0.1:7612

If you get message **error: device not found** connect a usb device to system
then follow same procedure.  
for a rooted device

    
    
    setprop service.adb.tcp.port 5555
    stop adbd
    start adbd

[share](https://stackoverflow.com/a/14576927 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/14576927/edit)

[edited Jun 24 '15 at 6:31](https://stackoverflow.com/posts/14576927/revisions
"show all edits to this post")

answered Jan 29 '13 at 6:28

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAADh0lEQVRYhbVXP0wTYRx9dy30KIUymFRByt/SAilMQEVkMmIFE9SEwmCciDpaiESiAQYdEBpHiUYnI+BijEFQJiBQ6lQE2ggUSpSkGhP+XKEunAO961057iqlb7u79r3ve/n9ft/3iDef/zCleRTKC9Xgw+sPYeobja5XGxCDUa/CvSYdlAoC1iot976xcxlfvbvc89O7ZyHGv7i2hwk3DbK8MAX1Hcu49WQV7uVdeP0h3O7z46L9O4qyVaLCz9v1GHcU4Wp1BhxDAewzDPfdbtMJfh/N7/HvobXXj0v2JZTkUlCW5qWgriIdo65tGLMpaDUKfJzeQoVJjdrytEM7rrdoQZIEbychjLm2ORdqy9NQYVJzLojxjzgj/Ep21QVZKnTePHPAygDmghRJYT4cQwHUVaaDJAjOhZaeVYErR/GTAJCcRCBDo+D+kJ6qAJVMAgBndbS4yxNEc7dP4AIL1gUWUvxKAHj27hfeT26CYQ4+Phj4iZoyDQa780WFHUMBTM7RMbsgxa9c+hHCh6lNVJjUMBekgEomUVOmweQcDZcniMriVElhFkfVghh/tTmV4ydej/xm8jNVgoJjBdkFSAnzUZJLYazfwLkw4d6Bb+MvxPidCzRmF4MgMq+5GTEytvju9K3LCkvhZUeO5JwgxYT5fR4v5OaEki8s127HgdycIKN3fJLiLKRcIGPp83ghNScIhmEERSjXbseFWIe09KxGaiBRwiyOqgVidpFmEinMR7QLk+4dECPOTUaqTxO5GHuTDqRcn540inMovLifg7F+A6wWLZRyfXpSMOkp2G06WC2RAwsIT8JEumDUUxho1+OLw4D6c1qBOLcAufM8How7DGgQmTNTczQaO5cjZ0GiXIgWnp6ncf3hCmzdPnz17kbmQKJrwblAo28wgJmFoHCB/IdEuODyBNHUtYIbj3yHxAGAkMsFWaeSYLX8/5xgT9ed4H58ucAxLHSlrVnalejTNe5csLi2itHZbVwJu3ChLA2VxWq4PLuHhMXuE3HnAuCgNi5XRQZIm+00bOGjOpaLTFy5AAA8/hA+OSNzoqZMg6qSg9tyLPeJY+WCanMqhnsKBC5Yq9I5oTabDk1dvphyw7FzgXMhQuJdD2HEuYWG8EX1vFkDS9iFo4QBiOYCfu6QzAUz8zR63wa4d0Y9hXGHgdv19DyNJAWBfon7xOPWTNFcwOaOf/aHY3DbIPu1AAAAAElFTkSuQmCC'
width='32' height='32' />[](https://stackoverflow.com/users/1232051/rinkesh)

[rinkesh](https://stackoverflow.com/users/1232051/rinkesh)rinkesh

2,5982222 silver badges2626 bronze badges

  * 2

In console write `su` first to get a rooted-console. – [Peter
Rader](https://stackoverflow.com/users/843943/peter-rader "6,478 reputation")
Aug 1 '14 at 18:31

add a comment  |

30

[](https://stackoverflow.com/posts/3465107/timeline "Timeline")

I do not know how to connect the device without any USB connection at all, but
if you manage to connect it maybe at another computer you can switch the adbd
to TCP mode by issuing

    
    
    adb tcpip <port>

from a terminal and connect to your device over wifi from any PC on the
network by:

    
    
    adb connect <ip>:<port>

Maybe it is also possible to switch to TCP mode from a terminal on the device.

[share](https://stackoverflow.com/a/3465107 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/3465107/edit)

answered Aug 12 '10 at 6:06

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAADt0lEQVRYhbWXXWxTZRjHf29zki5hiW7dMlxJt4lTSkJnKO6jAa6wmmiMW4CSyOAOLrzUxPhxQbwzGdxpIncCiUwNjURMJHrBRxh0DreFrMRsOJDCmm0aRd26th4vtvfde07PR8HxT87Fc/5v3//zPuf/PKdHmKZpsoIzmVGSsSi1NUEVh+ueoKu9DTf0HT3ueD8SqmNvT5yp/Cz9O7vU/ZMXr1liQxc/dSlDMha1xK2NITqfaUUI4ZqEk3D3s20EhGDgm+8BlGh6eMwSG7qYPRmA6dl5MpPTnlVwEtZhF9Vjwy6ezoyqBRKDQ9ddq+Al7JSEPRYPFhaVB9KZUZIdUdYFg2rhgY8/A+Cd1150rMK/pukp/NdiwRKfupRh/45OFQdqa4LU1gQ5P54lPTzGuuByLC+JwaHraH5d3cDHG/peSiczquIAVHrACdILa4H08BgnL14DqPSAF7y88ChJAIirP98yvRz+yXcX+GV2nqn8nOV+JFTHlkiYQrHoyZ/76Ybjvq2N9eztiWP4nWoyP8dAfx8jt+7wxdAIxVJZuf7Dr77lz4VFT96OloZ6Uok4XSuahl+fT8/OM7zCb3s6gsmy8bK5Gcbv5AB8eYBIQz2pnq10t7dZDmuA/7PVebli8MpIVXykYWVOtDvPCUOe0qsKxXIZ0wT990ulUlX8sQO7PVs1oJ/Cqc8B9nRvJRCwbpJKxKvi/eaEehm5VSFc/yTbn9tINjfD4JURlkolUok4HS0b2NTcxIPFgifvB9E78Kk6dmtjiKP9fRYvHP/hMvd++8NiKIBNzU1Ew+tZKBY9ef3V61iBM28d8lxQKpX5u1CouP9PYYmlUtmXt+O9z7/m5r28igMVK2yYzM/x0Ru9vPv6S2xsaiASquPtV3dx7OBufp3/3Ze3Q/cOaB5ww1rNAQnpDVkF3wrAaocIIZSr7XPAi7dDr4JrAtncDEe+PAes9rkOpzngxtuhd0hFAlL4/dNnVQn/zxxwg+SVB2Qf25/b45oDkhcTd++bTsISLz+/+bHNgbHbOYwfp25bfnzizYOWv2IPC9nn8rInoH9HJGNRAv07u+h9oeORBe3Yl9hW1bpkLMrhXduXTbiWScRawkTD66sSF0KsdsFaJuHVAbo4gDhx4aqpfzQkY1HOj2dV7PaukK4/sucVR/6D02eZyM1UiOt7O3pg/45Oz0o4zQknpGxekCe3xwa4fzjqlXGbE27YEmlm84anmLh7v6LseqwGkb1dZPywwjr2JeJcvjnlKg7wHxKYYpADKSFtAAAAAElFTkSuQmCC'
width='32' height='32' />[](https://stackoverflow.com/users/412767/christoph)

[Christoph](https://stackoverflow.com/users/412767/christoph)Christoph

30133 silver badges22 bronze badges

  * Of all the complicated answers that received massive upvotes, this 8 year old answer his the simplest and works No rooting required. Just type 'adb connect <ip>:5555' and it will be available to be deployed to. – [RogerW](https://stackoverflow.com/users/168925/rogerw "315 reputation") Sep 9 '18 at 14:34

add a comment  |

29

[](https://stackoverflow.com/posts/37669270/timeline "Timeline")

First you must connect your device via USB

Then connect your device to WIFI and get the IP address. While still connect
via usb type this in command line or via Android Studio Terminal

    
    
    adb tcpip 5555
    adb connect <device IP>:5555

You will see these messages:

    
    
    restarting in TCP mode port: 5555
    connected to 172.11.0.16:5555

Now remove the USB cable and you will still see your logcat as normal

Done. Enjoy

[share](https://stackoverflow.com/a/37669270 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/37669270/edit)

answered Jun 7 '16 at 1:45

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAADcUlEQVRYhbVXSU8UQRh9Pd2JGpKeRpOBwFUj6MkDXEwGUUmMgEAkGn+AiXE5uCTG7WIIBxw5uNxdzppoVEDFMDLozGDwJIRBExOVJS5Mz5JoMt2fB+y2uqjuGiO8U3/93lR9X9XXr2qU6Y42Ko6nAQBrNm5C/Ys4FFWFg0xnO1heMwwU34y78ZZ4AiIU0inM98dg//wJ0fj5sQTmYn2AGR+hiZoITdRE6Pv9e8SD52X6fCpJMwe7XQ2vzydfU6a7y32n6dEmVDQ0orS4iMp9Hcsq4XlFVQP1lmmiZJq+v88NP4fF8HCqFFXDrgLLy/S2bVP26RBN7WkR6m3bosXHj2hyZxNhuqONzPgI2ZblOyARLeNl+nwqSTMH9gfqbcsiOHvhJPK/4HtAhpC7d7kcLNME2bawq8sF3wNSTDZH6cfDB9Il/RfwPRAETdV1fDxyGID4O//1fsZNNnL0ODTDwGxvj7AYGc/C1wf42Hn+3HPZzXr+xjX3vYznwfsAiIimO9roXXQ72aUS8TE/uGiSIJ5HdmiQplp2ehMI+s5Fg7OTyHgRWB/QgCW3YrufjTXD8N1HVdcD99mPV5QQ1HB4ifdN/w8maiLCSr7euUUTtVVSngffAyFhihxme3uwcPO6G3+7exufzp0FiMriWVim6TkLFCKBisHb2ir3ueb8Rai67ju4iN/2ZWGZjsiGOTCAuatXEMp0tiP3Mh6Ug4tSNgsrlxNOXg7vQFFCMPa2on54BFpxPI0Phw6goqER1afOQI82CX8UOXoctRcuuTFvNjLeF04z+FnySvsAD+lZsBo+wCKk6jrUcBhKSPxByHygHJ8opFPIDjxx33ti2X1gJXxg5mA3Te1udleZjTUnK/Y+wK+G01BVx04AEPuAH19Ip5AffQkAMIcGoW3Y4I3Xbq5D9cnTMFrbfLeBncTPB/z4+f6Yq5nvj0Fdv94TS614pa5qPHKJUZrubKeynVDmE+WikEpiLtaHwqsxAEBZZwGwsnfGZf8LgrA6d8a/9wHhWVBIJZEdeAxgqamCfILXi2IexXQaUBTUPXsh9oFMdxdN7tpBtmWRzCd4vSgW6X19IJ8YdRuErcLPJ/JjCY9eMyo9cWVru6d6Vm8ODUKZbI4S6wOZrn0oplMAgLV1dQAh0Cd4vaqHPXH9cNxXv27LVvwGHjsHYyN2U3oAAAAASUVORK5CYII='
width='32' height='32' />[](https://stackoverflow.com/users/3792198/joolah)

[Joolah](https://stackoverflow.com/users/3792198/joolah)Joolah

8,09399 gold badges6363 silver badges9292 bronze badges

  * This worked. However. After performing these steps, I can no longer switch back to the emulator. Suggestions? – [Tim Scott](https://stackoverflow.com/users/29493/tim-scott "13,605 reputation") Aug 28 '16 at 23:35

  * You need to restart your adb with: <adb kill-server> and then <adb start-server> – [Joolah](https://stackoverflow.com/users/3792198/joolah "8,093 reputation") Aug 30 '16 at 14:02

add a comment  |

21

[](https://stackoverflow.com/posts/33243646/timeline "Timeline")

If you want to easily connect your device to run, debug or deploy your Android
apps over WiFi you can use an open source IntelliJ Plugin I've developed.
[Here](https://github.com/pedrovgs/AndroidWiFiADB) is the code and
[here](https://plugins.jetbrains.com/plugin/7983) the plugin ready to be used.

The usage is quite simple. Here you have a gif:

[](https://i.stack.imgur.com/Fvy8z.gif)

[share](https://stackoverflow.com/a/33243646 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/33243646/edit)

answered Oct 20 '15 at 18:01

[](https://stackoverflow.com/users/3097137/pedro-
vicente-g%c3%b3mez-s%c3%a1nchez)

[Pedro Vicente Gómez Sánchez](https://stackoverflow.com/users/3097137/pedro-
vicente-g%c3%b3mez-s%c3%a1nchez)Pedro Vicente Gómez Sánchez

62588 silver badges1010 bronze badges

  * This error occures: "'adb'command not found. Review your Android SDK installation. – [rostamiani](https://stackoverflow.com/users/2085899/rostamiani "971 reputation") Oct 21 '15 at 6:44

  * 1

You have to declare a environment variable with name ANDROID_HOME. But I have
a PR pending to review to avoid this. With the version 1.2 I'm going to
publish next week the plugin will work just with IntelliJ installed :) –
[Pedro Vicente Gómez Sánchez](https://stackoverflow.com/users/3097137/pedro-
vicente-g%c3%b3mez-s%c3%a1nchez "625 reputation") Oct 21 '15 at 19:36

  * Im using mac, don't see an icon in AS? Do I need to do something manual first? – [powder366](https://stackoverflow.com/users/278174/powder366 "3,546 reputation") Oct 27 '15 at 19:20

  * 1

I've already published a new version where the ANDROID_HOME environment
variable is not needed anymore. @powder366 you need to install the plugin from
the IntelliJ plugins store of installing it manually. All the instructions
needed to install and use the plugin are in the project readme, take a look
[github.com/pedrovgs/AndroidWiFiADB](https://github.com/pedrovgs/AndroidWiFiADB)
– [Pedro Vicente Gómez Sánchez](https://stackoverflow.com/users/3097137/pedro-
vicente-g%c3%b3mez-s%c3%a1nchez "625 reputation") Nov 2 '15 at 20:03

  * @PedroVicenteGómezSánchez Thanks. I picked the wrong plugin, there exist another plugin with similar name... – [powder366](https://stackoverflow.com/users/278174/powder366 "3,546 reputation") Nov 2 '15 at 20:19

 |  show **2** more comments

11

[](https://stackoverflow.com/posts/4778876/timeline "Timeline")

As Brian said:

> According to a post on xda-developers, you can enable ADB over WiFi from the
> device with the commands
>
> setprop service.adb.tcp.port 5555
>
> stop adbd
>
> start adbd
>
> And you can disable it and return ADB to listening on USB with
>
> setprop service.adb.tcp.port -1
>
> stop adbd
>
> start adbd
>
> If you have USB access already, it is even easier to switch to using WiFi.
> From a command line on the computer that has the device connected via USB,
> issue the commands
>
> adb tcpip 5555
>
> adb connect 192.168.0.101:5555
>
> To tell the ADB daemon return to listening over USB
>
> adb usb
>
> There are also several apps on the Android Market that automate this
> process.

It works.You just need to access the android shell and type those commands...

One other (easier) solution is on the Market: adbWireless, it will
automatically set your phone.

Root is required! for both...

[share](https://stackoverflow.com/a/4778876 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/4778876/edit)

[edited Feb 7 '13 at 15:27](https://stackoverflow.com/posts/4778876/revisions
"show all edits to this post")

answered Jan 24 '11 at 5:13

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAADzUlEQVRYhbWXX2hbVRzHPze5ayZ001LL1rJ0jbTUf3SmhNI/hmmLfyi4veiD5kHYEAoFx9AXHch9EsG9in2y4Iy+DbuH2YG2lMymdFmDWS37pw0mLlIpc3SQmmy5PtST3ntyTtqa+n2793fu+X7P7/zO9/6OcXX2Kzs+PYYKwd4IAP2DI8q4jFwmxflzo+XnZ4LH2P9YC919EeX4xYUJPN19EfperCQI9kboHxwhORdldkotUMZ8bNxFfvTV94lPj7EQjyrJZybP4gGQRQhyge2IyGVSZNMJF7lhGAAVIgQ5gCleijSt59eUKU/ObUyg2w6xeplcQGxzna++TA5sZECgzlfP3kf2uT4cfuMTmg52lkWoMiFWryMXWM+vUfj7vutdOQPOtMBmRgIdA7S195O+PcuV2LgyE/Ox8S3J5W0VGfFalmXJ5Nl0AtP00ezvAsAwDBoaW3n6uddoau7keuoi9+7ewR8IkcukuL+2oiW/EhuvIG/2d2GaPrLpBN7XjwUtJ7lOhCzk4cMCqyu/UCzkCfa+pV35g2JBWTdChPHjD5/b2z3ntULlE56dnPNaofIJE7Y+YgCffRx2PZ88fdF1YraK63yifAz/70zofMKznXNeK6r5hLmdc14rqvmEYdu2LR5s2y4LOdQWcolYz6+5PvTtrXdNpovnMiluLF7Sm5StQKlUsn+9edm+tTSlCu8It5am7FKppI17KiVtGE6gYwCvd88OEq2G16wjm76qjSsFACzEoxSL+ZoFBDoGyCwnOH9uVCnEVQNO8uup73jznS8xPBsaa/WB2akxknNRmv1H6Amf4FBbN+D4GzrJ49NjvHT8ozL5bkAUdHIuysTXp2hpPUJP+KR7CwR5Q+NhOp4a2jVypwjRZ9757Se+jb67KUCQA4Sef3tXV68TAf/WgJO8ofGwa+8F/qsP6CBqwnSSg371cqu207gMURMmwOiHMeWgxYUJnu0+rp1k+eZlMAxM04c/EFKOkRfoRLA3grfriRVL7nwE+czkWXrCJ7QTm3t8tD/5Aj8nLzAf+4J9+w/waEOLa5yz/ZLJ+wdH8A4PtVpy++XsEVUChE8cfeU9DMPAHwjx12qGmclPySwnKoTIIpw9ond4qNWCzR5w9c9lV4MqCxApDb98iscPtJff+wMhHhQL3F76nhuLlyqECBFNBztdPzlXtan6dhW5ziecR+yP7DUufHPaFVfdO8pOqOvbZXKo7hNOx3NCd+/wqMjlu6LsE1u5pGw2Mrnzrug9c+YDq1rfnstec2VD3nsdRE3cu/s71e4d/wDle34ftaPAHgAAAABJRU5ErkJggg=='
width='32' height='32' />[](https://stackoverflow.com/users/587035/offcourse)

[offcourse](https://stackoverflow.com/users/587035/offcourse)offcourse

31633 silver badges1111 bronze badges

  * 2

...but only if the phone is rooted. –
[android.weasel](https://stackoverflow.com/users/444234/android-weasel "2,665
reputation") Oct 27 '12 at 17:41

  * Asus Transformer 301 - Working no root required – [Aiden Strydom](https://stackoverflow.com/users/929391/aiden-strydom "1,129 reputation") Jun 18 '13 at 16:28

add a comment  |

9

[](https://stackoverflow.com/posts/4733015/timeline "Timeline")

    
    
    adb tcpip 5555

Weird, but this only works for me if I have the USB cable connected, then I
can unplug the usb and go for it with everything else adb.

and the same when returning to usb,

    
    
    adb usb

will only work if usb is connected.

It doesn't matter if I issue the

    
    
    setprop service.adb.tcp.port 5555

or

    
    
    setprop service.adb.tcp.port -1

then stop & start adbd, I still need the usb cable in or it doesn't work.

So, if my ADB over usb wasn't working, I bet I wouldn't be able to enable ADB
over WiFi either.

[share](https://stackoverflow.com/a/4733015 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/4733015/edit)

answered Jan 19 '11 at 8:05

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAADGElEQVRYhb1Xz08TQRh9W/YAGIKtxsTYcIFAoUagEPUG/4By5WbwKB49cIIQoyQiB8MVETl47v4DpTe8IDGBbS1EKOwBDwps6bZJl44HM9uZ2Z1uf8V3253Z+b6Zfe993yiEEAIPHGRNaEkDr54Nce/fftzH4UnO6xMAwOrcOG50qJ7z795ux+vZYQQCijMe8Ar8/rOOpXUd+k/TFWBqMiwN7gV2/pOJMBccAFTxg3zxGvnitXTBaG83+nq6XKdw704Hnk6E0dne5jk/b5Xw8P4t13quBEYGghjuv4nvmQtoSUO6q5XNFBd4LBpCQFGk83P5kmv3AIA3a3tk7/CCeKFcLpOZ+W0yM79NdvTf3NiVVSJXVolcl8ue32aOL8nyxj63FjtG11MPT3JY2Uyhr6cLU5NhRHu7neQUZkda0sBoJOi8Y4nGgpJX5I+4Vs6yMRoJVn5BoWjDKtgghHCTKU7PLOymzxEbDHkGplha16uOH2RNJ7nd9DnUWv4hmzl7Co2A5ZWWNKCIPiDqfH3xccPBAOD5wlfuWfQJlw/Uq/Nm4WKSTOd+O/Ebl/mEJ5VZnTcLP46pNPOX0/0Ow6O93VidG29JAosvHngGTh1dIp4wKidQq87rhRg8kzURTxhIH/+TojIzv+2ogD0FEfmCzT13trdxcvQbpxC5wm2zms79TqTRE+NkeHpmwapSCVuBvp4ueQL/A6LPOOcm0ylFsz5AIfpMXbWgVWB9RpXpVNYT1gs/n1HF4LJ63ixkPuP6SbJ6LjqjyBW/cVk/UbN4W+EDXj6jin372sIjrnmsld0UtfYTtBYE/Pr2euHXT2SyJt590rG8kcLBSQ6qX99O4ecTFLJ+giJfsGEVK3VDpVnL+vZGfKJaPzEaCWFkIIhvqXNoW6eVnpDthjNZEznLxthgCGVCqvoElevsdD/GGIbT6vjhyw9Xu09RJqSiApaZ8YSBq4KNWCToCi7zCW3LQMxD59XuHQFFcRej1NEl0scmjF8WdvQ/rqxll1bZfAr23sHCpad4gu/bx6NyYorQkgZiQzxX/Dj0Fypu/9yG2Oo0AAAAAElFTkSuQmCC'
width='32' height='32' />[](https://stackoverflow.com/users/581103/chris)

[Chris](https://stackoverflow.com/users/581103/chris)Chris

9911 silver badge11 bronze badge

add a comment  |

8

[](https://stackoverflow.com/posts/11485355/timeline "Timeline")

To switch between TCP and USB modes with just one command, you can add this to
`/init.rc`:

    
    
    on property:service.adb.tcp.port=*
        restart adbd
    
    on property:service.adb.tcp.enable=1
        setprop service.adb.tcp.port 5555
    
    on property:service.adb.tcp.enable=0
        setprop service.adb.tcp.port -1

And now you can use property `service.adb.tcp.enable` to enable or disable
listening on port 5555. Run `netstat` to check whether it's listening. As you
can see it will also trigger if you do wish to change `service.adb.tcp.port`
manually.

[share](https://stackoverflow.com/a/11485355 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/11485355/edit)

[edited Jul 16 '12 at
21:48](https://stackoverflow.com/posts/11485355/revisions "show all edits to
this post")

answered Jul 14 '12 at 16:17

<img
src='data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAIAAgAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A7L4peNLmTxtqayS+aJL9ZYZPmfaogYKqhgCpDbTwO4P8Izyt344vwirHO5jZixikARWH8IKj5SBj3yVOSdozm6vqK6jrUlyd0aXE0jq8iDc7NJ8wYEfKflJ9gAOKbDpLBiYhvkUfKyZblRhRkfTHH8uvQ5cuh5qjzO51lt8T7nT8QtMtxMpJV8cNjtk849iCP9kHp3Hhv40zQM0blAyvtMiM6o8p5LlF5Kr/ALOOhOD0rxkWt1DD5saqEVwC+4YBPTP4gY+nSphHLbr+6jZTGPkIbe2RjOPywePXNReMtGW6bjqjB0S8nvryB5FDFjnytoALHLOx5ODyzADjJ9zjr5Jba0/dxtHzlm2tubAOCox0x05PfPRs1zWiWC2s1296rwWvzt5LkLGQNrc4yqoCHzgkgEn6cRo/xzuPFXxA0rRbC3X+ytSvI7I3dyuZDvcIJMdARnI9MAeuRpyNkkjqb/4Xatp/iqbWvD/iG5j1C2u0lvbC9uJD9tRpsOYU2ANGEb+8SNpHIwx7bUvLkj8iTchABJkXBIzz0znPXpiunT9k3RvDfjnxF4k8O+ILPUH1FJGtNOnO4xNvDOoO75sgMoPG3dn6cfpTi/hkuo3jaJn+eFUVXVQxXLLnchyGzxwcjqOeOhGcb852150p29mraH//2Q=='
width='32' height='32'
/>[](https://stackoverflow.com/users/717998/errordeveloper)

[errordeveloper](https://stackoverflow.com/users/717998/errordeveloper)errordeveloper

5,59666 gold badges3333 silver badges4848 bronze badges

add a comment  |

8

[](https://stackoverflow.com/posts/52834803/timeline "Timeline")

Bash util function:

    
    
    function adb-connect-to-wifi {
        ip="$(adb shell ip route | awk '{print $9}')"
        port=5555
        adb tcpip ${port}
        adb connect ${ip}:${port}
    }

[share](https://stackoverflow.com/a/52834803 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/52834803/edit)

answered Oct 16 '18 at 11:48

[](https://stackoverflow.com/users/798165/eleven)

[eleven](https://stackoverflow.com/users/798165/eleven)eleven

6,16222 gold badges2525 silver badges4141 bronze badges

add a comment  |

7

[](https://stackoverflow.com/posts/35931221/timeline "Timeline")

# STEP 1.

Make sure **both** your adb host computer and Android device are on the same
Wifi network.  
  

# STEP 2.

Connect the Android device with the computer using your USB cable. As soon as
you do that, your host computer will detect your device and adb will start
running in the USB mode on the computer. You can check the attached devices
with `adb devices` whereas ensure that adb is running in the USB mode by
executing `adb usb`.

    
    
    $ adb usb
    restarting in USB mode
    $ adb devices
    List of devices attached
    ZX1D63HX9R  device

  

# STEP 3.

Restart adb in tcpip mode with this command:

    
    
    $ adb tcpip 5556
    restarting in TCP mode port: 5556

  

# STEP 4.

Find out the IP address of the Android device. There are several ways to do
that:

  * **WAY: 1** Go to Settings -> About phone/tablet -> Status -> IP address.
  * **WAY: 2** Go to the list of Wi-fi networks available. The one to which you’re connected, tap on that and get to know your IP.
  * **WAY: 3** Try `$ adb shell netcfg`.

Now that you know the IP address of your device, connect your adb host to it.

    
    
    $ adb connect 192.168.0.102:5556
    already connected to 192.168.0.102:5556
    $ adb devices
    List of devices attached
    ZX1D63HX9R  device
    192.168.0.102:5556  device

  

# STEP 5.

Remove the USB cable and you should be connected to your device. If you don’t
see it in `adb devices` then just reconnect using the previous step’s command:

    
    
    $ adb connect 192.168.0.102:5556
    connected to 192.168.0.102:5556
    $ adb devices
    List of devices attached
    192.168.0.102:5556  device

Either you’re good to go now or you’ll need to kill your adb server by
executing `adb kill-server` and go through all the steps again once more.

Hope that helps!  
  
  
**Reference:**

  * <http://developer.android.com/tools/help/adb.html#wireless>
  * <http://codetheory.in/android-debug-bridge-adb-wireless-debugging-over-wi-fi/>

[share](https://stackoverflow.com/a/35931221 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/35931221/edit)

answered Mar 11 '16 at 2:34

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAAECklEQVRYhaWXXWxTZRjHf8XTZqXt1oiiQ5RhNyWtCKuKCDdmGwvBCy+8IMFuxrHEiKgxMVkyRYkGWPCO4NeFmG1l+HFjTAgxtoxPV3tBoR+k0ZUeFiPLbhzujE50Hi/WczynPR8bfa767/99n/c9532e/3n/juSpk3JjoJnVLY+gjUmxSOFyikIqRVuky5A/PRLl33/muTp2EYA1wRCeBr8Oh7d1YpT/xrUC46lLCA+0PMrR119l3VNP0xbpQnA6OT0SJXvhPD0HBjj5+afkkwnWbdpcxSPL7D36mbpge6Sb5fUNVViXX3ASPz5M7qcL9BwYQFgVCBDcvIWrYxfJJxPgcIAssyYYork1rO64JM0wJ0kILhelmRmQZQBWBQIEn9nK7M1pdXwVtsgvALS92KXuWkncHulWX2N7pFu3md2HDiPmssSjQyjzb/15U+WNsFn+ZQCC04nD4dCdkeByAeD2+qjzeqmMOo8Ht8+HMt9ZHm+GzfIvAxg9EUUu70wJ5enyyQSfvPEaQ+/v47dff2FSLDJy8EOO7HmF7PlzKPNj5fFm2Cy/MDUxQfrsGfVVCy4X8egQhcspxFxWnWBWA8p8WZYRc1mW++oNsZrf6SIWHVTzO8a+/06+Z/WDujMGEHNZruey5H9OVNWAwsejQ3j9fq6cGQUgsLG1Coe2bMUofzGTRsxmcAy+965s1ee7+vep/5395itKksT2nl6MwoiPfrDfVCceCoYQ8smEZZ9rk//w5RcqrtyEGa/tgEqd6Ih0L7QhmJ+xNvmmHc9R5/Fy7tuvdYtY8XY6Idj1uTb583vfVNtJWcTt9Vry23t6LXVCsOvzkiSVsVdN7i6Pn5uVNOPNeSudsK2Bg6d+XNITV/KwoAPS9DS7Dx2uwouqAeWslUUqF7fi7XTCtgYqNzE3K+kWt+O1KqjohhYLngY/x/r7AOPvuTaUs61c3Ir/61aJPUc+1unMzr5+blwrED8+jGDVp8oXC+5cB6pqTHMfQJbL9wGb73ktOqCErsak/2tMvQ+Y9WmtOmBUY70DH1HMpIkNDy5swKpPa9UBO50RwLpPK1tsqTrwzo5O6xqw69Om0GM16YBdDdz15P337p8UiwBMT03x+/jCrUfB4Y5tADS3hvn79m3ua2oy1AEzfjx1iRfeepvOl17m7sZG/CtXEu7o5OENG/ljchKHnS8optOW936312fpG1rCT9TmC9au32CpE8f6+yy/Jc/u3FW7L7DTiaozrvQNtfgChTfTicX6hqX7AqdeFwSXMV6sb1iyL4hFB9XfoyeixIaN8WJ9wx35gmImjafBr+qCEVbCzjeY+Q5LX1BMX2Fq4rp6z1+7/nHqV6zQ4fn5eTosfIOZLxBzWcRshv8A39/mhVY2U20AAAAASUVORK5CYII='
width='32' height='32' />[](https://stackoverflow.com/users/2893073/eddy)

[Eddy](https://stackoverflow.com/users/2893073/eddy)Eddy

2,3902828 silver badges3333 bronze badges

  * Additionally, you can get the IP of your device with this script on Unix: adb shell ip -f inet addr show wlan0 | grep inet | echo -n $(grep -Eo '[0-9\\.\/]') | echo -n $(grep -Eo '^[^\/]*') | sed 's/ //g' – [ahsan.dev](https://stackoverflow.com/users/1608317/ahsan-dev "651 reputation") Apr 13 '16 at 15:11

  * @Eddy One doubt that both system and mobile/Tablet must connected via WiFi or else system connected through LAN and tablet connected using of WIFi router of same network. Please Clarify it – [iSrinivasan27](https://stackoverflow.com/users/4499697/isrinivasan27 "1,046 reputation") Apr 25 '16 at 12:36

  * @i-Droid I don't know why both have to connect in the same network. maybe ADB use special net routing protocol. I have no idea and no deep research about it. If you have interest in it, welcome to clarify it and share it with me, thanks! – [Eddy](https://stackoverflow.com/users/2893073/eddy "2,390 reputation") Apr 26 '16 at 2:33

add a comment  |

5

[](https://stackoverflow.com/posts/5035073/timeline "Timeline")

You can also use SSH local port forwarding. But it still involves a USB cable.
Connect your phone using USB to a computer (host) with an sshd running. On a
remote (guest) pc start an SSH client capable of portforwarding/tunneling.
Example:

    
    
    plink -L 5037:localhost:5037 <host_IP_address>

I use this construction to connect my device to a virtual machine. Eltima USB
to Ethernet wasn't stable enough (timeouts during debug).

SSH tunneling works for free and is more reliable.

[share](https://stackoverflow.com/a/5035073 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/5035073/edit)

[edited Mar 16 '14 at 11:09](https://stackoverflow.com/posts/5035073/revisions
"show all edits to this post")

[](https://stackoverflow.com/users/63550/peter-mortensen)

[Peter Mortensen](https://stackoverflow.com/users/63550/peter-mortensen)

25.2k2121 gold badges9090 silver badges118118 bronze badges

answered Feb 17 '11 at 21:45

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAADf0lEQVRYha1Wz08TQRT+djsttrRAAeWnxbaIFIgSL020ifGAB+BgPPkHcFHDyT+CRM4eNJ49+QMOrQkkGBMxelCpFtqCDdBSILYg26RoNKYecJbd2Z3ZEnjJJn3ztvO998373qz06N1SJb61C2qX2hqh9Yd6OjC7nFf9ydEwXA6CamwmvYEbFzpNYxt7ZcSSWcjDobO6AOvfHDiHoZ6OqgBZ8OnFdcN6Xinj8fskJuYWEN/aBelscOuqZn2aBAAdE0cFzytlxJI5LGzu6NYJcFC1FpD1tUkcFXxTKSOWyuFzfsf0fQIYqzZjgSYxlVjTMfHw1lUd+OXOZkT8reqay0EwFu41ANMeULupGhZoEoDxOGjlEX+rsEnzShnRZBbxzd1DBrRV83xREryGY4G5PUDNShFmSViBW/WA9PLrakWk8/nVbXQ2uNHldRs2ThcUOGyyMH69u52b3Ex6A8RKYl1eNybm4hho9WI45INdltSKxiP9cDuIMC4Cn15cPzgCURJaRSS2f6jrgSYPes80AIBlnAcOADJdFE08s14YCfmqjvPAAaYJeTonsgwJQEXzrl1Wc7eMa8HZOWF4y4yJV6mcbnMAiCazVccp+PTiOlx2Apfj8DGdGNqe2C7t4+NGEYEmD0ZCPthlGdFkFumCgkyxhFoHEcaDzXVCqUqVSoVNXrWpxBq8zhq0eJyGhsoUS8jslFBDbMI4AB04K3MDA/dezKu/I/4WnK49BafdSJTTboPdJoPIkjCu/Pqtuy9Y4w7tiL8FtweDyCvlY82BZ19WAfBvU9MEKLgkSScyB6iqzJIwqEALTu0k5sDsch5TiTXDe4Q9cxYcsNa5KD45GtbtNZVY0zGh7sIDB443B7SadzmIgQliBX4Sc4A1bU9ITz+tVHjgAPAms3WsOcB+lmuPfKinA9Ld529NBxGtiN2Y7RmnnQg/WFkWNpUy2utrVd+ggkCTB+ORfty/dpF7nVLw24NBbndTY++EWCqn89U5wKtYBE6PTaTzdEHBt6KC7uZ6AEDq+56OFbnainng1ERMRJM5xj9khWyV9vHkQ8rwp2BTHYZDPjx4HReCW+kcAJYLClaKCs7/Z0GrEPnnn7/QPm11LoyFe3HnSp/uQ5NXuZXO1aqXzFmoqgdEc8LMzHpipahgpaCoPmWBBBo9GOnjN99RwdkktMYqIprM4h+5FU1grsnIGAAAAABJRU5ErkJggg=='
width='32' height='32' />[](https://stackoverflow.com/users/622188/ron)

[Ron](https://stackoverflow.com/users/622188/ron)Ron

5111 silver badge11 bronze badge

add a comment  |

4

[](https://stackoverflow.com/posts/11518911/timeline "Timeline")

I find the other answers confusing. Far simpler to use adbWireless:

<http://ppareit.github.com/AdbConnect/>

Simply install an app on your phone to toggle debugging over wifi, install an
eclipse plug-in and you're done.

[share](https://stackoverflow.com/a/11518911 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/11518911/edit)

[edited Jul 17 '12 at
21:27](https://stackoverflow.com/posts/11518911/revisions "show all edits to
this post")

answered Jul 17 '12 at 8:41

user146043user146043

  * What eclipse plug-in are you referring to? Edit: Nevermind. Found it by following the link in your answer. – [ArtOfWarfare](https://stackoverflow.com/users/901641/artofwarfare "15,783 reputation") Oct 5 '12 at 15:13

  * This is only root though – [Zoe](https://stackoverflow.com/users/6296561/zoe "19,692 reputation") Aug 18 '17 at 10:19

add a comment  |

3

[](https://stackoverflow.com/posts/14172202/timeline "Timeline")

I put together a batch file for automatic enabling and connecting ADB via TCP,
to a device connected via USB. With it you don't have to put in the IP
manually.

    
    
    @echo off
    setlocal
    
    REM Use a default env variable to find adb if possible
    if NOT "%AndroidSDK%" == "" set PATH=%PATH%;%AndroidSDK%\platform-tools
    
    REM If off is first parameter then we turn off the tcp connection.
    if "%1%" == "off" goto off
    
    REM Set vars
    set port=%1
    set int=%2
    if "%port%" == "" set port=5557
    if "%int%" == "" set int=wlan0
    
    REM Enable TCP
    adb -d wait-for-device tcpip %port%
    
    REM Get IP Address from device
    set shellCmd="ip addr show %int% | grep 'inet [0-9]{1,3}(\.[0-9]{1,3}){3}' -oE | grep '[0-9]{1,3}(\.[0-9]{1,3}){3}' -oE"
    for /f %%i in ('adb wait-for-device shell %shellCmd%') do set IP=%%i
    
    REM Connect ADB to device
    adb connect %IP%:%port%
    
    goto end
    
    :fail
    echo adbWifi [port] [interface]
    echo adbWifi off
    goto end
    
    :off
    adb wait-for-device usb
    
    :end

[share](https://stackoverflow.com/a/14172202 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/14172202/edit)

answered Jan 5 '13 at 13:25

<img
src='data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAIAAgAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8Ap/8ABbbwwf8AhJPhXra2/wC7ngvbOWcFjyrxMqnsPvsRjnls9q5b9lHwZaeFtO0zUp7GD/TI0RJWjz8xGRg46819Q/8ABVzw6fE/7Mdxq72SyXvhnxHbNHNGM+XDKBGSc8c+bH7ZAr45/YZj134s+IfEvhi21I/Y9AsEvrJ/LAPnEldpHTaS34YHpXDjE5U9Gezl0oxnqj9Q/CuiaWfDUNu+mW7o6ZYPEDknGc5+n6V8UeBrKy8HfHiOxtLQxxJrjwQbw37s+aAiKQCcckcgj5Bx6ez/ALPsHxVXULyXxL4hKwrIqHSrqzRURfmyUkU8/wAPbnnpXe+Ffg1a658cNV8VILeSzeeAtbPECySxqGaVT2JYKOPRvXjzKb/eKN7ndXjzJuWiOq+Ltp4f+NPwh+KHhRdQt2t9b02dba6mykKSC3ASTewAASSINnOOM1+Tn/BPL4yS/CjxZ4jjg0ZNSbVFt7aSRpsMg3n5to+8o578Zr750v4aaT8Xfhfqmka5Hqif2vD5V00WstZXNxDx+8RCSqI/dDgHowOTX5xS6ToH7Kf7ROqeGYvFerzaZaSxO04tWs7qEk58qQMMEqCDvTKOCCDg4Hoqr7aDTWpxQpLD1E76fI/TPwv8Qryz/tKC7kml2yiWMXkWySNHOcZ4DAdiOoyDgjn3D4E/Ezwp4wh1fQtK1K3l8SaFcGHVtPI2T27OA6kqeShVkwwyM8ZyCK+SvDWtL44v9M1UXktzZyxI8KyOHkk7ruIOAB+Zyegr5j/am+Kp0H9qKwvfA2pzaJr2m6Utvdarp0mySS6SRmZSR97CSBCDnO0qeBiuTBxtWbt0N8e+akm+/wB5/9k='
width='32' height='32' />[](https://stackoverflow.com/users/660198/felizk)

[Felizk](https://stackoverflow.com/users/660198/felizk)Felizk

3111 bronze badge

add a comment  |

3

[](https://stackoverflow.com/posts/26841437/timeline "Timeline")

Here's an extension to Brian's answer using Bluetooth:

  1. On Linux, use Blueman to share PC internet with your device via Bluetooth:
    
        $ sudo apt-get install blueman
    $ blueman-manager
    Pair them: Search devices after enabling Bluetooth
    on your phone and making it visible
    $ blueman-services
    Network > [X] Network Access Point (NAP)
    Your Phone > Settings > Bluetooth > Paired Device > [X] Internet access

  2. Use the Bluetooth network for ADB commands:
    
        $ adb tcpip 5555
    $ adb connect $(adb shell ip -f inet addr show bt-pan | egrep -o '[0-9]+\.[0-9]+\.[0-9]+\.[0-9]+' | head -n1):5555

Once done to return to USB mode:

    
    
    $ adb disconnect
    $ adb usb

Note: [Bluetooth 3.0 and 4.0 can go up to 24
Mbit/s](http://en.wikipedia.org/wiki/Bluetooth).

[share](https://stackoverflow.com/a/26841437 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/26841437/edit)

[edited Nov 10 '14 at
12:20](https://stackoverflow.com/posts/26841437/revisions "show all edits to
this post")

answered Nov 10 '14 at 10:19

<img
src='data:image/png;base64,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'
width='32' height='32' />[](https://stackoverflow.com/users/167897/wernight)

[Wernight](https://stackoverflow.com/users/167897/wernight)Wernight

28.6k2121 gold badges104104 silver badges125125 bronze badges

add a comment  |

3

[](https://stackoverflow.com/posts/27789274/timeline "Timeline")

**Steps :**

  1. `su` \-- To switch to super user.
  2. `setprop service.adb.tcp.port 5555` \- To specify the tcp Port - 5555 is the port number here
  3. `stop adbd` \- To stop the adbd service.
  4. `start adbd` \- To start adbd service.

this works perfectly with `ssh` from my windows PC

I try to do this on the boot on my cyanogen mobile or launch this with plink.
With plink I can't launch shell with su right ... sudo or su command not
works. On boot I don't know how it's works! My shell program works from ssh
with `su -c "sh /storage/sdcard1/start_adb.sh"` with the last 3 commands
(without su --)

Thanks

[share](https://stackoverflow.com/a/27789274 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/27789274/edit)

[edited Jun 3 '15 at 9:00](https://stackoverflow.com/posts/27789274/revisions
"show all edits to this post")

[](https://stackoverflow.com/users/1825820/venkatvb)

[venkatvb](https://stackoverflow.com/users/1825820/venkatvb)

65511 gold badge99 silver badges2222 bronze badges

answered Jan 5 '15 at 22:50

[](https://stackoverflow.com/users/4421879/beguinner)

[beguinner](https://stackoverflow.com/users/4421879/beguinner)beguinner

3122 bronze badges

add a comment  |

2

[](https://stackoverflow.com/posts/36331439/timeline "Timeline")

One additional note (learned the hard way): You should not have your company
VPN-connection active at the same time...

[share](https://stackoverflow.com/a/36331439 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/36331439/edit)

answered Mar 31 '16 at 10:57

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAAAx0lEQVRYhWP8////f4YBBEwDaTkDAwMDCzJn6o/bDB///Wao4tLCUCjzfhMK/wq/B4MAExvR8rjMZ0GWbP9+HS6BzRGUAFzmw6Pg47/fcMlP/38z/KNy0sBlPjwEYC769P83QxuXHgMTIyNVHYDLfEb0XPDv/3+sln/49wuFz8fIiqKOkDwu8zEcQG8w4NlwwB0AT4TE5GNKAC7zBzwERh0Az4bE5mNyAS7zR8uBAXfAaDkw6oDRcmDAo2DAHTDaLxjtF4z2CwAH+8KI89pT/QAAAABJRU5ErkJggg=='
width='32' height='32' />[](https://stackoverflow.com/users/842549/tuomasg)

[TuomasG](https://stackoverflow.com/users/842549/tuomasg)TuomasG

5344 bronze badges

add a comment  |

2

[](https://stackoverflow.com/posts/37451669/timeline "Timeline")

You Need to do following things:

  * First, Add ADB to your environment path.
  * From your CLI type this command **adb connect YOUR_DEVICE_IP:PORT_NUMBER** (example **adb connect 192.168.100.100:5555** )

[share](https://stackoverflow.com/a/37451669 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/37451669/edit)

answered May 26 '16 at 4:31

[](https://stackoverflow.com/users/3502024/noman404)

[noman404](https://stackoverflow.com/users/3502024/noman404)noman404

81688 silver badges2121 bronze badges

add a comment  |

2

[](https://stackoverflow.com/posts/58334911/timeline "Timeline")

There are two ways to connect your Android device with ADB over TCP?

## First way

Follow this steps

> First use below command to get your device IP Address
    
    
    adb shell ifconfig

OUTPUT of above command

    
    
    wlan0     Link encap:UNSPEC    Driver icnss
              inet addr:XXX.XXX.X.XX  Bcast:XXX.XXX.X.XXX

With the help you above command you will find the IP Address of connected
device

> Now use below command
    
    
    adb tcpip 5555

The above command will restart this TCP port: 5555

> Now use below command to connect your device
    
    
    adb connect XXX.XXX.X.XXX:5555
                ^^^ ^^^ ^ ^^^
            IP Address of device

## Second way

You can use Android Studio Plugin `Android device with ADB`

[**Android WiFi ADB - IntelliJ/Android Studio Plugin**](https://android-
arsenal.com/details/1/2654)

> IntelliJ and Android Studio plugin created to quickly connect your Android
> device over WiFi to install, run and debug your applications without a USB
> connected. Press one button and forget about your USB cable

Please check this article for more information

[Connect Android Device with Wifi within Android
Studio](https://android.jlelse.eu/connect-android-device-with-wifi-within-
android-studio-3b1bc00c1e17)

[share](https://stackoverflow.com/a/58334911 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/58334911/edit)

answered Oct 11 '19 at 5:44

[](https://stackoverflow.com/users/7666442/nilesh-rathod)

[Nilesh Rathod](https://stackoverflow.com/users/7666442/nilesh-rathod)Nilesh
Rathod

45.5k1212 gold badges6969 silver badges9191 bronze badges

add a comment  |

2

[](https://stackoverflow.com/posts/59661180/timeline "Timeline")

I'm struct at the same issue but a simple hack `adb reverse tcp:<PORT>
tcp:<PORT>` worked for me. It allows the system to accept tcp requests.

Thank You for reading

[share](https://stackoverflow.com/a/59661180 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/59661180/edit)

answered Jan 9 at 9:47

[](https://stackoverflow.com/users/12668430/radha-manohar)

[Radha Manohar](https://stackoverflow.com/users/12668430/radha-manohar)Radha
Manohar

3131313 bronze badges

add a comment  |

2

[](https://stackoverflow.com/posts/60239377/timeline "Timeline")

These are the steps I followed and it worked for me,

>   1. adb shell ifconfig (get the ip address of the device from here)
>
>   2. adb tcpip 7777 (connect adb to some port)
>
>   3. adb connect "ipaddress":7777
>
>

[share](https://stackoverflow.com/a/60239377 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/60239377/edit)

answered Feb 15 at 13:51

[](https://stackoverflow.com/users/6680585/tom-taylor)

[Tom Taylor](https://stackoverflow.com/users/6680585/tom-taylor)Tom Taylor

1,5772020 silver badges4040 bronze badges

add a comment  |

1

[](https://stackoverflow.com/posts/6793974/timeline "Timeline")

Use the adbwireless app to enable the phone, then use adb connect from the
Windows machine to talk to it. The adbwireless app on the phone tells you how
to connect to it, giving the IP address and everything.

The much less fun alternative is to connect via USB, tell the phone to use
TCPIP via adb tcpip 5555, then disconnect USB, then use adb connect. This is
much harder because this way you have to figure out the IP address of the
phone yourself (adbwireless tells you the IP), you have to connect via USB,
and you have to run adb tcpip (adbwireless takes care of that too).

So: install adbwireless on your phone. Use it. It is possible, I do it
routinely on Linux and on Windows.

[share](https://stackoverflow.com/a/6793974 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/6793974/edit)

answered Jul 22 '11 at 17:45

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAADH0lEQVRYha1XX0hTURz+plemU0dWT20lSBuVD8UWG92hBFEvWrjBhj2nT3MvGgoZ4XMP0ssKEiXDHsqHFUkPaSUIWwMnFmR4/YPosMJGUBD0dHtY53p37jnnXre+p7v9zr2/75zz+77fObaHL9+rvZ1B8JBT8vB73QCAjd0Crt56BFVVueMJfB4X4mEZN+5Oc8f0dAQgjU4vAAB4JJKpNCaGYgCABy8ypslJYrm1WTiupyOAgVg7JAAQkcisbCOn5HGooQ6vsqvCjwKAs94Op8NuKTmAIgEzEslUGoedDktLP7+8ifnlTVw814J4lyxMXkJARCKzsl3y2+dxoamxDm+W1jE13I1kKm0YQ4iIkgNAFc1wdHoBYzNZ/hQBxMOyNju/142JoRimhrtx4cwJ7jus5AC1AnoSAHs7fB6XVmCXfCe1/xsddjjraw+UnEtAT4JGPLy/r/EuGUp+D/efZ/B6UQGrRETJAcC2uLqjlqPzShE4dRyJSAjSQXVeKfxeFxKREIKni/VSRXS+sVsw1XlPRwD90bay4wDgdNSiUecT1UfPXhn5UviJT1vfoOS/Cz8+EGuH3+uGvabaIDuzOMHW1x949u4jlJ09tBw7UixCkc73mdt1z8Zq58V5PjGbW8Pc0hpbBfGwjKaGUgJEFU5HLUYmZw3v8OLEJ3JK3kBEVRkypHXOIsGDKM7zCQMBWud6AuXAzCcMBEj/Jm21Uvz6/Qf3+q4BYPsMcwus9HOrMPMZQzMS9fNyfMDMZwwrwOvntKfTBSeKi84TktV+Xq4PAGKfsan/aLF0SqM/2sb1AStxgvHBKJoa6hC583h/C0T9nKASHyCgfUYy0+n/Bu0z2haw8PTtB+5yErnaa6qF94b+aJtwZQwyNEvu87gwPhjFk9vXIbc2I5lKazGWzns7g0LpMpuRaOa0T1i5N5CzJWslDAREyQG2T1i5N/BIlNQAKznPJ0Twe4s6n8ut4/PkzZLY2Ey2hIRWA7yZWz3365GIhIoVzojRNSGJkuthxSeA4mmXHDgvn/cwx+i3QzJLflCfSERC2jPrbkiT+AtmBuOTT8e/IwAAAABJRU5ErkJggg=='
width='32' height='32'
/>[](https://stackoverflow.com/users/858427/concernedparty)

[ConcernedParty](https://stackoverflow.com/users/858427/concernedparty)ConcernedParty

1111 bronze badge

add a comment  |

1

[](https://stackoverflow.com/posts/8607842/timeline "Timeline")

On my system it went like this:

On my Android device in my Linux shell, a simple "ifconfig" did not give me my
IP address. I had to type:

ifconfig eth0

-or-

netcfg

to get my IP address. (I knew eth0 was configured because I saw it in my
dmesg.) Then I did the :

setprop service.adb.tcp.port -1

stop adbd

start adbd

Then on my Win7 box (the one running Eclipse 3.7.1). I opened a command prompt
to

\android-sdk\platform-tools>

without running as admin. Then I did a

adb connect 12.345.678.90

I never put a port. If I did a

adb tcpip 5555

it said it couldn't find the device then nothing appeared in my "adb devices"
list. I.e. it only works if I DON'T do the tcpip command above.

I can do an "adb shell" and mess with my Android Device. But my Android Device
does not appear in my Run->Run Configurations->Target tab right now. On the
other hand, if I keep the Target Tab set to automatic. Then when I run my app
via Run->Run it does run on my Android device even though my Android device is
not even listed as one of my targets.

[share](https://stackoverflow.com/a/8607842 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/8607842/edit)

[edited Dec 23 '11 at 20:02](https://stackoverflow.com/posts/8607842/revisions
"show all edits to this post")

answered Dec 22 '11 at 17:44

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAACKElEQVRYhe1Xu04CQRQ9w5JAIWuMRiOxFWNtpVb6E9pqItHGSKRFFhtNVLCwQaOtfIOVVloJhV9gfICaGAlIKNixMLOywzxWV604yRa7Zzj3zt177jIkX87S+FACXnBYyaHaekUyuumZHyuZUr2lwTUE9x7TAABdEoeVHNhaAB1J6HhR8GR0E0b/csi6rJ0jRMKY6Jn0FPy6foWm3cBUZEbLH5S3pMEBIMgeyirBizMcPe0DAEyjT8mrgrsSkCVRbb0KhT65Nykn4vngAD5fQfsD/nVMRWbQtBu4rl+5fjjXv4DMSA7T5qySP6hsS4MDAGLFCBVd+XKWtmPnPuVwqdtVatstT3ysGKE79ykqQ0cFdJUYDY8jM5IDIQHXehnftBtKRxBKKWU3Op/7hVCflSJfzjolVJXsp5Dpgyf/IgmVvhFd6bVEPuaHjZ+yq/QDfnzuBTp942zvwlL5mBDiKwHdHHGaUOdzv5DpO6OYWaPaehP63C9k+q5vgWn0AcCvB1fqi6zSnQNAdw5058D/zQHX/wEehZcTzA8sOvc/ORfImtCBrGSnz8c0VjSFVhJZVMWLbMguYZ0LLydI3yUAUOEujp72sfuwId0lz8eHElgfzggLYFiWZamCh0hY6eOb95KSZ3NkomcSIRLGZe3ctc71LeCDA797LmDnjfaEnQREwYGv7uVPOl9zIqDkeXQk0d5woibR+dgrL2vaoGznPHRz4rtzhFXiAx4WVALXWfgQAAAAAElFTkSuQmCC'
width='32' height='32' />[](https://stackoverflow.com/users/883354/joe-c)

[Joe C](https://stackoverflow.com/users/883354/joe-c)Joe C

2,22733 gold badges2222 silver badges2929 bronze badges

add a comment  |

1

[](https://stackoverflow.com/posts/6315171/timeline "Timeline")

I did get this working. Didn't use any usb cable.

  * app adb wireless. 
  * Run it. That will set ip and port; Then in dos
    
        cd C:\Program Files\Android\android-sdk\platform-tools adb connect "192.168.2.22:8000 "enter"

Connected.

[share](https://stackoverflow.com/a/6315171 "short permalink to this answer")

Share a link to this answer

Copy link

|[improve this answer](https://stackoverflow.com/posts/6315171/edit)

[edited Nov 19 '12 at 23:18](https://stackoverflow.com/posts/6315171/revisions
"show all edits to this post")

[](https://stackoverflow.com/users/967100/bruno-vieira)

[Bruno Vieira](https://stackoverflow.com/users/967100/bruno-vieira)

3,62611 gold badge1919 silver badges3535 bronze badges

answered Jun 11 '11 at 9:31

<img
src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAAA7EAAAOxAGVKw4bAAAC70lEQVRYhb1XPW8TQRB9s3eWqAgUiZw4H0hxEaHYYBBU6SIhEVOkoKGnocnPQBRUNDQpoU9zQXKBhJQCQZHgI1GEsEBO4hBHihJFQgq+vaG47Nnnu9s7f8Dr9mb23uxo580sXbx5xogAjUzAKCwBRgbStsAn9Wi7EBBTt6N+AbdZg3tgw92pBPbxWcNfm3HENF0CEXnfcvPgg6+QtgVIJ2BvWc9Bk7d8305I20JmcQUO4AdhFJbgbKyGA4gi9m1EoMkCKDfvrxX4dB+8/wXUlQW3WQP/2vVISst+EJSdA43Ogo9rnk1HHMpOjF1W10NZkLYV8FFBeFkow3n/yvvOZw0/JSK/AOP+k8RAusGuA4ABdOyTrZCfWVoGM0OMt7MglLFfcu9ED0Ekur6VI33V/5XdTEvuNmuXl7AFo1CGGJ/zDFezEDN3Q/7qlHFQdmp9fMs6ckWsLpR/ktFZGIUy+OIcxo170XsPd9uBxthJ7lVZV+di5k7sD9LA3dvS6oQpLssrrs4HRVSF+Dbb8u6Ars4HRZJOBK4uEQ2VXEFW18EcVHylEyJqw7DR1onOCFr/LwCdTvi9ILbOB0WCTpA8+s66Oh80EPnzs1YnTFycI7O4Eu3QrA1EDgBkXkHr3YuwzlzLwSiWYSbVqYgJLi0idaa4BJrydMZM088HhU5nBKCv02EiSmcEoK/Tfw0B9NbPhw2z337eKwI6UyxDZL3yJufHJ+63n/dCHNKZsTyM4iOQrG9yXL8Gkvs5/vzWvht084TcrsCUVStWB4Dkfp5ZXOlrnpDbFcitNZh8egDe2wJNlyId0+hEr/OEIgeUDthhHQhsSKkTaeaJTnI/AJUFAHA210KbhqkTIr+AzOOXMBeegkYm2vOAtC0wM9ydSiiISJ0o9qcTfFKH8+E1nI1V8FmjPQ/waQNc3wTgveEceC+ZWJ3IzoHG8v46aZ5wD3e9Qx4HOyx1Ps+7n87i5gPQ9Vx8Pz/6BpChfTcAiCRW+AtX+sdTbYqfsgAAAABJRU5ErkJggg=='
width='32' height='32' />[](https://stackoverflow.com/users/793836/lee)

[lee](https://stackoverflow.com/users/793836/lee)lee

2111 bronze badge

add a comment  |

1

[2](https://stackoverflow.com/questions/2604727/how-can-i-connect-to-android-
with-adb-over-tcp?page=2&tab=votes#tab-top "Go to page 2") [
Next](https://stackoverflow.com/questions/2604727/how-can-i-connect-to-
android-with-adb-over-tcp?page=2&tab=votes#tab-top "Go to page 2")

**[Highly active question](https://stackoverflow.com/help/privileges/protect-
questions)**. Earn 10 reputation in order to answer this question. The
reputation requirement helps protect this question from spam and non-answer
activity.

##  Not the answer you're looking for? Browse other questions tagged
[android](https://stackoverflow.com/questions/tagged/android "show questions
tagged 'android'")
[networking](https://stackoverflow.com/questions/tagged/networking "show
questions tagged 'networking'")
[tcp](https://stackoverflow.com/questions/tagged/tcp "show questions tagged
'tcp'") [debugging](https://stackoverflow.com/questions/tagged/debugging "show
questions tagged 'debugging'")
[adb](https://stackoverflow.com/questions/tagged/adb "show questions tagged
'adb'") or [ask your own question](https://stackoverflow.com/questions/ask).

The Overflow Blog

  * [ ](https://stackoverflow.blog/2020/03/19/coming-together-as-a-community-to-connect/?cb=1)

[Coming together as a community to
connect](https://stackoverflow.blog/2020/03/19/coming-together-as-a-community-
to-connect/?cb=1)

  * [ ](https://stackoverflow.blog/2020/03/23/defending-yourself-against-coronavirus-scams/?cb=1)

[Defending yourself against coronavirus
scams](https://stackoverflow.blog/2020/03/23/defending-yourself-against-
coronavirus-scams/?cb=1)

Featured on Meta

  * [ ](https://meta.stackexchange.com/questions/344187/planned-maintenance-scheduled-for-saturday-march-28-2020-at-1300-utc-9am-us?cb=1)

[Planned maintenance scheduled for Saturday, March 28, 2020 at 13:00 UTC
(9AM…](https://meta.stackexchange.com/questions/344187/planned-maintenance-
scheduled-for-saturday-march-28-2020-at-1300-utc-9am-us?cb=1 "Planned
maintenance scheduled for Saturday, March 28, 2020 at 13:00 UTC \(9AM
US/Eastern\)")

  * [ ](https://meta.stackexchange.com/questions/344491/an-update-on-creative-commons-licensing?cb=1)

[An Update On Creative Commons
Licensing](https://meta.stackexchange.com/questions/344491/an-update-on-
creative-commons-licensing?cb=1)

  * [ ](https://meta.stackexchange.com/questions/345032/community-and-moderator-guidelines-for-escalating-issues-via-new-response-proces?cb=1)

[Community and Moderator guidelines for escalating issues via new
response…](https://meta.stackexchange.com/questions/345032/community-and-
moderator-guidelines-for-escalating-issues-via-new-response-proces?cb=1
"Community and Moderator guidelines for escalating issues via new response
process \(March-April 2020\)")

  * [ ](https://meta.stackoverflow.com/questions/295650/how-does-the-triage-queue-work?cb=1)

[How does the Triage queue
work?](https://meta.stackoverflow.com/questions/295650/how-does-the-triage-
queue-work?cb=1)

  * [ ](https://meta.stackoverflow.com/questions/394498/triage-needs-to-be-fixed-urgently-and-users-need-to-be-notified-upon-receiving?cb=1)

[Triage needs to be fixed urgently, and users need to be notified
upon…](https://meta.stackoverflow.com/questions/394498/triage-needs-to-be-
fixed-urgently-and-users-need-to-be-notified-upon-receiving?cb=1 "Triage needs
to be fixed urgently, and users need to be notified upon receiving a review
ban!")

#### Linked

[ 68 ](https://stackoverflow.com/q/31327839?lq=1 "Vote score \(upvotes -
downvotes\)") [Adb over wireless without usb cable at all for not rooted
phones](https://stackoverflow.com/questions/31327839/adb-over-wireless-
without-usb-cable-at-all-for-not-rooted-phones?noredirect=1&lq=1)

[ 5 ](https://stackoverflow.com/q/51922573?lq=1 "Vote score \(upvotes -
downvotes\)") [Android adb: No connection could be made because the target
machine actively refused
it](https://stackoverflow.com/questions/51922573/android-adb-no-connection-
could-be-made-because-the-target-machine-actively-ref?noredirect=1&lq=1)

[ 3 ](https://stackoverflow.com/q/48519847?lq=1 "Vote score \(upvotes -
downvotes\)") [Is it possible to debug over wifi without using any usb cable
in android studio?](https://stackoverflow.com/questions/48519847/is-it-
possible-to-debug-over-wifi-without-using-any-usb-cable-in-android-
studio?noredirect=1&lq=1)

[ 2 ](https://stackoverflow.com/q/52749958?lq=1 "Vote score \(upvotes -
downvotes\)") [Android Studio – Running and Debugging Builds over Wi-Fi on Mac
OS](https://stackoverflow.com/questions/52749958/android-studio-running-and-
debugging-builds-over-wi-fi-on-mac-os?noredirect=1&lq=1)

[ 3 ](https://stackoverflow.com/q/47302478?lq=1 "Vote score \(upvotes -
downvotes\)") [How to do “adb logcat” via Wifi without connecting the device
to the computer first?](https://stackoverflow.com/questions/47302478/how-to-
do-adb-logcat-via-wifi-without-connecting-the-device-to-the-computer-
fi?noredirect=1&lq=1)

[ -1 ](https://stackoverflow.com/q/55193202?lq=1 "Vote score \(upvotes -
downvotes\)") [Is there any way to use physical device for testing server
sided apps? [Android]](https://stackoverflow.com/questions/55193202/is-there-
any-way-to-use-physical-device-for-testing-server-sided-apps-
android?noredirect=1&lq=1)

[ 972 ](https://stackoverflow.com/q/4893953?lq=1 "Vote score \(upvotes -
downvotes\)") [Run/install/debug Android applications over Wi-
Fi?](https://stackoverflow.com/questions/4893953/run-install-debug-android-
applications-over-wi-fi?noredirect=1&lq=1)

[ 168 ](https://stackoverflow.com/q/3912548?lq=1 "Vote score \(upvotes -
downvotes\)") [Android adb “Unable to open sync
connection!”](https://stackoverflow.com/questions/3912548/android-adb-unable-
to-open-sync-connection?noredirect=1&lq=1)

[ 85 ](https://stackoverflow.com/q/33726622?lq=1 "Vote score \(upvotes -
downvotes\)") [How to debug in Android Studio using adb over
WiFi](https://stackoverflow.com/questions/33726622/how-to-debug-in-android-
studio-using-adb-over-wifi?noredirect=1&lq=1)

[ 32 ](https://stackoverflow.com/q/42364380?lq=1 "Vote score \(upvotes -
downvotes\)") [How can I use adb over
WiFi?](https://stackoverflow.com/questions/42364380/how-can-i-use-adb-over-
wifi?noredirect=1&lq=1)

[see more linked
questions…](https://stackoverflow.com/questions/linked/2604727?lq=1)

#### Related

[2178](https://stackoverflow.com/q/48198?rq=1 "Vote score \(upvotes -
downvotes\)")[How can you find out which process is listening on a port on
Windows?](https://stackoverflow.com/questions/48198/how-can-you-find-out-
which-process-is-listening-on-a-port-on-windows?rq=1)

[2588](https://stackoverflow.com/q/151777?rq=1 "Vote score \(upvotes -
downvotes\)")[How to save an activity state using save instance
state?](https://stackoverflow.com/questions/151777/how-to-save-an-activity-
state-using-save-instance-state?rq=1)

[1829](https://stackoverflow.com/q/1016896?rq=1 "Vote score \(upvotes -
downvotes\)")[How to get screen dimensions as pixels in
Android](https://stackoverflow.com/questions/1016896/how-to-get-screen-
dimensions-as-pixels-in-android?rq=1)

[3747](https://stackoverflow.com/q/1109022?rq=1 "Vote score \(upvotes -
downvotes\)")[Close/hide android soft
keyboard](https://stackoverflow.com/questions/1109022/close-hide-android-soft-
keyboard?rq=1)

[461](https://stackoverflow.com/q/4567904?rq=1 "Vote score \(upvotes -
downvotes\)")[How to start an application using android ADB
tools?](https://stackoverflow.com/questions/4567904/how-to-start-an-
application-using-android-adb-tools?rq=1)

[972](https://stackoverflow.com/q/4893953?rq=1 "Vote score \(upvotes -
downvotes\)")[Run/install/debug Android applications over Wi-
Fi?](https://stackoverflow.com/questions/4893953/run-install-debug-android-
applications-over-wi-fi?rq=1)

[9](https://stackoverflow.com/q/15860274?rq=1 "Vote score \(upvotes -
downvotes\)")[Unable to connect Android ADB over
TCP/IP](https://stackoverflow.com/questions/15860274/unable-to-connect-
android-adb-over-tcp-ip?rq=1)

[74](https://stackoverflow.com/q/30964854?rq=1 "Vote score \(upvotes -
downvotes\)")[Android Studio - Device is connected but
'offline'](https://stackoverflow.com/questions/30964854/android-studio-device-
is-connected-but-offline?rq=1)

[10](https://stackoverflow.com/q/49329919?rq=1 "Vote score \(upvotes -
downvotes\)")[No Consistent Way to Connect ADB over
TCP](https://stackoverflow.com/questions/49329919/no-consistent-way-to-
connect-adb-over-tcp?rq=1)

####  [ Hot Network Questions ](https://stackexchange.com/questions?tab=hot)

  * [ 2 columns followed by 5 columns (multiple columns) in a table ](https://tex.stackexchange.com/questions/533727/2-columns-followed-by-5-columns-multiple-columns-in-a-table)
  * [ How many "I"s am I talking about? : Asks Grandpa ](https://puzzling.stackexchange.com/questions/95256/how-many-is-am-i-talking-about-asks-grandpa)
  * [ Can I substitute salts 1:1 by weight? ](https://cooking.stackexchange.com/questions/105958/can-i-substitute-salts-11-by-weight)
  * [ Leaving major cities during COVID-19 pandemic ](https://travel.stackexchange.com/questions/155180/leaving-major-cities-during-covid-19-pandemic)
  * [ Will Canadian citizens be denied entry to Canada during COVID-19 border closure? ](https://travel.stackexchange.com/questions/155211/will-canadian-citizens-be-denied-entry-to-canada-during-covid-19-border-closure)
  * [ What makes the tonic the tonic and when do I know it changed? ](https://music.stackexchange.com/questions/96374/what-makes-the-tonic-the-tonic-and-when-do-i-know-it-changed)
  * [ Is it possible to control a value in all of my materials with one click? ](https://blender.stackexchange.com/questions/170596/is-it-possible-to-control-a-value-in-all-of-my-materials-with-one-click)
  * [ What does "She ran up the stairs two at a time." mean? ](https://ell.stackexchange.com/questions/241214/what-does-she-ran-up-the-stairs-two-at-a-time-mean)
  * [ A word for a group of people who believe the same scientific idea ](https://english.stackexchange.com/questions/528364/a-word-for-a-group-of-people-who-believe-the-same-scientific-idea)
  * [ Who or what is Milton? ](https://ell.stackexchange.com/questions/241318/who-or-what-is-milton)
  * [ Postdoc position "on hold" due to covid-19 ](https://academia.stackexchange.com/questions/145653/postdoc-position-on-hold-due-to-covid-19)
  * [ Why does the car go on the flywheel longer than it is pushed? ](https://physics.stackexchange.com/questions/537756/why-does-the-car-go-on-the-flywheel-longer-than-it-is-pushed)
  * [ I have a YMA Visa - will Germany let me into the country because of Covid? ](https://travel.stackexchange.com/questions/155235/i-have-a-yma-visa-will-germany-let-me-into-the-country-because-of-covid)
  * [ Conditional statements in Field Calculator QGIS ](https://gis.stackexchange.com/questions/354818/conditional-statements-in-field-calculator-qgis)
  * [ Find how many ordered pairs of integers share only one digit ](https://codegolf.stackexchange.com/questions/201607/find-how-many-ordered-pairs-of-integers-share-only-one-digit)
  * [ Can I safely plug a two prong plug into an extension cord with a ground socket? ](https://diy.stackexchange.com/questions/187140/can-i-safely-plug-a-two-prong-plug-into-an-extension-cord-with-a-ground-socket)
  * [ Using cryptographically random password as both the password and the salt ](https://crypto.stackexchange.com/questions/78377/using-cryptographically-random-password-as-both-the-password-and-the-salt)
  * [ Is the COVID-19 pandemic curve a Gaussian curve? ](https://stats.stackexchange.com/questions/455202/is-the-covid-19-pandemic-curve-a-gaussian-curve)
  * [ Volume adjustment based on frequency of played note ](https://music.stackexchange.com/questions/96384/volume-adjustment-based-on-frequency-of-played-note)
  * [ Question about Federal reserve open market operations - reducing money supply ](https://economics.stackexchange.com/questions/34578/question-about-federal-reserve-open-market-operations-reducing-money-supply)
  * [ How to select multiple cells using ctrl + click ](https://stackoverflow.com/questions/60809845/how-to-select-multiple-cells-using-ctrl-click)
  * [ Storing unchangable data in database vs in code ](https://softwareengineering.stackexchange.com/questions/406877/storing-unchangable-data-in-database-vs-in-code)
  * [ I was up a piece but could not win. What went wrong? ](https://chess.stackexchange.com/questions/28993/i-was-up-a-piece-but-could-not-win-what-went-wrong)
  * [ Is it possible to take advantage of the current low market by buying financial instruments connected with oil/natural gas? ](https://money.stackexchange.com/questions/121944/is-it-possible-to-take-advantage-of-the-current-low-market-by-buying-financial-i)

[ Question feed ](https://stackoverflow.com/feeds/question/2604727 "Feed of
this question and its answers")

#  Subscribe to RSS

Question feed

To subscribe to this RSS feed, copy and paste this URL into your RSS reader.

<img src='/posts/2604727/ivc/6e0e' width='0' height='0' />

default

[](https://stackoverflow.com)

##### [Stack Overflow](https://stackoverflow.com)

  * [Questions](https://stackoverflow.com/questions)
  * [Jobs](https://stackoverflow.com/jobs)
  * [Developer Jobs Directory](https://stackoverflow.com/jobs/directory/developer-jobs)
  * [Salary Calculator](https://stackoverflow.com/jobs/salary)
  * [Help](https://stackoverflow.com/help)
  * Mobile
  * Disable Responsiveness

##### [Products](https://stackoverflowbusiness.com)

  * [Teams](https://stackoverflow.com/teams)
  * [Talent](https://stackoverflow.com/talent)
  * [Advertising](https://stackoverflow.com/advertising)
  * [Enterprise](https://stackoverflow.com/enterprise)

##### [Company](https://stackoverflow.com/company/about)

  * [About](https://stackoverflow.com/company/about)
  * [Press](https://stackoverflow.com/company/press)
  * [Work Here](https://stackoverflow.com/company/work-here)
  * [Legal](https://stackoverflow.com/legal)
  * [Privacy Policy](https://stackoverflow.com/legal/privacy-policy)
  * [Contact Us](https://stackoverflow.com/company/contact)

##### [Stack Exchange  
Network](https://stackexchange.com)

  * Technology
  * Life / Arts
  * Culture / Recreation
  * Science
  * Other

  * [Stack Overflow](https://stackoverflow.com "professional and enthusiast programmers")
  * [Server Fault](https://serverfault.com "system and network administrators")
  * [Super User](https://superuser.com "computer enthusiasts and power users")
  * [Web Applications](https://webapps.stackexchange.com "power users of web applications")
  * [Ask Ubuntu](https://askubuntu.com "Ubuntu users and developers")
  * [Webmasters](https://webmasters.stackexchange.com "pro webmasters")
  * [Game Development](https://gamedev.stackexchange.com "professional and independent game developers")

  * [TeX - LaTeX](https://tex.stackexchange.com "users of TeX, LaTeX, ConTeXt, and related typesetting systems")
  * [Software Engineering](https://softwareengineering.stackexchange.com "professionals, academics, and students working within the systems development life cycle")
  * [Unix & Linux](https://unix.stackexchange.com "users of Linux, FreeBSD and other Un*x-like operating systems")
  * [Ask Different (Apple)](https://apple.stackexchange.com "power users of Apple hardware and software")
  * [WordPress Development](https://wordpress.stackexchange.com "WordPress developers and administrators")
  * [Geographic Information Systems](https://gis.stackexchange.com "cartographers, geographers and GIS professionals")
  * [Electrical Engineering](https://electronics.stackexchange.com "electronics and electrical engineering professionals, students, and enthusiasts")

  * [Android Enthusiasts](https://android.stackexchange.com "enthusiasts and power users of the Android operating system")
  * [Information Security](https://security.stackexchange.com "information security professionals")
  * [Database Administrators](https://dba.stackexchange.com "database professionals who wish to improve their database skills and learn from others in the community")
  * [Drupal Answers](https://drupal.stackexchange.com "Drupal developers and administrators")
  * [SharePoint](https://sharepoint.stackexchange.com "SharePoint enthusiasts")
  * [User Experience](https://ux.stackexchange.com "user experience researchers and experts")
  * [Mathematica](https://mathematica.stackexchange.com "users of Wolfram Mathematica")

  * [Salesforce](https://salesforce.stackexchange.com "Salesforce administrators, implementation experts, developers and anybody in-between")
  * [ExpressionEngine® Answers](https://expressionengine.stackexchange.com "administrators, end users, developers and designers for ExpressionEngine® CMS")
  * [Stack Overflow em Português](https://pt.stackoverflow.com "programadores profissionais e entusiastas")
  * [Blender](https://blender.stackexchange.com "people who use Blender to create 3D graphics, animations, or games")
  * [Network Engineering](https://networkengineering.stackexchange.com "network engineers")
  * [Cryptography](https://crypto.stackexchange.com "software developers, mathematicians and others interested in cryptography")
  * [Code Review](https://codereview.stackexchange.com "peer programmer code reviews")

  * [Magento](https://magento.stackexchange.com "users of the Magento e-Commerce platform")
  * [Software Recommendations](https://softwarerecs.stackexchange.com "people seeking specific software recommendations")
  * [Signal Processing](https://dsp.stackexchange.com "practitioners of the art and science of signal, image and video processing")
  * [Emacs](https://emacs.stackexchange.com "those using, extending or developing Emacs")
  * [Raspberry Pi](https://raspberrypi.stackexchange.com "users and developers of hardware and software for Raspberry Pi")
  * [Stack Overflow на русском](https://ru.stackoverflow.com "программистов")
  * [Code Golf](https://codegolf.stackexchange.com "programming puzzle enthusiasts and code golfers")

  * [Stack Overflow en español](https://es.stackoverflow.com "programadores y profesionales de la informática")
  * [Ethereum](https://ethereum.stackexchange.com "users of Ethereum, the decentralized application platform and smart contract enabled blockchain")
  * [Data Science](https://datascience.stackexchange.com "Data science professionals, Machine Learning specialists, and those interested in learning more about the field")
  * [Arduino](https://arduino.stackexchange.com "developers of open-source hardware and software that is compatible with Arduino")
  * [Bitcoin](https://bitcoin.stackexchange.com "Bitcoin crypto-currency enthusiasts")
  * [Software Quality Assurance & Testing](https://sqa.stackexchange.com "software quality control experts, automation engineers, and software testers")
  * [Sound Design](https://sound.stackexchange.com "sound engineers, producers, editors, and enthusiasts")

  * [Windows Phone](https://windowsphone.stackexchange.com "enthusiasts and power users of Windows Phone OS")
  * [ **more (27)** ](https://stackexchange.com/sites#technology)

  * [Photography](https://photo.stackexchange.com "professional, enthusiast and amateur photographers")
  * [Science Fiction & Fantasy](https://scifi.stackexchange.com "science fiction and fantasy enthusiasts")
  * [Graphic Design](https://graphicdesign.stackexchange.com "Graphic Design professionals, students, and enthusiasts")
  * [Movies & TV](https://movies.stackexchange.com "movie and tv enthusiasts")
  * [Music: Practice & Theory](https://music.stackexchange.com "musicians, students, and enthusiasts")
  * [Worldbuilding](https://worldbuilding.stackexchange.com "writers/artists using science, geography and culture to construct imaginary worlds and settings")
  * [Video Production](https://video.stackexchange.com "engineers, producers, editors, and enthusiasts spanning the fields of video, and media creation")

  * [Seasoned Advice (cooking)](https://cooking.stackexchange.com "professional and amateur chefs")
  * [Home Improvement](https://diy.stackexchange.com "contractors and serious DIYers")
  * [Personal Finance & Money](https://money.stackexchange.com "people who want to be financially literate")
  * [Academia](https://academia.stackexchange.com "academics and those enrolled in higher education")
  * [Law](https://law.stackexchange.com "legal professionals, students, and others with experience or interest in law")
  * [Physical Fitness](https://fitness.stackexchange.com "physical fitness professionals, athletes, trainers, and those providing health-related needs")
  * [Gardening & Landscaping](https://gardening.stackexchange.com "gardeners and landscapers")

  * [Parenting](https://parenting.stackexchange.com "parents, grandparents, nannies and others with a parenting role")
  * [ **more (11)** ](https://stackexchange.com/sites#lifearts)

  * [English Language & Usage](https://english.stackexchange.com "linguists, etymologists, and serious English language enthusiasts")
  * [Skeptics](https://skeptics.stackexchange.com "scientific skepticism")
  * [Mi Yodeya (Judaism)](https://judaism.stackexchange.com "those who base their lives on Jewish law and tradition and anyone interested in learning more")
  * [Travel](https://travel.stackexchange.com "road warriors and seasoned travelers")
  * [Christianity](https://christianity.stackexchange.com "committed Christians, experts in Christianity and those interested in learning more")
  * [English Language Learners](https://ell.stackexchange.com "speakers of other languages learning English")
  * [Japanese Language](https://japanese.stackexchange.com "students, teachers, and linguists wanting to discuss the finer points of the Japanese language")

  * [Chinese Language](https://chinese.stackexchange.com "students, teachers, and linguists wanting to discuss the finer points of the Chinese language")
  * [French Language](https://french.stackexchange.com "students, teachers, and linguists wanting to discuss the finer points of the French language")
  * [German Language](https://german.stackexchange.com "speakers of German wanting to discuss the finer points of the language and translation")
  * [Biblical Hermeneutics](https://hermeneutics.stackexchange.com "professors, theologians, and those interested in exegetical analysis of biblical texts")
  * [History](https://history.stackexchange.com "historians and history buffs")
  * [Spanish Language](https://spanish.stackexchange.com "linguists, teachers, students and Spanish language enthusiasts in general wanting to discuss the finer points of the language")
  * [Islam](https://islam.stackexchange.com "Muslims, experts in Islam, and those interested in learning more about Islam")

  * [Русский язык](https://rus.stackexchange.com "лингвистов и энтузиастов русского языка")
  * [Russian Language](https://russian.stackexchange.com "students, teachers, and linguists wanting to discuss the finer points of the Russian language")
  * [Arqade (gaming)](https://gaming.stackexchange.com "passionate videogamers on all platforms")
  * [Bicycles](https://bicycles.stackexchange.com "people who build and repair bicycles, people who train cycling, or commute on bicycles")
  * [Role-playing Games](https://rpg.stackexchange.com "gamemasters and players of tabletop, paper-and-pencil role-playing games")
  * [Anime & Manga](https://anime.stackexchange.com "anime and manga fans")
  * [Puzzling](https://puzzling.stackexchange.com "those who create, solve, and study puzzles")

  * [Motor Vehicle Maintenance & Repair](https://mechanics.stackexchange.com "mechanics and DIY enthusiast owners of cars, trucks, and motorcycles")
  * [Board & Card Games](https://boardgames.stackexchange.com "people who like playing board games, designing board games or modifying the rules of existing board games")
  * [Bricks](https://bricks.stackexchange.com "LEGO® and building block enthusiasts")
  * [Homebrewing](https://homebrew.stackexchange.com "dedicated home brewers and serious enthusiasts")
  * [Martial Arts](https://martialarts.stackexchange.com "students and teachers of all martial arts")
  * [The Great Outdoors](https://outdoors.stackexchange.com "people who love being outdoors enjoying nature and wilderness, and learning about the required skills and equipment")
  * [Poker](https://poker.stackexchange.com "serious players and enthusiasts of poker")

  * [Chess](https://chess.stackexchange.com "serious players and enthusiasts of chess")
  * [Sports](https://sports.stackexchange.com "participants in team and individual sport activities")
  * [ **more (16)** ](https://stackexchange.com/sites#culturerecreation)

  * [MathOverflow](https://mathoverflow.net "professional mathematicians")
  * [Mathematics](https://math.stackexchange.com "people studying math at any level and professionals in related fields")
  * [Cross Validated (stats)](https://stats.stackexchange.com "people interested in statistics, machine learning, data analysis, data mining, and data visualization")
  * [Theoretical Computer Science](https://cstheory.stackexchange.com "theoretical computer scientists and researchers in related fields")
  * [Physics](https://physics.stackexchange.com "active researchers, academics and students of physics")
  * [Chemistry](https://chemistry.stackexchange.com "scientists, academics, teachers, and students in the field of chemistry")
  * [Biology](https://biology.stackexchange.com "biology researchers, academics, and students")

  * [Computer Science](https://cs.stackexchange.com "students, researchers and practitioners of computer science")
  * [Philosophy](https://philosophy.stackexchange.com "those interested in the study of the fundamental nature of knowledge, reality, and existence")
  * [Linguistics](https://linguistics.stackexchange.com "professional linguists and others with an interest in linguistic research and theory")
  * [Psychology & Neuroscience](https://psychology.stackexchange.com "practitioners, researchers, and students in cognitive science, psychology, neuroscience, and psychiatry")
  * [Computational Science](https://scicomp.stackexchange.com "scientists using computers to solve scientific problems")
  * [ **more (8)** ](https://stackexchange.com/sites#science)

  * [Meta Stack Exchange](https://meta.stackexchange.com "meta-discussion of the Stack Exchange family of Q&A websites")
  * [Stack Apps](https://stackapps.com "apps, scripts, and development with the Stack Exchange API")
  * [API](https://api.stackexchange.com "programmatic interaction with Stack Exchange sites")
  * [Data](https://data.stackexchange.com "querying Stack Exchange data using SQL")

  * [Blog](https://stackoverflow.blog?blb=1)
  * [Facebook](https://www.facebook.com/officialstackoverflow/)
  * [Twitter](https://twitter.com/stackoverflow)
  * [LinkedIn](https://linkedin.com/company/stack-overflow)

site design / logo © 2020 Stack Exchange Inc; user contributions licensed
under [cc by-sa 4.0](https://creativecommons.org/licenses/by-sa/4.0/) with
[attribution required](https://stackoverflow.blog/2009/06/25/attribution-
required/). rev 2020.3.23.36349

Stack Overflow works best with JavaScript enabled <img
src='https://pixel.quantserve.com/pixel/p-c1rF4kxgLUzNc.gif' />



