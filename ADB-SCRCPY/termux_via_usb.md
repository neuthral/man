# Access Termux via USB

I've been using Termux over SSH for quite a while now. I've always done so over WiFi. This works reasonably well at home, where I control the IP Addresses. In other networks it was more annoying, because I always had to run ifconfig first, to get my IP. But the big annoyances start when you want to use it in a place that has no WiFi network available. Previously, I used an Android tablet and a keyboard. With this I set up a WiFi direct connection between my phone. It's wonky and sometimes requires to restart both devices before working again, but it works.

Then I got a laptop. Installed a proper Linux on it and tried to connect to Termux. I tried setting up WiFi Direct. But after an hour or so of messing around wpa_supplicant I concluded that it's just too much of a hassle. But somewhere in the GitHub issues I came across the mention of connecting to Termux via ADB. The ADB shell is bad. I didn't actually manage to launch Termux programs via the ADB shell, but I heard that it's possible. But, and this is the point of this article, you can create port forwarding via ADB. This means that you can map a local port on your computer to a port on your Android device. Then you can open the 8022 port to access Termux via SSH over USB. This is awesome, when you're on the train, in a coffee shop or otherwise in a place with wonky or nonexistent WiFi.

Here is how you do it
1. You need ADB
Most operating systems have an ADB package. On my one I was simply able to install it with:

sudo apt install adb
For other platforms you can check this site here.

2. Create your port forward
This part is really simple as well, and that's key. I don't want to do 500 things every time I want to connect to my phone.

adb forward tcp:8022 tcp:8022
This is really all it takes. The first instance of tcp:8022 is the local port you want to bind the remote port to. The second one is the port from your Android device. Because Termux' SSHD runs on port 8022 by default, this is what you want.

3. Connect to it
Now that your local port is bound to your Android device you can simply connect to localhost on your computer:

ssh localhost -p 8022
#This is were you put the local port
#(ie. the first one)
This will connect you to your SSH Server. If you haven't set this up yet read this.

You will need to run the ADB command after every restart or after you've unplugged your device. I set up an alias for myself for the following command sequence:

adb forward tcp:8022 tcp:8022 && adb forward tcp:8080 tcp:8080&& ssh localhost -p 8022

This will also setup the port 8080, which is used by the httpd webserver on termux
#Technology #Termux #CLI #Android #Tutorial #Snippet #SSH #2016