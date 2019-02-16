## Network Config

## Mac: ifconfig (Linux: IP)

* Facts
  * List information about available network interfaces (NICs)
  * Can start/stop individual interfaces
  * ifconfig can change an interface's MAC address

* Challenges
  * Run ifconfig/ipconfig/ip and determine the name/id of your primary network interface
     * After running **ifconfig**, I discovered that there's several network interfaces on my Mac. Some of them are physical network interfaces while others are logical:
         * lo0: loopback interface. localhost 127.0.0.1
         * en0: physical network interface: ethernet
         * en1: physical network interface for WIFI
         * p2p0: virtual interface for Airdrop Mac-specific
         * fw0: FireWire network interface
         * utun0: for VPN MacOS Sierra or later
         * gif0: tunnel interface, used to tunnel IPv4 traffic to Ipv6 network and back
         * stf0: is an IPv6 to IPv4 tunnel interface, basically a bridge connection to transition IPv4 to Ipv6:  http://en.wikipedia.org/wiki/6to4

  * What is your primary interface's IP address? Is it different from your public IP? Why or why not?
     * On en0, it shows that my primary ip **inet** is 10.8.80.XYZ. Since I am connected to ethernet, my MAC is assigned a private IP address. A private IP address is assigned to every node connected to a local network. The organizations that distribute IP addresses to the world reserved a range of IP addresses for private networks. They are:
        * 192.168.0.0 - 192.168.255.255 (65536 IP addresses)
        * 172.16.0.0 - 172.31.255.255 (1,048,576)
        * 10.0.0.0 - 10.255.255.255 (16,777,216)
     * If the node from this network makes a request to a server outside of this network, your router assigns a public IP address to this node and makes a request using a node's public IP. To translate a public IP back to private or vica versa, the router uses Network address translation (NAT). As a result, a private IP address is used only inside local network and your router.

  * What is the MAC address of your primary interface?
  * Identify and understand your loopback interface



## Ping

* Facts
  * Determine the reachability of a specific destination
  * Determine the IP resolved from a specific hostname
  * Displays the latency of the network connection

* Challenges
  * What is the IP address of codepath.com?
  * What is the IP address of google.com?
  * Why would the IP address of google.com change between runs or from different locations?*

## nslookup

* Facts
  * Command line interface for DNS server queries
  * Determine IP from hostname or hosts from IP
  * Often (but not always) helpful for determining an IP's provenance

* Challenges
  * Using the IP for codepath.com from the previous, pass it to nslookup
  * Does the domain returned from nslookup match? If not, why not?

## traceroute

  * Facts
  * Determine the path to a specific destination
  * Each step in the path is called a hop
  * Determine the latency at each hop

* Challenges
  * Compare the traceroutes for codepath.com and google.com
  * How many of the hops are the same? What accounts for this?
  * Which has more hops? What accounts for the difference?

## telnet
* Facts
  * Both a protocol and a command line utility
  * Part of the early internet
  * Largely abandoned in favor of ssh
  * Still useful to determine if a port is open
* Challenges
  * What's one thing that makes telnet insecure?
  * Can you telnet to codepath.com? What port is open and why?
