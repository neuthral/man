       search...
   Blog




  IRC SERVER + SSL + SERVICES , HOW
  TO BUILD YOUR OWN
  WEDNESDAY, 21 AUGUST 2013 POSTED IN BLOG (/BLOG)



  How to build your own IRC server with services like, nickserv, chanserv etc, and a secure encrypted
  connection with SSL, you can build a secure chating environment away from unwanted eyes and
  smart ass agencies.

  This is a step by step tutorial on how to build your Private IRC Server with Services and encrypted
  SSL connection, it will be invisible to the outside world and you can even filter individuals by
  hostname, i will be using Debian (http://www.debian.org/) as the O.S., the ircd server i chose was
  the IRCD-hybrid (http://www.ircd-hybrid.org/) version 8.1.7
  (http://prdownloads.sourceforge.net/ircd-hybrid/ircd-hybrid-8.1.7.tgz),its my favourite, very
  reliable, its an active project and it has regular releases that fix any security bugs as soon as they
  are detected and/or reported.

  This will be enought to get our IRC private network up and running, but we will want to be able to
  register nicknames, channels and even bot services, that is done apart with another software, the
  services program and i chose Anope (http://www.anope.org/) version 1.8.9 (/wget
  http://sourceforge.net/projects/anope/files/anope-legacy/Anope%201.8.9/anope-1.8.9.tar.gz), also
  very reliable.

  We will also need to generate our own SSL certificates and i will be using OpenSSL
  (http://www.openssl.org/) that ships by default with Debian.




  This tutorial will be divided in 3 chapters:

1. First Chapter (downloading and installing)

2. Second Chapter (Configuring the actual server and services)

3. Third Chapter (configuring SSL)
First Chapter
Downloading and installing :



Start by opening your console/terminal and assuming your on your home folder ( otherwise type cd
~/ ), and we will be starting by downloading ircd-hybrid and anope, type:

 wget http://prdownloads.sourceforge.net/ircd-hybrid/ircd-hybrid-8.1.7.tgz



And anope, type:

 wget http://sourceforge.net/projects/anope/files/anope-legacy/Anope%201.8.9/anope-
 1.8.9.tar.gz



Before we continue any further and in order to be able to use SSL encrypted connections we need
to install openssl development librarys on our Debian system, type:

 sudo apt-get install libssl-dev



Next we unpack hybrid and anope, type:

 tar -xvf ircd-hybrid-8.1.7.tgz



Next type:

 tar -xvf ./download



Next we will compile the sources we just downloaded,lets begin with hybrid, type:

 cd ~/ircd-hybrid-8.1.7/
 ./configure -prefix="/home/electropepper/ircd"
 make
 sudo make install
     In the path above, change the name "electropepper" to the one of your user



Next we compile anope, type:

 cd ~/anope-1.8.8/
 ./configure



Several questions will be made, and i just pressed ENTER to them all, this way i chose all default
options, next type:

 make
 sudo make install



Now we finally have everything installed and ready, the next step is editing the configuration files
for both IRCD-hybrid server and anope services, but because we did sudo while installing we need
to change the owner of the installation files, type:

 cd ~/ircd/etc
 sudo chown -R electropepper.electropepper ircd
 sudo chown -R electropepper.electropepper services




Second Chapter
Configuring the actual server and services :



We go now into the folder where we installed the IRC server, enter the etc folder and make a copy
of the file reference.conf renamed ircd.conf which will the configuration file for the server, type:

 cd ~/ircd/etc
 cp reference.conf ircd.conf


     A small note here, i will be using VIM editor you can use any editor of your choice you just
     have to replace whenever you see vi with your editor like for example, gedit ircd.conf .
So lets proceed to editing our configuration file ircd.conf, type:

 vi ircd.conf



Now uncomment the following lines, by inserting "//", like this:


 // havent_read_conf = 1;

 // flags = need_ident;



At this moment you have a basic working IRCD server, you can try to run and connect to it with a
client, but im going to proceed for now.

We need an operator to have total control over the server so we can rehash the config file
whenever we wish, whithout having to reset the server, believe me it will make your life much
easier, to do this we go to the operator block that starts at line 424, and we change the name to
electropepper and password to 12345, like this:

 name = "electropepper";

 user = "*@192.168.1.*";

 password = "12345";

 encrypted = no;



Now we can reload the ircd.conf file after editing it, with the commad "/rehash" inside the client
after identifying ourselves as operator.
Just drop a line in comments asking or If a lot of people request and i have enought time i can
make a quick tutorial on the subject, but for now we will proceed to configure our services.

Again inside our configuration file ircd.conf we go now to the service block that starts on line 548
and we baptise our services server with the name anope.services, like this:

 name = "anope.services";

 host = "127.0.0.1";
 send_password = "pepper";

 accept_password = "pepper";



After this we need to get this info and match it into the anope configuration file, we also need to
make a copy of example.conf and rename it has services.conf, type:

 cd ~/services/

 cp example.conf services.conf

 vi services.conf



And start editing:

 IRCDModule "hybrid"

 RemoteServer 127.0.0.1 6666 "pepper"

 ServerName "anope.services"

 ServicesRoot "electropepper"



We have anope configured to connecto to our ircd server, now we can start IRCD-Hybrid and Anope
services, type:

 ~/ircd/sbin/./ircd

 ~/services/services



Joy joy :), fire cracks and so on.




Third Chapter
Configuring SSL :
Final chapter lets configure our secure connection, we are going to generate our own certificates
with openssl, it is explained inside the ircd.conf how to do it starting in line 100, first we generate
a RSA key, type:

 cd ~/ircd

 mkdir ssl

 cd ssl

 openssl genrsa -out rsa.key 2048

 chmod 600 rsa.key



Now we generate the certificate, type:

 openssl req -new -days 365 -x509 -key rsa.key -out cert.pem



As you see above, several questions will be made, for the purpose of this tutorial(or maybe not) i
just made up the answers, its ok it still works no problem, now we create the DH parameter file,
but because we used 2048 while generating the RSA key we will use the same now, type:

 openssl dhparam -out dhparam.pem 2048



Now we have our own SSL certificates, we just edit our ircd server config file:

 rsa_private_key_file = "/home/electropepper/ircd/ssl/rsa.key";

 ssl_certificate_file = "/home/electropepper/ircd/ssl/cert.pem";

 ssl_dh_param_file = "/home/electropepper/ircd/ssl/dhparam.pem";



And uncomment in ircd server config file:

 host = "192.168.0.1";
And yet again now, comment in:

 ssl_server_method = tlsv1, sslv3;



And there you go, feel free to ask any question on comments, and make sugestions for other
tutorial on this subject. You can now play around with settings on the config files to change
chanserv and nickserv options or even block IPs , ban ips etc.

Enjoy your new secure chat server :).




Tweet (//twitter.com/share)




Webmaster Ricardo - Copyright © 2013 - 2019
