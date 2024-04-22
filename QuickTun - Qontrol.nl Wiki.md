QuickTun is probably the simplest VPN tunnel software ever, yet it's very secure. It relies on the [NaCl](http://wiki.ucis.nl/NaCl "NaCl") encryption library by [D. J. Bernstein](http://cr.yp.to/).

QuickTun uses the [curve25519xsalsa20poly1305 crypto-box](http://nacl.cace-project.eu/box.html) functionality of the NaCl library for secure public-key encryption.

And that's about all QuickTun does; encrypting and sending data. No fancy features which would only lead to bloating the binary. In fact, QuickTun itself has only a few hundred lines of pure C code, making it dead simple to maintain, analyze, debug and fix.

-   [1 Installing QuickTun on Debian/Ubuntu Linux](http://wiki.ucis.nl/QuickTun#Installing_QuickTun_on_Debian.2FUbuntu_Linux)
-   [2 Installing QuickTun on Linux or BSD](http://wiki.ucis.nl/QuickTun#Installing_QuickTun_on_Linux_or_BSD)
-   [3 Configuring QuickTun on Linux (non Debian/Ubuntu)](http://wiki.ucis.nl/QuickTun#Configuring_QuickTun_on_Linux_.28non_Debian.2FUbuntu.29)
-   [4 QuickTun configuration options](http://wiki.ucis.nl/QuickTun#QuickTun_configuration_options)
-   [5 QuickTun on Windows](http://wiki.ucis.nl/QuickTun#QuickTun_on_Windows)
-   [6 Protocol](http://wiki.ucis.nl/QuickTun#Protocol)
-   [7 QuickTun Linux kernel module](http://wiki.ucis.nl/QuickTun#QuickTun_Linux_kernel_module)
-   [8 Links](http://wiki.ucis.nl/QuickTun#Links)
-   [9 Third party packages](http://wiki.ucis.nl/QuickTun#Third_party_packages)
-   [10 Thanks to...](http://wiki.ucis.nl/QuickTun#Thanks_to...)
-   [11 Support QuickTun](http://wiki.ucis.nl/QuickTun#Support_QuickTun)

## Installing QuickTun on Debian/Ubuntu Linux

A precompiled package is available in the UCIS.nl apt repository:

```
wget -q http://apt.ucis.nl/IvoSmits.asc -O- | apt-key add -
echo "deb http://apt.ucis.nl/ current ucis" >> /etc/apt/sources.list
apt-get update
apt-get install quicktun

```

If you prefer to compile QuickTun yourself, or if your platform is not covered in our repository, you can follow the steps below (Installing QuickTun on Linux), and either manually copy the files (from out/ and debian/static/etc/) to their destination, or install the generated debian package (dpkg -i out/quicktun\*.deb).

The tunnel can then be configured in the /etc/network/interfaces file:

```
auto tun0
iface tun0 inet static
       address 192.168.77.1
       pointopoint 192.168.77.2
       netmask 255.255.255.255
       qt_tun_mode 1
       qt_protocol nacltai
       qt_remote_address 1.2.3.4
       qt_local_address 9.8.7.6
       qt_private_key_file <LOCAL-SECRET-KEY-FILE>
       qt_public_key <REMOTE-PUBLIC-KEY>

```

See below for supported configuration options. Please note that all options are written in lower case and are prefixed with qt\_. The interface name is taken from the 'iface' entry.

## Installing QuickTun on Linux or BSD

Building QuickTun is very simple. Just run the following commands:

```
wget http://oss.ucis.nl/quicktun/src/quicktun.tgz -O- | tar -xvz
cd quicktun*
./build.sh

```

This command will first download and build the NaCl cryptography engine - this will take some time. When done, the out/ directory will contain a few binaries:

-   libquicktun.raw - dynamically loadable library which implements the 'raw' unencrypted quicktun protocol
-   quicktun.combined - the one you'll probably want to use, has all supported protocols and can be used 'stand alone'
-   quicktun.debian - a binary targeting Debian based systems, for optimal integration with Debian's network configuration files
-   quicktun.keypair - can be used to generate a public/secret key pair
-   quicktun.nacl0 - stand alone binary implementing the nacl0 protocol (NaCl encryption without nonce)
-   quicktun.nacltai - stand alone binary implementing the nacltai protocol (NaCl encryption with nonce)
-   quicktun.raw - stand alone binary implementing the 'raw' unencrypted protocol
-   quicktun-\*.tgz - compressed tarball containing the sourcecode and build scripts, for distribution
-   quicktun-\*.deb - a Debian binary package, only generated on Debian based systems

You'll most likely want to use the out/quicktun.combined and out/quicktun.keypair executables. You may want to copy them to /usr/sbin.

## Configuring QuickTun on Linux (non Debian/Ubuntu)

QuickTun configuration is usually stored in a shell script like this:

```
#!/bin/sh
export TUN_MODE=1
export PROTOCOL=nacltai
export REMOTE_ADDRESS=ipaddress-of-remote-end
export LOCAL_ADDRESS=ipaddress-of-local-end
export PRIVATE_KEY=private-key-of-local-end
export PUBLIC_KEY=public-key-of-remote-end
/usr/sbin/quicktun

```

Make sure that the script is not publicly readable because it contains the secret key: chmod 700 will do! To start the VPN tunnel, simply run the shellscript. You can also run the script using some service supervisor (daemon tools, supervisord).

Alternatively all configuration can be specified on the command line like this:

```
/usr/sbin/quicktun -c PROTOCOL nacltai -c TUN_MODE 1 -c PRIVATE_KEY_FILE secret.key -c PUBLIC_KEY public-key-of-remote-end

```

## QuickTun configuration options

-   INTERFACE - interface name (non-debian systems only)
-   TUN\_MODE - set to 1 to operate in tun (IP), unset or 0 (recent versions only) for tap (Ethernet) mode
-   USE\_PI - set to 1 to include packet information header in wire packets, must be set on both sides if used; set to 2 to automatically add the packet information header for cross-platform compatibility (also compatible with USE\_PI=0), some (BSD) kernels need USE\_PI to be enabled for IPv6 support
-   REMOTE\_ADDRESS - IP address or hostname of the remote end (use 0.0.0.0 for a floating/dynamic remote endpoint)
-   LOCAL\_ADDRESS - IP address or hostname of the local end, optional
-   LOCAL\_PORT - local UDP port, optional, defaults to 2998
-   REMOTE\_PORT - remote UDP port, optional, defaults to LOCAL\_PORT
-   REMOTE\_FLOAT - allows the remote address and port to change when properly encrypted packets are received
-   TUN\_UP\_SCRIPT - run specified command or script after the tunnel device has been opened
-   SETUID - drop privileges and change user and group IDs to specified username after setting up the tunnel
-   nacl0, nacltai and salty (encrypted) protocols only:
    -   PRIVATE\_KEY - local secret key in hexadecimal form (not needed for raw protocol)
    -   PUBLIC\_KEY - remote public key in hexadecimal form (not needed for raw protocol)
    -   PRIVATE\_KEY\_FILE - file containing local secret key in binary or hexadecimal form (not needed for raw protocol)
-   nacltai (encrypted) protocol only:
    -   TIME\_WINDOW - allowed time window for first received packet in seconds (positive number allows packets from history)
-   Combined binary only (quicktun.debian and quicktun.combined executables, Debian based systems):
    -   PROTOCOL - the protocol to use, one of "raw", "nacl0" and "nacltai"
-   Debian /etc/network/interfaces only:
    -   NO\_PRECREATE - set to 1 to run QuickTun as root and not use a persistent tunnel device, unset otherwise

## QuickTun on Windows

A pure C# implementation of QuickTun and the required cryptography code is included in the [Virtual Network Environment](http://wiki.ucis.nl/VNE "VNE"). This code can run on both, Windows and Linux systems, and provide full VPN functionality, in addition to many other features. The [DNRouter](http://wiki.ucis.nl/VNE/DNRouter "VNE/DNRouter") software uses this library to provide QuickTun support.

A stand-alone tunnel application is also available on [http://oss.ucis.nl/vne/quicktun/](http://oss.ucis.nl/vne/quicktun/). Download all files, rename example.xml to quicktun.xml and edit it according to your needs. Then run UCIS.QuickTun.exe. Note that you will have to create/install a tun/tap device before running the software. You can do this either by installing OpenVPN or tinc, or by downloading all files from [http://oss.ucis.nl/vne/tuntapwin/](http://oss.ucis.nl/vne/tuntapwin/) and running addtap.bat.

The configuration file has the following elements:

-   <tunnel> - the document root element
    -   -   <tuntap> - this element defines the tun/tap interface to connect to the host
            -   @ifname - this attribute specifies the interface name (it works for both Windows and Linux!)
            -   @type - either "tap" or "tun", on Windows only tap is supported
            -   @dhcpserver - (windows only, optional) enables automatic host IP configuration, this specifies the address of the virtual DHCP server
            -   @hostip - (windows only, optional) specifies the IP address to configure on the host (requires @dhcpserver to be set)
            -   @netmask - (windows only, optional) the network mask for host IP configuration (requires @dhcpserver and @hostip to be set)
        -   <quicktun> - defines the QuickTun VPN tunnel
            -   @local - (optional) specifies the local tunnel in IP:PORT format, eg 10.0.0.1:2997
            -   @remote - (optional) specifies the remote tunnel in IP:PORT format, eg 10.0.0.2:2997
                -   Note that at least one of local and remote must be specified!
            -   @protocol - specifies the QuickTun cryptographic protocol to use (currently supported are "raw", "nacl0", "nacltai" and "salty")
            -   <secretkey> - (nacl0, nacltai and salty protocols only) this element contains the secret key of the local end (eg <secretkey>THE\_KEY\_GOES\_HERE\_IN\_HEXADECIMAL</secretkey>)
            -   <publickey> - (nacl0, nacltai and salty protocols only) this element contains the public key of the remote end

Note that <xxx> indicates an XML element. @xxx indicates an attribute to the XML element. See also the example configuration file.

## Protocol

QuickTun supports four different protocols:

| Protocol name | Security | Overhead | Remarks | Details |
| --- | --- | --- | --- | --- |
| raw | None | 0 bytes | Compatible with VirtualBox UDPTunnel | The IP or ethernet packet as it was read from the device is sent directly in an UDP packet |
| nacl0 | Very weak | 16 bytes |  | The IP or ethernet packet is encrypted using the curve25519xsalsa20poly1305\_box function, with the nonce set to all zero, the first 16 all-zero bytes of the result are stripped off, the rest is sent in an UDP packet |
| nacltai | Secure | 32 bytes |  | The IP or ethernet packet is encrypted using the curve25519xsalsa20poly1305\_box function, with the nonce being <7bytes=0><1byte=local\_pub\_key>remote\_pub\_key?1:0><16bytes:tai64an\_packed\_timestamp>, the tai64an\_packed\_timestamp is copied to the beginning of the encrypted buffer (to the area that is normally all zero), the entire buffer is sent (crypto adds 32 bytes of overhead) |
| salty | Secure with PFS | 20 bytes + control packets | Requires at least one endpoint to have a fixed address | The IP or ethernet packet is encrypted using the curve25519xsalsa20poly1305\_box function, with temporary keys and nonces which are periodically regenerated and exchanged; this protocol provides Perfect Forward Secrecy and does not depend on clock synchronization for replay protection; the current implementation does not work well if both endpoints are floating |

## QuickTun Linux kernel module

Matthias is working on a Linux kernel module providing QuickTun functionality: [http://git.universe-factory.net/modquicktun/](http://git.universe-factory.net/modquicktun/)

## Links

-   Mercurial repository: [http://oss.ucis.nl/hg/quicktun/](http://oss.ucis.nl/hg/quicktun/)
-   GitHub project: [https://github.com/UCIS/QuickTun](https://github.com/UCIS/QuickTun) (git repository: [https://github.com/UCIS/QuickTun.git](https://github.com/UCIS/QuickTun.git))
-   BitBucket project: [https://bitbucket.org/IvoSmits/quicktun](https://bitbucket.org/IvoSmits/quicktun)
-   Debian/Ubuntu packages: [http://apt.ucis.nl/packages/](http://apt.ucis.nl/packages/)
-   Sourcecode archives: [http://oss.ucis.nl/quicktun/src/](http://oss.ucis.nl/quicktun/src/) (latest: [http://oss.ucis.nl/quicktun/src/quicktun.tgz](http://oss.ucis.nl/quicktun/src/quicktun.tgz))

## Third party packages

-   ArchLinux: [http://aur.archlinux.org/packages.php?ID=44278](http://aur.archlinux.org/packages.php?ID=44278)
-   FreeBSD (beta): [http://hg.dereckson.be/freebsd-ports/src/tip/net/quicktun/](http://hg.dereckson.be/freebsd-ports/src/tip/net/quicktun/)
-   OpenWRT: [https://dev.openwrt.org/browser/packages/net/quicktun](https://dev.openwrt.org/browser/packages/net/quicktun)

## Thanks to...

-   somerandomnick, some anonymous person who introduced me to the NaCl cryptography library and encouraged me to extend [TunTapIO](http://wiki.ucis.nl/Projects/Software/TunTapIO "Projects/Software/TunTapIO")
-   Daniel Dickinson <daniel@cshore.neomailbox.net>, who contributed [some fixes](http://oss.ucis.nl/hg/quicktun/rev/51c6d2fc712f)
-   Everyone who uses QuickTun and has suggested improvements, reported bugs, supported me while fixing them, etc.

## Support QuickTun

You can support QuickTun by spreading the word, reporting bugs, suggesting fixes, porting it to other platforms, packaging it for other distributions, and more. If you would like to make a financial donation, you may send some money to my PayPal account Ivo@UFO-Net.nl, via bitcoin to [13LJt54w2VD9WZQgBG6hGdmny26wg4jqEH](bitcoin:13LJt54w2VD9WZQgBG6hGdmny26wg4jqEH?message=QuickTun%20donation) or ask me for my address (cash) or bank account (IBAN, send me an e-mail).