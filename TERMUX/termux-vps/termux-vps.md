![[Pasted image 20230726105143.png]]

# Android phone into a VPS hosting server, Hosting Apps ,Nginx ,Music server and a lot

[#devops](https://dev.to/t/devops)[#android](https://dev.to/t/android)[#nginx](https://dev.to/t/nginx)[#webdev](https://dev.to/t/webdev)

All rights guys, this is my first appearance in a public blog like this, posting an article. I don't have an account in Medium.com, and I don't like it nowadays since it has imposed limits. Anyways, I'm there in devs network (freenode) and that also gave me an impression. Personally, I've a blog (blog.b3nsh4.tk) and seems, I've less traffic hits since it went unmaintained for few years (but, it will be back soon with full power). And that led me to think about dev.to

Structure this article.  
-> Intro to pain made by CGNAT/Ipv4  
-> Intro to ipv6 setup  
-> setting up nginx  
-> setting up an http server  
-> DNS configuration  
-> Possibilities  
-> Part-2 (soon)

-> Prerequisites: Patience, coffee, snacks :)

Okay, I'm about to complete what I have to say part by part for easy digestion and I'm really excited to share this. So, enjoy reading :)

How ipv4 made chaos!

In our ipv4 world, to make your server accessible to outside world, you would do portforwading, ddns and I know people who bought public ip to home, connect with pi and hosting stuffs. Wasn't it so tedious. CGNAT (NAT444) really made us crazy.

Well, that can't be blamed since ipv6 was only at implementation stage. The overall idea was; In my ISP, they give me a /30 subnet and it's under router-A ,it's to router-B and to router-C to internet  
Me -> Ra -> Rb -> Rc -> Internet Or Me -> Ra -> Rb -> internet.
![[Pasted image 20230726105205.png]]

The structure (look via traceroute) depends on architecture. Looks, It's clear that we cannot run something local to make it accessible via internet. Tunnels are exceptions, you forward local port to your VPS or services like serveo,and done!  
So this NAT stuff was the pain in everyone's mind. I know CGNAT really sucks. While this meme suits for some ISPs
![[Pasted image 20230726105222.png]]

Well, let me get to the point of how ipv6 works. Turns out (this is Andrew Ng effect), everyone is using Android with 4G LTE/VoLTE. Internet advanced is pretty significant after ipv6. In short what ipv6 really gives us is a power global unicast address. An address which is globally reachable. Before moving any further, I'm not willing to explain the architecture of ipv6 here and I assume you know basics and if you don't, that's still okay.

What can we do with this global unicast address?  
Yes, it makes you available via internet. Meaning that, you could host something from your phone and that service is accessible via internet now. No forwarding garbage. But, there are many things to care of which I'll talk now.

How to enable ipv6 now?  
Take your android settings -> Networks -> APNs -> Edit existing APN settings -> Select protocol to ipv4/v6. I've a video explaining this; 

(Meanwhile few people at twitter yelling: "ipv6 isn't stable".  
IPV6 Fans: Troll starts)

Cool, now your device is ipv6 enabled. But wait! Why do we use ipv6 and ipv4 together (dualstack). Well, this is necessary for the coexistence of both worlds. Simple example;  
I have enabled ipv6 only in protocol settings, then I host a web server, python httpserver. Can your friend with a ipv4 access the network? No! And this is one of some reasons why dualstack is useful.

Okay, your ISP still don't provide ipv6?  
Hmm! they should have done that and you could ask them why. But, there's a workaround I use when I'm in this situation. We could use a Ipv6 Tunnel Broker. This technique allows you to connect IPv6 sites over your ISP's IPv4 network. At the tunnel head end, an IPv6 packet is encapsulated into IPv4 packet and sent to the remote tunnel destination. To make it technical, think how GRE tunneling works!

Okay, There are few providers, but the one by Hurricane Electric is good. (tunnelbroker.net) .  
A small picture would be similar;  
Me(ipv6) -> ISP (ipv4) -> Webserver (ipv6)

Cool! Now we have IPV6 ready. Awesome!

Now what?  
Wouldn't it be nice if we have a Linux machine running locally so that we can do few ip6tables stuffs? Yah! We can use a Linux proot, chroot in android. Personally, I use Termux. But, there are few guys who can also help with this. Install 'whatever' from your favorite app provider (I use Fdroid).

All good! Let's setup the environment.  
Let's start by installing python. Only because we'll get SimpleHTTPServer module. Of course, you can install whatever suits your needs. In then end, we'll have a Webserver. Make a simple index.html file put it in somewhere. Cd into that dir and initialize httpserver. It normally bind to both ipv6 and ipv4.  
Verify it! To test out, you could try ipv4 loopback or the ipv6 loopback. Okay, we've our server running.

How to make it accessible from internet?  
Well, at this point your server is already accessible from internet. You could try accessing with your ipv6 address. But, it's a tedious task to remember/copy the address and send it to someone. Most of you have already got the idea. Yes, we could use a ddns service and get a hostname. This is what we are going to do. Not only that, we don't have a static ipv6 address and need to update it all the time. This is why I wrote ipv6 ddns updater for dynv6 ( [https://github.com/b3nsh4/dynv6-updater](https://github.com/b3nsh4/dynv6-updater) )
![[Pasted image 20230726105250.png]]

dynv6 is an ipv6 ddns provider. I've been using it for an year and ½ and works really well.  
Okay, we resister with them/or any provider you like. Copy, paste your ipv6 address there. Done! Now, your server is accessible via that hostname.  
myhostname.ddns.service:8080 (my server port)

This works all the time?  
No! You know your ipv6 address will change every time you disconnect. Now you have to update the address either using the script (above mentioned) or manually update it (who does that?). But, who has time? What I I've been doing all the time something really effective.

All right, we have a domain. Now, goto your DNS settings and add a CNAME record and point it your ddns hostname. You don't need an A record. One CNAME record is enough. But, if you already have an A record, it's completely okay.
![[Pasted image 20230726105304.png]]

You can also add AAAA record and point it to your ipv6 address. Which again, you need to manually change it. Who has time?

To get an entire picture of what I just said, I made a video explaining this. Hope this helps 

Okay! Trust me, at this point, you're done! But, let's setup nginx in Termux and host our own music server (online music player may be?) Whatever you used to call it.

A quick note: We are running nginx on port 80 , which requires you to have root privilege. If don't you will end up having port numbers after your domain. yourdomain:port. But, you don't necessarily need to use nginx which I'll talk after this.

Okay! Do `pkg install nginx` and goto the configuration. I'm not going through the configuration. This is usually the same configuration you normally use in any Linux machine expect one little change. Since Termux is a single user environment, the worker process should be 'root'. I mean, make;  
user root (usually the first line)

```nginx
user root
events { 
	worker_connections 1024;
}
http {
	server_names_hash_bucket_size 64;
	server {
		//SOME STUFF HERE
		server_name bb.example.com;
	location / {
		proxy_pass http://127.0.0.1:8000;
		}
	}
	server {
		//SOME STUFF HERE
		location / {
			proxy_pass http://127.0.0.1:2233;
			}
		}
	}

```

In nginx config.
![[Pasted image 20230726105625.png]]

[Could not find all screenshots, so posting what i got]

And, then you can write your normal forwarding rules as showed and setup pages accordingly (like how you would normally use nginx). But, proceed with caution! You know how fatal it is to run your internet facing Webserver as root. So, this is discouraged at the same time. But, if you're in a hurry and need to get things done, this would help!.

If running nginx as root is bad, why the heck did you explain this?  
Well, you see, I just wanted to explain all possibilities ( _smile in plain_ )

Back to SimpleHTTPServer (python). As we said, make an index.html and start http server by explicitly providing the port as 80. (Needs root) . If everything is good, you can see few tcp6 listeners by nginx.

Python -m http.server 80 (from index dir)  
Okay, let's use tree command from inside our music directory to generate the structure like below.

![[Pasted image 20230726105655.png]]

Now, depends on your setup, either AAAA record or CNAME record, in the end, we'll have a hostname pointing to our current address. And this , I could access it from internet and my friends could listen/download my libraries. It's fun. Why don't you make this small piece as a CDN, Host an app if it has some process power. Figure out your idea!

Cool! This seems the possibilities are endless. You could host an entire app from your phone and what not? We need to implement containerization, docker and run inside it.  
Since your device is now exposed to internet, there are some Security measures that we have to take. Which I'm looking forward to write in upcoming post (soon).

Enjoyed? Thank you very much.  
DMs are always open via Twitter, also i write future updates via twitter.com/b3nsh4 .  
Finally, i want to Thank you all for your time :)  
Stay tuned for Part-2, Part-3 and more from now! 😉

---

If you would to donate my works/future works, kindly consider donating ❤️  
PayPal: [https://www.paypal.me/b3nsh4](https://www.paypal.me/b3nsh4)  
UPI: private.benshaji-1@okicici
