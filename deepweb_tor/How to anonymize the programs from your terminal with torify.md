  
In the past I’ve posted an article about [Anonymous browsing with Tor](https://linuxaria.com/howto/gnome-anonymous-browsing-with-tor?lang=en) that can be useful when you use your favorite browser and you wish to stay anonymous thanks to the [Tor](https://trac.torproject.org/projects/tor) software.

[Tor](https://en.wikipedia.org/wiki/Tor_(anonymity_network)) (short for The Onion Router) is a system intended to enable online anonymity. Tor client software directs internet traffic through a worldwide volunteer network of servers to conceal a user’s location or usage from anyone conducting network surveillance or traffic analysis. Using Tor makes it more difficult to trace Internet activity, including “visits to Web sites, online posts, instant messages and other communication forms”, back to the user and is intended to protect users’ personal freedom, privacy, and ability to conduct confidential business by keeping their internet activities from being monitored.

Today I want to show some simple uses of the command `torify` that can be used from the Linux terminal.  
  
  
  
**`torify`** is a simple wrapper that attempts to find the best underlying Tor wrapper available on a system. It calls torsocks or tsocks with a tor specific configuration file.

As first thing install the software, `tor` is usually found on all the repository so for Debian, Ubuntu and Mint you just have to type:

|   |
|---|
|sudo apt-get install tor|

In this example we’ll keep all the standard configuration but 2 things, in the file `/etc/tor/torrc` you should uncomment the directive:

|   |
|---|
|ControlPort 9051|

And set

|   |
|---|
|CookieAuthentication 0|

With these 2 options we set the port on which Tor will listen for local connections from Tor controller applications, and we tell to Tor that we don’t need an authentication, so any program can control Tor (don’t do this on a shared computer or server), later in this post I’ll show how to set a password, once changed save the file and restart `tor` with the command:

|   |
|---|
|sudo /etc/init.d/tor restart|

And now a simple example that shows how to use the command torify and start a new session on tor from the Linux terminal, as first thing I get [my public IP](https://linuxaria.com/howto/get-your-private-and-public-ip-from-the-linux-terminal "Get your private and public IP from the Linux terminal") address with:

|   |
|---|
|$  curl ifconfig.me<br>79.35.56.153|

So 79.35.56.153 is my public IP, now I use `torify` before the command `curl` in the command line :

|   |
|---|
|$ torify curl ifconfig.me 2&gt;/dev/null<br>74.120.15.150|

As you can see now I browse on the net with a different Ip: 74.120.15.150, but from the command line I can also force Tor to start a “new session” with the command:

|   |
|---|
|echo -e 'AUTHENTICATE ""\r\nsignal NEWNYM\r\nQUIT' \| nc 127.0.0.1 9051<br>250 OK<br>250 OK<br>250 closing connection|

This small script connects to port 9051 and issue the command “`signal newnym`” that will make Tor switch to clean circuits, so new application requests don’t share any circuits with old ones, now if I check my IP I expect to see a new one:

|   |
|---|
|$ torify curl ifconfig.me 2&gt;/dev/null<br>46.59.74.15|

In this small example I’ve used `curl` to get my ip address, but with torify you could use almost any terminal program, such as `ssh`, `wget`, `w3m` or `BitchX`.  
  

### How to set a password for Tor  

If you are in a shared environment it’s better to set up a password for Tor, here it’s how you can do it in a few steps:

**1) Generating your encrypted password:  
**

In a terminal type:

|   |
|---|
|tor --hash-password "passwordhere"|

This will generate a password hash, you will need to save this for inserting into the TOR configuration file in the next step.  
(This is the hash for “passwordhere”, 16:113BD60B17CD1E98609013B4426860D576F7096C189184808AFF551F65)

**2) Editing the Tor configuration file :  
**

Open the file `/etc/tor/torrc` and comment the line we set before:

`#CookieAuthentication 0   `

Next find the line:

`#HashedControlPassword 16:2283409283049820409238409284028340238409238   `

remove the # at the beginning and replace the password hash that is currently there with the hash you have just generated.

So with the hash generated in this example the configuration would be:

`HashedControlPassword 16:113BD60B17CD1E98609013B4426860D576F7096C189184808AFF551F65   `

Save your changes.

**3) Restart TOR:**

Restart Tor so it get the new directives with:

|   |
|---|
|sudo /etc/init.d/tor restart|

Now you can use the former command to connect to teh Tor daemon, but using your password, so for me this would be:

|   |
|---|
|echo -e 'AUTHENTICATE "passwordhere"\r\nsignal NEWNYM\r\nQUIT' \| nc 127.0.0.1 9051|

References:

[http://fixitts.com/2012/09/28/data-scraping-series-2-1-rotating-your-tor-ip-address-php-or-linux/  
](https://linuxaria.com/howto/Rotating%20your%20TOR%20IP%20Address%20(PHP%20or%20Linux))[Using Tor to Anonymize Your Traffic (and setting up Tor in Arch Linux)  
](http://www.speakingcode.com/2012/04/13/using-tor-to-anonymize-your-traffic/)[Using Tor in Ubuntu | Torify our life](https://vocf.wordpress.com/2008/02/18/using-tor-in-ubuntu-torify-our-life/)

