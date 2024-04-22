






















































* Home
* Learning
* Videos
* Subscribe
*
  o [Type here to search...]


   Linux_Commands


30 Nmap Examples

1 year ago
by David_Adams
This tutorial shows 30 Nmap usage examples, related to subjects which were
explained in previous articles published at Linux Hint.
Examples include from host discovery to vulnerability audit, network
diagnostics and more. Most of them were produced in real or simulated scenarios
making them real valuable for network administrators or students.
Implementing the examples described in this tutorial is pretty simple, as
running a command.
All subjects covered in this article include:

* Nmap_ping_sweep_examples
* Defining_ports_to_scan_with_Nmap
* Nmap_NULL_scan_example
* Nmap_FIN_scans
* Xmas_Scan_with_Nmap
* Updating_Nmap_NSE_(Nmap_Scripting_Engine)
* Get_devices_OS,_workgroup,_domain,_device_name_over_SMB_protocol
* Finding_Zombie_for_Idle_Scan
* Executing_an_Idle_scan
* Scanning_ranges_for_vulnerabilities
* Scanning_for_smb-vuln-ms08-067_vulnerability
* Brute_force_against_SSH_with_Nmap_NSE

NOTE: Last update of this tutorial was in October 2021.

Ping Sweep with Nmap

Ping sweep is a technique used to discover live hosts within a network or
range.
Nmap ping sweep examples were deeply explained at Nmap_ping_sweep.
To execute ping sweep using Nmap, you need to implement the -sP or -sn options,
which instruct Nmap to avoid port scan after discovery.
In the following example, a wildcard is implemented to instruct Nmap to
discover all online C class network hosts or devices.
nmap -sP 192.168.0.*
In the previous example, Nmap only confirms the host is alive without scanning
the target. The opposite would be the -Pn option, which instructs Nmap to start
the scan without checking if the host is alive.
nmap -Pn 192.168.0.2-240
At the end, it will print the total number of live hosts as shown in the
screenshot below.
As you can see, from 239 scanned addresses, 10 were online devices.

Defining Ports with Nmap Using the -p Flag

Defining a port to scan with Nmap is pretty easy, just add the flag -p followed
by the port, or ports separated by commas as shown in the screenshot below.
nmap -p 80,22,139,21,23 192.168.0.*
In the following example the port range is defined with a hyphen to scan Linux
Hint port range from 22 to 80:
nmap -p 22-80 linuxhint.com
The following example shows Nmap scanning two different port ranges separated
by commas.
nmap -p 20-80,100-600 192.168.0.3-14
There are many ways to specify ports to scan using Nmap. We have published a
tutorial showing different ways to scan_all_ports_using_Nmap. One of these
methods to scan all ports on a target requires the implementation of the -p-
option as shown in the following example.
nmap -p- linuxhint.com
The final example of this section shows an ARP scan executed through Nping,
part of the Nmap suite, which inherited Nmap flags to customize ARP scans.
nping --arp-type ARP 192.168.1.100-104
As you see, Nping identifies every IP with the proper MAC address.

Nmap FIN Scan Example

The next example is an aggressive FIN scan against a port range.
nmap -sF -T4 192.168.0.3-14
This is an example of an insane FIN scan against a single device:
nmap -sF -T5 192.168.0.3
To end FIN scan examples, letâs do a less aggressive scan against a
metasploit virtual device.
nmap -sF -T2 192.168.56.1

Nmap NULL Scan Example

The following example shows a NULL scan against linuxhint.com port 80. Remember
Nmap NULL, Xmas and FIN scans canât distinguish between open and filtered
ports, in many scenarios.
sudo nmap -v -sN -p 80 linuxhint.com
Now, letâs try an insane scan against a router.
nmap -sN -T5 192.168.56.1
Usually NULL, Xmas and FIN scans canât distinguish between filtered and open
ports when the port is open, the next example includes the -sV option to help
it distinguish, but adding this option results in a less stealthy scan:
nmap -sN -T2 -sV -p80,22,21,139  192.168.56.1

Nmap Xmas Scan Example

The Xmas scan with Nmap was deeply explained in_this_article.
Below, you can see an example of an aggressive Xmas scan against the target
192.168.56.1.
nmap -sX -T4 192.168.56.1
Now, a less aggressive Xmas scan against port 80 and 22.
nmap -sX -T2 -p80,22 192.168.0.3
The following example is similar to the above, but includes level 2 verbosity:
nmap -sX -T2 -v2  -p80,22 192.168.0.3
As you can see, the last output reveals additional information than the
previous output.

Update Scripts Database

Nmap contains a suite of scripts with additional functionalities. This suite is
known as Nmap NSE.
Before using the Nmap NSE update the database by running the command below.
nmap --script-updatedb
Once updated, you can proceed with Nmap NSE.

Get Devices OS, Workgroup, Domain, Device Name Over SMB Protocol

The following example uses the NSE script âscript smb-os-discovery (https://
nmap.org/nsedoc/scripts/smb-os-discovery.html) against whole last 2 octets of
the network 172.31.X.X
nmap -p 445 --script smb-os-discovery 172.31.*.*
As you can see in the screenshot below, the first possible vulnerable target
was one.
The screenshot below reveals a new vulnerable target was found.
Two Windows XP computers were found, great candidates for a Idle scan which
will be explained later below in this tutorial.

Finding Zombie for Idle Scan

The following example shows how to search for a zombie candidate to execute an
Idle scan by scanning the last octet of the 10.100.100.X network by using the
NSE script ipidseq (https://nmap.org/nsedoc/scripts/ipidseq.html).
nmap -p80 --script ipidseq 10.100.100.*
Another way to find potential zombie candidates for Idle scans:
nmap -Pn -O -v 192.168.56.102

Executing an Idle Scan

Running an Idle scan using a candidate found in the previous step.
nmap -Pn  -sI 10.100.100.108 -p80,21,22,443 172.31.124.141
Another Idle scan using the same candidate against a gateway:
nmap -Pn -sI 172.31.100.108 -p80,21,22,443 172.31.99.2
An Idle scan against the FTP of a router using a Windows 98 virtualized device:
nmap -Pn -sI  192.168.56.102 -p21 192.168.0.1

Scanning Ranges for Vulnerabilities

The following example shows the wildcard implementation to scan a whole
octetâs range.
nmap -v --script vuln  172.31.100.*
Below, you can see an output sample.

Scanning for smb-vuln-ms08-067 Vulnerability

The following scan uses the NSE script smb-vuln-ms08-067 (https://nmap.org/
nsedoc/scripts/smb-vuln-ms08-067.html) to search for a remote execution
vulnerability on two last octets of the network by implementing the wildcard
twice.
nmap -p445 --script smb-vuln-ms08-067 172.31.*.*

Brute Force Against SSH with Nmap NSE

Nmap NSE (Nmap Scripting Engine) was deeply covered in the Nmap_NSE_tutorial.
This example shows how to use the Nmap scripting engine to bruteforce the
target ssh.
For this attack we will use the NSE script named ssh-brute.nse.
nmap --script ssh-brute.nse 192.168.0.3
As you can see, NSE will read a list including username and password pairs. Of
course, you can provide NSE your custom list.

Conclusion

I hope all Nmap examples shown in this tutorial were useful to you. Nmap is
probably the best network scanner in the market. Despite faster solutions, like
Mass Scan, Nmap leads with multiple features and additional scripts. You also
can write your own NSE scripts to use with Nmap.
As you can see, despite its power, Nmap can be easily executed by any Linux
level user. Deep Nmap learning is very advantageous for anyone dealing with
networking.
Thank you for reading this tutorial showing 30 Nmap examples. Keep following
Linux Hint for additional Linux tips and tutorials.
nmap


About the author


David Adams

David Adams is a System Admin and writer that is focused on open source
technologies, security software, and computer systems.
View_all_posts

RELATED LINUX HINT POSTS


* Linux_LDAP_Commands
* How_to_Print_the_Usernames_of_Currently_Logged-In_Users_in_Linux
* How_to_Create_an_Ext4_File_System_with_Mkfs
* Ldapsearch_Command
* Understanding_Sudo_and_Su:_Syntax_and_Functions
* How_to_Detach_the_Screen_Session
* How_to_Copy_the_Files_with_SSH_and_PIPE_to_Remote_Host

Linux Hint LLC, [email protected]
1309 S Mary Ave Suite 210, Sunnyvale, CA 94087
 Privacy_Policy and Terms_of_Use
