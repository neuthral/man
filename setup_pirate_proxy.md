Sections
========

-   [Overview](https://proxybay.github.io/setup.html#Overview)
-   [NGINX Method (Advanced)](https://proxybay.github.io/setup.html#Nginx)
-   [PHP Method](https://proxybay.github.io/setup.html#PHP)
-   [Tips](https://proxybay.github.io/setup.html#Tips)
-   [Next steps](https://proxybay.github.io/setup.html#what-next)

Overview
========

This guide will explain how to set up your own Pirate Bay proxy site. A proxy site helps users access The Pirate Bay in countries and networks where The Pirate Bay has been blocked.

NGINX is our recommended method of setting up a proxy since it is fast, requires few resources, and has caching support. However, setting up an NGINX proxy is for advanced users since it involves the Linux command line. You will also need access to a server with command line access such as a VPS or dedicated server.

A simpler method to setup a proxy is by using the PHP script. The PHP script is much easier to setup and can be used on shared web hosting packages that support PHP. This means unlike the NGINX method, you do not need a dedicated server or VPS

### Update: April 12, 2020

The Pirate Bay has made some new changes that break existing proxy methods

We have updated the [PHP script](https://github.com/piratebayproxy/UnblockedPiratebayClean) and it is now compatible with the new update

NGINX Method (Advanced)
=======================

With the NGINX method, you will compile NGINX from source in order to include the substitutions module. The substitutions module allows NGINX to search and replace text on the pages. Once set up, the NGINX server will serve as a fully functioning reverse proxy without the need for any server side code or scripts.

In order to compile NGINX, you will need root access to a Linux based server (e.g. VPS or dedicated server)

1\. Once you have your server online you will want to get NGINX compiled and installed.

To do this, we will first need to install some packages.

a) If you're using a Debian based OS (e.g. Ubuntu), run this:

`apt-get install libpcre3 libpcre3-dev zlib1g zlib1g-dev openssl libssl-dev gcc make git wget`

b) If you're using a Red Hat based OS (e.g. Centos), run this:

`yum install -y zlib zlib-devel pcre pcre-devel openssl openssl-devel gcc make git wget tar`

2\. Now that the packages are installed, we will download the NGINX source code to the /tmp/nginx directory and compile it.

You can find the latest version [here](http://nginx.org/en/download.html).

`mkdir -p /tmp/nginx;cd /tmp/nginx`\
`wget https://nginx.org/download/nginx-1.20.1.tar.gz`

3\. We need to download the [substitutions module](https://github.com/yaoweibin/ngx_http_substitutions_filter_module "substitutions module on Github") in order to make text and regex replacements with the proxy.

Clone the Github repository with the following command.

`git clone git://github.com/yaoweibin/ngx_http_substitutions_filter_module.git`

4\. Extract the source.

`tar xzvf nginx-1.20.1.tar.gz;cd nginx-1.20.1`

5\. Now we can configure NGINX. Ensure that the substitutions module folder path is correct.

See [this](https://www.nginx.com/resources/wiki/start/topics/tutorials/installoptions/ "Configure Nginx") link for more configuration options.

`./configure --with-http_ssl_module --add-module=/tmp/nginx/ngx_http_substitutions_filter_module`

6\. Now we can compile and install NGINX. It will be installed to /usr/local/nginx/ by default.

`make && make install`

7\. Test if NGINX is working by starting it

Note: If logged in as root, you don't need the sudo command

`sudo /usr/local/nginx/sbin/nginx`

8\. Check if it's working by typing in your server IP in your web browser. You should see the "Welcome to NGINX!" message.

If it's working, stop NGINX with the following command now so we can configure it.

If it's not working, ensure nothing else is running on port 80 ([link](https://stackoverflow.com/questions/14972792/nginx-nginx-emerg-bind-to-80-failed-98-address-already-in-use "Stackoverflow help")) or try checking Google for a solution.

If you're using a Centos/RHEL based Linux distro, ensure your firewall is allowing HTTP traffic, see [this link](https://www.osetc.com/en/centos-rhel-how-to-open-port-in-linux-firewall.html "Open port in firewall")

`sudo /usr/local/nginx/sbin/nginx -s stop`

9\. Rename the default config file so we've got a copy of the original config

`cd /usr/local/nginx/conf;mv nginx.conf nginx.conf-backup`

10\. Copy the following config and insert it into nginx.conf using a text editor such as nano or vi. (e.g. nano nginx.conf). Change yourdomain.com to your own domain in the config.

For more information on how to configure NGINX, see [this](https://www.linode.com/docs/web-servers/nginx/how-to-configure-nginx/ "Linode tutorial") link.

**Update: April 2020** The NGINX config has been updated for the new TPB update.

`worker_processes auto; events {worker_connections 1024;} http { include mime.types; default_type application/octet-stream; proxy_ssl_server_name on; sendfile on; gzip on; #Logs access_log logs/access.log; error_log logs/error.log; server { listen 80; server_name yourdomain.com; #Redirects proxy_redirect https://thepiratebay.org http://$host; proxy_redirect http://thepiratebay.org http://$host; #Other URI's location = / {return 301 /index.html;} location /session {return 302 /;} location ~ /torrent/(?<myvar>[0-9]+)/ {return 301 /description.php?id=$myvar;} location ~ /search/(?<myvar>.+)/0/ {return 301 /search.php?q=$myvar;} #Root URI location / { proxy_pass https://thepiratebay.org; proxy_set_header Host thepiratebay.org; proxy_set_header Referer 'https://thepiratebay.org'; proxy_set_header Accept-Encoding ""; proxy_set_header CF-Connecting-IP ""; #Substitutions subs_filter_types 'application/javascript'; subs_filter 'https://torrindex.net' "http://$host/torrindexp"; subs_filter 'https://apibay.org' "http://$host/apip"; subs_filter '<a href="/session/" title="Login/Upload">Login/Upload</a> |' ''; subs_filter '<a href="/session/" title="Register">Register</a>' ''; subs_filter '<a href="/session/" title="Login">Login</a> |' '<b><a href="https://" title="TPB Proxy List">TPB Proxy List</a></b>'; subs_filter '<a href="" title="Register">Register</a>' ''; subs_filter 'https://thepiratebay.org' http://$host; subs_filter 'thepiratebay.org' $host; } #API URI location /apip/ { proxy_pass https://apibay.org/; proxy_set_header Host apibay.org; proxy_set_header Referer 'https://thepiratebay.org'; proxy_set_header Accept-Encoding ""; proxy_set_header CF-Connecting-IP ""; } #Recent URI location /apip/precompiled/data_top100_recent.json { proxy_pass https://apibay.org/precompiled/data_top100_recent.json; proxy_set_header Host apibay.org; proxy_set_header Referer 'https://thepiratebay.org'; proxy_set_header Accept-Encoding ""; proxy_set_header CF-Connecting-IP ""; } #Torrindex URI location /torrindexp { proxy_pass https://torrindex.net/; proxy_set_header Host torrindex.net; proxy_set_header Referer 'https://thepiratebay.org'; proxy_set_header Accept-Encoding ""; proxy_set_header CF-Connecting-IP ""; } } }`

11\. Test your config works by starting NGINX with the following command.

If you see an error, try checking inputting the error in Google for solutions. You can also check the error log by going to /usr/local/nginx/logs/.

`sudo /usr/local/nginx/sbin/nginx`

12\. You can test if it works by going to your domain in your browser or running the following curl command on your server.

`curl -H 'Host: yourdomain.com' localhost`

If it works then submit it to The Proxy Bay by going to [this Link](https://proxybay.github.io/submit.html).

13\. You should now setup an init script to load NGINX when your server starts.

You can find startup scripts for different distributions [here](https://www.nginx.com/resources/wiki/start/topics/examples/initscripts/). Be sure to change the paths to match where your NGINX installation is located

PHP Method
==========

With the PHP method, you simply need to uplaod the files to a web server that supports PHP and the PHP-Curl function

In most cases, you will just need to upload the files to your web directory and the script will work

If you don't have a web server running on your server, you will need to install it first using your distributions repositories (e.g. apt-get install nginx php php-curl)

**Update:** The script is now compatible with the April 2020 update of The Pirate Bay

[Download from Github here](https://github.com/piratebayproxy/UnblockedPiratebayClean)

Tips
====

### Find a good Web Host

Try looking for a provider that ignores DMCA requests and is not based in the USA or UK. Some hosts (even in Europe) will honour DMCA takedowns, so it's good to do your research. Try doing a Google search for keywords such as: offshore, vps, dmca.

### Use a CDN

Use a free CDN service such as [Cloudflare](https://www.cloudflare.com/) to help speed up your site and lessen the load on your server. It will also conceal the true location of your server.

**Note:** If you are using Cloudflare, you will need to add `proxy_set_header CF-Connecting-IP '';` to your Nginx config for it to work. Otherwise you might get DNS errors

### Block bots

To prevent your server IP from being blocked by The Pirate Bay, we recommend preventing search engine bots from scraping your site. If you are using Cloudflare, this can be done by either creating a firewall rule or enabling the DDOS protection.

You can create a firewall rule in Cloudflare by going to **Firewall > Firewall Rules** and selecting **Create a Firewall rule**. As the field select **Known Bots** and ensure the action is set as **Block**. You can then deploy the new rule to make it active

Note: This will prevent your site from being crawled by search engines

### Use SSL

Aside from protecting the privacy of your users, using SSL can also bypass a lot of blocks from ISP's. Therefore, it is highly recommended to use SSL for your proxy

Cloudlfare automatically provides an SSL certificate for your site so you can simply add https in front of your domain.

### Use NGINX

NGINX is the fastest and most reliable proxy method available. The PHP scripts should be used if you don't have ssh access to a server and are unable to setup NGINX

Take a look at the [NGINX Documentation](http://nginx.org/en/docs/) to further configure it to your needs

[Here](https://www.digitalocean.com/community/tutorials/how-to-optimize-nginx-configuration) is a guide on how to optimize NGINX

### Find a good Domain Registrar

We recommend [Njalla](https://njal.la/ "Njalla"), [Hover](https://www.hover.com/ "Hover"), [EasyDNS](https://www.easydns.com/ "EasyDNS"), or [NameCheap](https://www.namecheap.com/ "Namecheap").

In regards to domain names, it's recommended to avoid any domains managed by the following registries: [Donuts](http://www.donuts.domains/services/domain-names), [Radix](http://radix.website/tlds/generic.php), [CoCCA](https://nic.cx/), or any UK based domain registry such as [CentralNic](https://en.wikipedia.org/wiki/CentralNic) or [Nominet](https://icannwiki.org/Nominet). These registries are known to suspend domains without any notice or dispute process.

You can investigate the registry responsible for a particular domain TLD at [ICANNWiki](https://icannwiki.org/)

Some example domain TLD's to avoid are:

-   .pe
-   .io
-   .ly
-   .ph
-   .do
-   .cx
-   .vip
-   .fit
-   .uk

### Use WHOIS privacy on your domain name

When you register a domain name, your billing/registration information usually becomes public in the public WHOIS database. Therefore, anyone can go on a [Whois search](http://who.is/) site and lookup your domain.

Some domain names do not support WHOIS privacy and will require your contact details to be public. In that case, you can try inputting fake data. However, be aware that this might be against the terms of your domain registration. Here is [More information](http://www.hover.com/blog/why-whois-privacy-is-kind-of-a-big-deal/ "More Information").

### Get a Free Domain Name

Using [FreeDNS](https://freedns.afraid.org/), you can register a free subdomain name (e.g. subdomain.domain.com). This is free and doesn't require you to register or pay for a regular domain. However, since it's a subdomain, you don't control the name servers and cannot use it with services like Cloudflare

Another option is to get a free domain from [Freenom](http://freenom.com/). Since these are regular domains (e.g. domain.tk), you can set up name servers to point at services such as Cloudflare

### Monitor your site

Here are some free options to monitor the uptime of your site: [UpTrends](https://www.uptrends.com/) and [Uptime Robot](http://uptimerobot.com/)

### Handle DMCA requests

By operating a Pirate Bay proxy site, you will likely receive DMCA takedown requests. If you have found a hosting provider that ignores DMCA requests, this likely won't be an issue. However, sometimes your hosting provider or even domain registrar will require you to respond to a DMCA complaint.

In this case, we suggest letting the complainant know that you are operating a proxy site and don't host any infringing content.

Here is an example template:

`Hello, The site hosted at mysite.com functions as a reverse proxy that fetches content from third-party sites. You can find more information on how a reverse proxy operates here: https://en.wikipedia.org/wiki/Reverse_proxy The content you mention originates from a third party site that we do not operate, thepiratebay.org. Therefore, in order to remove any content, you will need to send a request to the original site. Once the content is removed on the original site, it will automatically be removed from proxies such as the one we operate. The original files can be found at thepiratebay.org: https://thepiratebay.org/description.php?id=99999999 We have set up this proxy site to unblock sites that are blocked on networks, mainly for anti-censorship purposes and to promote a free and open Internet. If you have any further questions feel free to contact us. Cheers,`

### Check for updates

In the case that something changes with the TPB servers or setup, you may need to update the config or code to make the proxy work. If you're using the PHP script, you can monitor the Github page. Othewise, for NGINX, check this page occasionally for updates

What next?
==========

Once you have set up your proxy and can confirm it is working, submit it to The Proxy Bay

[Submit your proxy](https://proxybay.github.io/submit.html)

[Back to top](https://proxybay.github.io/setup.html#)   [![Public Domain Mark](https://licensebuttons.net/p/mark/1.0/88x31.png)](http://creativecommons.org/publicdomain/mark/1.0/)
