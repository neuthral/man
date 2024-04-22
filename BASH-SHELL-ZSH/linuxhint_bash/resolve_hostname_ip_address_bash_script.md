





















































* Home
* Learning
* Videos
* Clothing
*
  o [Type here to search...]


   BASH_Programming


How can I resolve a hostname to an IP address in a Bash script?

3 years ago
by Karim_Buzdar
Every system in a TCP/IP network is assigned a unique identifier known as IP
address that helps to connect it with other system o the network and all over
the internet. All the websites you access on the internet also have unique IP
addresses. As it is difficult for everyone to remember the IP addresses of
these websites, the DNS system comes which helps to translate these hard to
remember IP addresses into human-readable names. With DNS, you no longer have
to remember the IP addresses. Instead, you have to just have to remember the
domain name and all done. Actually, on the backed, the DNS server takes the
hostname and resolves it to an IP address which the browser or application then
connects to.
In this article, we will explain how to resolve a hostname/domain name to an
IPv4 and IPv6 address in a Bash script. However, before proceeding towards
creating the script, let us review some of the commands that can be used to
resolve the hostname/domain name to an IP address.

Ping

Ping is the most simple and built-in tool that is available on almost all
operating systems. It is used to verify the reachability of a host in a
network. However, we can also used it to find the IP address against any
hostname/domain name. Use the following syntax to find the IP address of a
targeted hostname/domain name:
$ ping target-host

Nslookup

Nslookup is widely used to resolve the hostname to an IP address. In order to
use this command for an IP lookup, use the following syntax:
$ nslookup target-host

Host

Another command-line utility “host” can be used to find IP address against any
hostname/domain name. In order to use this command, use the following syntax:
$ host target-host

Dig

Dig is another useful command line tool that is used to query various DNS
related records. It can be used to find IP address against any hostname/domain
name. Use Dig command in the following way to find an IP address against a
specific hostname/domain name.
$ dig target-host +short

Bash script to resolve a hostname to an IP address

In order to use the bash script for an IP lookup, follow the below steps:

  1. Create a bash file using any text editor. Here I will be using the Nano
     editor to create a script named “iplookup.sh”.
     $ sudo nano script.sh


  1. Copy-paste the following lines in your script file. Note that, here in
     this script, I am specifying Google’s public DNS server for IP lookup. You
     can specify any other DNS server as per your environment.
     # Specify DNS server
     dnsserver="8.8.8.8"
     # function to get IP address
     function get_ipaddr {
       ip_address=""
         # A and AAA record for IPv4 and IPv6, respectively
         # $1 stands for first argument
       if [ -n "$1" ]; then
         hostname="${1}"
         if [ -z "query_type" ]; then
           query_type="A"
         fi
         # use host command for DNS lookup operations
         host -t ${query_type}  ${hostname} &>/dev/null ${dnsserver}
         if [ "$?" -eq "0" ]; then
           # get ip address
           ip_address="$(host -t ${query_type} ${hostname} ${dnsserver}| awk '/
     has.*address/{print $NF; exit}')"
         else
           exit 1
         fi
       else
         exit 2
       fi
     # display ip
      echo $ip_address
     }
     hostname="${1}"
     for query in "A-IPv4" "AAAA-IPv6"; do
       query_type="$(printf $query | cut -d- -f 1)"
       ipversion="$(printf $query | cut -d- -f 2)"
       address="$(get_ipaddr ${hostname})"
       if [ "$?" -eq "0" ]; then
         if [ -n "${address}" ]; then
         echo "The ${ipversion} adress of the Hostname ${hostname} is:
     $address"
         fi
       else
         echo "An error occurred"
       fi
     done
  2. Once done, use Ctrl+O and Ctrl+X to save and exit the file respectively.
  3. Now to find an IP address against a targeted hostname/domain name, run the
     script using the following syntax:
     $ ./script.sh target-host
     For instance, to resolve the IP address of “google.com”, the command would
     be:
     $ ./iplookup.sh google.com
     The output would be similar to this:
     Similarly, to resolve the IP address of “yahoo.com”, the command would be:
     $ ./iplookup.sh yahoo.com
     The output would be similar to this:
     That is all there is to it! In this article, we have learned to resolve
     the hostname to an IPv4 and IPv6 address using a bash script. We also
     learned some other command-line tools such as Ping, Nslookup, Host, and
     Dig that can be used to perform an IP lookup.



About the author


Karim Buzdar

Karim Buzdar holds a degree in telecommunication engineering and holds several
sysadmin certifications. As an IT engineer and technical author, he writes for
various web sites. He blogs at LinuxWays.
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
