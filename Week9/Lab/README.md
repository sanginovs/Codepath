## Network Config

## Mac: ifconfig (Linux: IP)

* Facts
  * List information about available network interfaces (NICs)
  * Can start/stop individual interfaces
  * ifconfig can change an interface's MAC address

* Challenges
  * Run ifconfig/ipconfig/ip and determine the name/id of your primary network interface
  * What is your primary interface's IP address? Is it different from your public IP? Why or why not?
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


