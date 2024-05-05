How to Unlock Android Phone via ADB (PIN & Pattern)
by RakeshMarch 29, 2023
Smartphones are fragile things. Just one accidental drop may smash its screen to the extent that you might not be able to use our device. If you are not able to unlock your Android phone or tablet using the preset PIN or pattern because the touchscreen is damaged, there are some ADB commands that might come in handy. If you aren’t able to unlock your device the normal way by entering the PIN or drawing pattern, you can follow the steps given in this tutorial to learn how you can unlock your Android phone the ADB way.

Unlocking your Android phone using ADB commands might really not be a practical solution if you are not able to enter the PIN or draw the pattern on your device’s screen. One cannot carry a laptop all the time just for this purpose. However, if your phone or tablet is locked or unusable because of a broken touchscreen, you can at least get a chance to back up your data and wipe sensitive things before handing over your device to a technician.

Android users can do a lot of things using ADB commands like removing bloatware, turning Talkback on or off, changing Android device name, unlocking your Android phone’s PIN or pattern lock, rebooting your device into the bootloader or fastboot modes, and so on. I have already written some useful tutorials to help users with damaged touchscreen and hardware buttons.

Turn on Android Device without Power Button
Turn off Android Phone without Power Button
Please note that you won’t be able to remove the pattern or PIN lock on your Android phone using ABD or Fastboot commands. Therefore, if you forgot the PIN or pattern on your device, this tutorial is of no use to you. Also, due to the enhanced security on modern smartphones, you cannot bypass the Android lock screen using commands on your computer.

In this Article hide
1. Getting Prepared
2. Unlock Android Phone PIN through ADB
3. Unlock Android Phone Pattern using ADB
4. Remote Control Tools for Unlocking Android Devices
4.1. scrcpy
4.2. MonkeyRemote
4.3. Vysor
Getting Prepared
Since this tutorial involves using ADB Shell commands to unlock an Android phone with PIN or pattern without touching the screen at all, you must download and set up the latest SDK Platform-tools on your Windows, Linux, or Mac machine. In most cases, ADB commands require USB Debugging to be enabled on the phone to do their job. Also, make sure you have a compatible USB cable so that your phone and computer can communicate with each other properly.

Unlock Android Phone PIN through ADB
Having installed ADB and fastboot tools on your PC, you just have to follow the steps given below to unlock an Android device that is locked with PIN protection through ADB Shell commands.

Unzip the ‘platform-tools-windows.zip‘ that you downloaded earlier and open the extracted folder.
Place the mouse cursor at an empty spot inside the folder window, press the Shift key, and right-click on the mouse to open the Windows context menu. Select the ‘Open PowerShell window here‘ option to launch the command prompt.windows powershell window option
Now, connect your Android phone or tablet to your computer using a compatible USB cable.
In the Windows PowerShell command window, type the following command and hit the Enter key to make sure that ADB has detected your Android device.
adb devices
You’ll see a string of alphanumeric values representing your device as shown in the screenshot attached below. If you see any error, try reconnecting your device or using a different USB cable.adb devices command in windows powershell
Now that ADB has detected your device, you need to use the following command to proceed.
adb shell
adb shell command

If you get the dollar sign as output you are all set to unlock your Android phone using ADB commands.
In case you want to wake up your Android phone’s touch screen while it’s locked using ADB, you can use the following command after invoking ‘adb shell‘.
input keyevent 26
Just type the command given below and press the Enter key to execute it. Don’t forget to replace ‘XXXX’ with the PIN or passcode you’ve set for your phone’s lock screen.
input text XXXX
simulate click okay adb shell

The above command will unlock your Android device without having to enter your PIN without touching the screen. However, if you have to press ‘OK‘ after entering the PIN, you’ll need to use one more command to simulate the OK button click.
input keyevent 66
unloack android pin using adb command

That’s it! You have successfully unlocked your Android device through ADB commands. I successfully tested this method on my Samsung Galaxy S21 Ultra, LG Wing, and OnePlus 8.
Unlock Android Phone Pattern using ADB
While it’s very easy to unlock an Android device locked with a PIN using ADB commands, things get complicated doing the same if you have set a pattern instead. Actually, drawing a pattern with continuous swipe events using commands is not easy at all. Upon extensive research about the possible ways to draw a lock screen pattern through ADB, I have found some working solutions that might do the job if followed carefully.

You can use the sendevent commands after invoking ‘adb shell’ to simulate the following actions or finger  gestures on your phone’s pattern lock screen:

Start touch (finger down)
New point (finger move)
End touch (finger up)
In order to perform the above actions to start and end a pattern swipe using ADB commands, you will basically need the following sendevent commands.
sendevent 3 0
sendevent 3 1
sendevent 0 0 0 # (event separator)
Github user Matt Wilson has prepared a great script for Android pattern unlock. You can customize this script by changing the variables for the 9-point pattern setup of your Android phone and unlock it. Needless to say, the Android pattern unlock script requires USB debugging enabled on your device to function properly.

The hardest part in using Matt Wilson’s pattern unlock script is to find the correct coordinates or variables of your pattern as they might differ depending on the resolution (in pixels) of your phone’s screen. The good thing is, there is another piece of code by Marian Schedenig called ADB Control which can help you view the screen of your Android phone or tablet in an output window on your computer. You can thus see the input taps and swipe events, and learn about the variables by clicking on the points of the pattern lock you have set on your phone.

Once you have the set of coordinates for the pattern you have set on your Android device, you can easily replace the values for (x1, y1), (x2, y2), (x3, y3), (x4, y4), (x5, y5). The number of coordinates depends on the points of the pattern you’ve set.

The simplified version of Matt Winson’s script is shared by Haider Khan on Stack Overflow and contains the coordinates for an Android device with a 1080 x 1920 px screen. Don’t forget to visit the source page for more information. You can execute the following commands after changing the x and y values that correspond with the pattern of your Android phone to achieve a continuous pattern swipe to unlock your phone using ADB.

adb shell
input keyevent 26
sendevent /dev/input/event3 3 57 14
sendevent /dev/input/event3 1 330 1
sendevent /dev/input/event3 3 53 x1
sendevent /dev/input/event3 3 54 y1
sendevent /dev/input/event3 3 58 57
sendevent /dev/input/event3 0 0 0
sendevent /dev/input/event3 3 53 x2
sendevent /dev/input/event3 3 54 y2
sendevent /dev/input/event3 3 58 57
sendevent /dev/input/event3 0 0 0
sendevent /dev/input/event3 3 53 x3
sendevent /dev/input/event3 3 54 y3
sendevent /dev/input/event3 3 58 57
sendevent /dev/input/event3 0 0 0
…
sendevent /dev/input/event3 3 53 xn
sendevent /dev/input/event3 3 54 yn
sendevent /dev/input/event3 3 58 57
sendevent /dev/input/event3 0 0 0
sendevent /dev/input/event3 3 57 4294967295
sendevent /dev/input/event3 1 330 0
sendevent /dev/input/event3 0 0 0

I hope the above string of ADB commands helped you unlock your Android phone pattern using cmd.

Remote Control Tools for Unlocking Android Devices
If you are not able to use your phone’s touchscreen to input the lock screen PIN or draw a pattern to unlock it, there are some remote control tools that might help you. Please note that these tools require USB debugging enabled on your Android device and your computer authorized to work.

scrcpy
Scrcpy is a great tool that works on works on Linux, Windows, and macOS. and allows you to control your phone remotely via ADB. It requires a little app to be installed on your device to stream the contents of your phone’s screen to the computer letting you control your device.

MonkeyRemote
MonkeyRemote is another remote control tool that connects over ADB and lets you control your phone using the computer mouse. Unlike Scrycpy and Vysor, it doesn’t require any app to be installed on the Android device you want to control via PC.

Vysor
Vysor is a great remote control tool that streams your phone’s screen on your computer and lets you control it using your mouse. It’s a Chrome web app that communicates with your phone via ADB after you install a companion app.

In case you know about a better way to unlock an Android phone PIN or pattern lock via ADB, please share it with us so that it can help others.

Tags:ADB AND FASTBOOTANDROID TIPSTIPS AND TRICKS