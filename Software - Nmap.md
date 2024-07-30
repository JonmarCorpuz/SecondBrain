Network Mapper is an open-source tool that's used for network discovery and security auditing

* Provides host discovery by identifying live hosts on a network
* Provides a list of open, closed, and filtered ports on a host, as well as the services that are running on them
* Can detect which OS is running on a host
* Can map out the path that packets take to reach their destination

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Nmap Port States

| Nmap Port State | Description | 
| --- | --- |
| Open | Indicates that a service is listening on the specified port |
| Closed | Indicates that no service is listening on the specified port (The port can still be accessible) |
| Filtered | Nmap cannot determine if the port is open or closed because the port isn't accessible (Usually due to a firewall preventing Nmap from reaching that port or that the responses are blocked from reaching Nmap's host |
| Unfiltered | Nmap cannot determine if the port is open or closed, although the port is accessible |
| Open/Filtered | Nmap cannot determine whether the port is open or filtered |
| Closed/Filtered | Nmap cannot decide whether a port is closed or filtered |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Nmap Scanning Engines

## Host Discovery Engine

## Port Scanning Engine

## Service and Version Detection Engine

## OS Detection Engine

## NSE Engine

* A script is a piece of code that doesn't need to be compiled, meaning that it'll remain in its original human-readable form and doesn't need to be converted to machine language)
* Nmap provides support for scripts using the Lua language
* NSE is a Lua interpreter that allows Nmap to execute Nmap scripts written in Lua
* Some scripts can belong to more than one category

| Nmap Script Category | Description |
| --- | --- |
| default | |
| auth | Authentication related scripts |
| broadcast | Discover hosts by sending broadcast messages |
| brute | |
| discovery | Retrieve accessible information (Ex: *Database tables*, *DNS names*, *etc.*) |
| dos | |
| exploit | |
| fuzzer | |
| intrusive | | 
| malware | |
| safe | |
| version | |
| vuln | |

## Traceroute Engine

## Output Engine

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Nmap Scanning Options

```Bash
nmap [options] {<target_ip>|<domain_name>|<target_ip_range>|<network_address><prefix_length>}
```

* `nmap --interactive` can be used to spawn a special shell-like interface

## Host Discovery

* Nmap uses a ping scan to find live hosts on a network
* When a privileged user tries to scan targets on its local network, Nmap will use ARP requests
* When a privileged user tries to scan targets outside its local network, Nmap will use ICMP echo requests, TCP ACK to port 80, TCP SYN to port 443, and ICMP timestamp request
* When an unprivileged user tries to scan targets outside its local network, Nmap will resort to a TCP Three-Way Handshake by sending SYN packets to ports 80 and 443
* By default, Nmap will look up online hosts and will use reverse-DNS lookup

| Nmap Host Discovery Option | Meaning | Purpose | Command Syntax |
| --- | --- | --- | --- |
| -sL | List Scan | | |
| -sn | Ping Scan | Host discovery only (No port scanning) | |
| -Pn | | | |
| -PR | ARP Scan | Sends an ARP request for every address in the specified network to discover live hosts | |
| -PS[<port_number>] | | TCP SYN Ping scan | |
| -PA[<port_number>] | | TCP ACK Ping scan | |
| -PU[<port_number>] | | UDP Ping scan | |
| -PE | | Tells Nmap to use ICMP Echo to discover live hosts | |
| -PP | | Tells Nmap to use ICMP Timestamp to discover live hosts | |
| -PM | | Tells Nmap to use ICMP Address Mask to discover live hosts | |
| -PO[protocol list] | | IP Protocol Ping | |
| -n | | No DNS lookup | |
| -R | | Reverse-DNS lookup for all hosts regardless if they're online or offline | |
| --dns-servers <dns_server>[, <dns_server>] | | Specify custom DNS servers | |
| --system-dns | | Use OS's DNS resolver | |
| --traceroute | | Trace hop path to each host (Starts with a packet of high TTL and keeps decreasing it) | |

## Scan Techniques

| Nmap Scan Technique Option | Meaning | Purpose | Command Syntax |
| --- | --- | --- | --- |
| -sS | | TCP SYN | |
| -sT | | TCP Connect Scan | |
| -sA | | ACK | |
| -sW | | Window | |
| -sM | | Maimon scans | |
| -sU | | UDP scan | |
| -sN | | TCP Null | |
| -sF | | FIN | |
| -sX | | Xmas scans | |
| --scanflags <tcp_flags> | | Customize TCP scan | |
| -sI <zombie_host[:probeport]> | | Idle scan | |
| -sY | | SCTP INIT scan | |
| -sZ | | COOKIE-ECHO scan | |
| -sO | | IP protocol scan | |
| -b <ftp_relay_host | | FTP bounce scan | |

## Port Specification and Scan Order Scan Options

| Nmap Port Specification and Scan Order Option | Meaning | Purpose |
| --- | --- | --- |
| -p {<port_range>|<port_list>} | | Only scan specified ports |
| -p- | | Scan all 65535 ports |
| --exclude-ports <port_ranges> | | Exclude the specified ports from scanning |
| -F | Fast Mode | Scan fewer ports than the default scan (From the 1000 most common ports to the 100 most common ports) |
| -r | | Scan ports consecutively and in order (Don't randomize) |
| --source-port <port_number> | | Specifies the source port |
| --top-ports <port_number> | | Scan the specified number of the most common ports | 
| --port-ratio <ratio> | | Scan port s more common than the specified ratio |

## Service and Version Detection Scan 

| Nmap Service and Version Detection Scan Option | Meaning | Purpose |
| --- | --- | --- |
| -sV | | Probe open ports to determine their service and its version (Forces Nmap to proceed with the TCP Three-Way Handshake and establish the connection, which is necessary because Nmap can't discover the version without establishing a connection fully and communicating with the listening service) |
| --version-intensity <0-9> | | Set from 0 (light) to 9 (try all probes) |
| --version-light | | Limit to most likely probes (intensity 2) |
| --version-all | | Try every single probe (intensity 9) |
| --version-trace | | Show detailed version scan activity (for debugging) |

## Script Scan

| Nmap Script Scan Option | Meaning | Purpose |
| --- | --- | --- |
| -sC | | Equivalent to --script=default |
| --script=<script_name>[,<script_name>,...] | |
| --script-args=<n1=v1[,n2=v2,...]> | | Provides arguments to scripts |
| --script-args-file=<filename> | | Provide NSE scripts args in a file | 
| --script-trace | | Shows all data sent and received |
| --script-updatedb | | Update the script database |
| --script-help=<lua_script>[,<lua_script>,...] | | Show help about scripts |

## OS Detection

| Nmap OS detection Option | Meaning | Purpose |
| --- | --- | --- |
| -O | OS Detection | Enable OS detection (Nmap needs to find at least one open and one closed port on the target to make a reliable guess, and the guest OS fingerpints might get distorted) |
| --osscan-limit | | Limit OS detection to promising targets |
| --osscan-guess | | Guess OS more aggressively |

## Timing and Performance 

| Nmap Timing and Performance Option | Meaning | Purpose |
| --- | --- | --- |
| -T<0-5> | | Set timing template (Higher is faster) |
| --min-hostgroup <size> | | |
| --max-hostgroup <size> | | |
| --min-parallelism <number_of_probes> | | Ensures that Nmap maintains the specified number of probes in parallel and that they're related to host discover and open ports |
| --max-parallelism <number_of_probes> | | |
| min-rtt-timeout <time> | | |
| max-rtt-timeout <time> | | |
| initial-rtt-timeout <time> | | |
| --max-retries <number> | | Caps number of port scan probe retransmission |
| --host-timeout <seconds> | | Give up on target after the specified time |
| --scan-delay <seconds> | | |
| --max-scan-delay <seconds> | | |
| --min-rate <number> | | Ensures that Nmap isn't sending a number of packets lower than the specified amount per second |
| --max-rate <number> | | Ensures that Nmap isn't sending a number of packets higher than the specified amount per second |

## Firewall and IDS Evasion and Spoofing 

| Nmap Firewall and IDS Evasion and Spoofing | Meaning | Purpose |
| --- | --- | --- |
| -f | | Fragments packets into 8 byte-fragments |
| -ff | | Fragments packets into 16 byte-fragments |
| -f; --mtu <number> | | Fragment packets to the specified number |
| -D <decoy>[,<decoy>]> | | Cloak a scan with decoys |
| -S <ip_address> | | Spoof source address |
| -e <iface> | | Use the specified interface |
| -g <port_number> | | Use the specified port number |
| --source-port <port_number> | | Use the specified port number |
| --proxies <url>[,<url>][,...] | | Relay connections through HTTP/SOCKS4 proxies |
| --data <hex_string> | | Append a custom payload to sent packets | 
| --data-string <string> | | Append a custom ASCII string to sent packets |
| --data-length <number> | | Increase the size of packets to the specified number of bytes |  
| --ip-options <options> | | Send packets with specified IP options |
| --ttl <value> | | Set IP TTL field |
| --spoof-mac <mac_address>/<prefix>/<vendor_name> | | Spoof your MAC address |
| --badsum | | Send packets with a bogus TCP/UDP/SCTP checksum | 

## Output 

| Nmap Output Option | Meaning | Purpose |
| --- | --- | --- |
| -oN <filename> | | Output scan in normal format to the given filename |
| -oX <filename> | | Output scan in XML format to the given filename |
| -oS <filename> | | Output scan in skript kiddie format to the given filename |
| -oG <filename> | | Output scan in grepable format to the given filename |
| -oA <basename> | | Output in the three major formats at once (normal, XML, and grepable) |
| -v | | Increase verbosity level |
| -vv | | Increase verbosity level even more |
| -d | | Increase debugging level |
| -dd | | Increase debugging level even more |
| --reason | | Displays why Nmap concluded that the system is up or a particular port is open |
| --open | | Only show open (or possibly open) ports |
| --packet-trace | | Show all packets sent and received |
| --iflist | | Print host interfaces and routes (For debugging) | 
| --append-output | | |
| --resume <filename> | | Resume an aborted scan |
| --stylesheet {<path>|<url>} | | XSL stylesheet to transform XML output to HTML | 
| --webxml | | Reference stylesheet from Nmap.org for more portable XML | 
| --no-stylesheet | | Prevent associating of XSL stylesheet with XML output |

## Misc 

| Nmap Misc Option | Purpose | Meaning | 
| --- | --- | --- |
| -6 | | Enable IPv6 scanning |
| -A | | Enable OS detection, version detection, script scanning, and traceroute |
| --datadir <directory_name> | | Specify custom Nmap data file location | 
| --send-eth | | Send using raw ethernet frames |
| --send-ip | | Send using raw IP packets |
| --privileged | | Assume that the user is fully privileged |
| --unprivileged | | Assume that the user lacks raw socket privileges |
| -V | | Print version number |
| -h | | Print the help summary page |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Nmap Scanning Techniques

## ARP Scan

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/f0ce4cd34b827f529255c5c73bb909d1.png)

* If a host sends back an ARP Reply, then the host is active

## ICMP Ping Scan

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/25fb5fd5d2009cf69d7aae40e8fde2ec.png)

* If a host sends back an ICMP Reply, then the host is active

## TCP SYN Ping Scan

**Privileged TCP SYN Nmap ping scan**
![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/168d48701c5f872cf1930e08b32bcd6f.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/fe642b2fafb70cbaa2531d2c41d6cddb1.png)

* If a port replies back with a SYN/ACK, then the port is open
* If a port replies back with a RST, then the port is closed
* Privileged users don't need to complete the TCP Three-Way Handshake even if the port is open
* Nmap tears down the connection once it receives a response from the host, which decreases the chances of the scan being logged since it didn't establish a TCP connection

**Unprivileged TCP SYN Nmap ping scan**
![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/23e7f481f78de8d3e89ef845b747002d.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/fe642b2fafb70cbaa2531d2c41d6cddb2.png)

* Unprivileged users have to complete the TCP Three-Way Handshake even if the port is open

## TCP ACK Ping Scan

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/db5ab44a8c700c4ab0603e85e456040d.png)

* Must be a privileged user to accomplish this scan (Attempting this with an unprivileged user will result in an attempt for the TCP Three-Way Handshake)
* An active target will respond with a RST flag because the TCP packet with the ACK flag isn't part of any ongoing connection
* Useful to help map out firewall rules

## TCP Connect Scan

TCP Connect scan works by completing the TCP Three-Way Handshake in order to determine if a TCP port is open and then tearing that connection down right away

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/514972cd54b3f58c83f951978ea9183e.png)

* The only scan that's possible for non privileged users to discover open TCP ports

## TCP Null Scan

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/04b178a9cf7048c21256988b8b2343e3.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/224e01a913a1ce7b0fb2b9290ff5e1c8.png)

* Requires root privileges
* A TCP packet with no flags set won't trigger any response when it reaches an open port, which means that a lack of reply in a Null scan indicates that either the port is open or a firewall is blocking the packet
* If a port is closed, it'll reply to a Null flag with a RST packet, which indicates that the port is closed (Note that some firewalls may drop the traffic without sending an RST reply)
* Can be efficient when scanning a target behind a stateless firewall, since it'll usually check if the incoming packet has the SYN flag set to detect a connection attempt

## TCP FIN Scan

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/78eb3d6ba158542f2b3223184b032e64.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/74dc07da7351a5a7f258948ec59efccc.png)

* If a port is closed, it'll reply to a FIN flag with a RST packet, which indicates that the port is closed (Note that some firewalls may drop the traffic without sending an RST reply)
* Can be efficient when scanning a target behind a stateless firewall, since it'll usually check if the incoming packet has the SYN flag set to detect a connection attempt

## TCP Xmas Scan

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/7d28b756aed3b6eb72faf98d6974776c.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/4304eacbc3db1af21657f285bc16ebce.png)

* If a port is closed, it'll reply to a Xmas scan with a RST packet, which indicates that the port is closed (Note that some firewalls may drop the traffic without sending an RST reply)
* Can be efficient when scanning a target behind a stateless firewall, since it'll usually check if the incoming packet has the SYN flag set to detect a connection attempt

## TCP Maimon Scan

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/8ca5e5e0f6e0a1843cebe11b5b0785b3.png)

* The FIN and ACK bits are set
* Most target systems respond with an RST regardless of whether the TCP port is open

## TCP Window Scan

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/5118dcb424d429376f09bf2f85db5bce.png)

* Almost the same as the ACK scan but it examines the TCP Window field of the RST packets returned, which can reveal an open port on specific systems
* Sometimes you have to repeat a TCP Window scan against a target that's behind a firewall in order to get more information
* Useful to help map out firewall rules

## UDP Ping Scan

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/1b827ef60c39619e281c4ca51a6d57b6.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/f927563f4778092ced3ef7afa67cece3.png)

* Open UDP ports aren't expected to send a reply
* Closed UDP ports are expected to send back an ICMP Port Unreachable packet reply, which reveals that the host is online

## Spoofed Scan

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/45b982d501fd26deb2b381059b16f80c.png)

* The target will respond to the incoming packets by sending the replies to the destination IP address that we spoofed
* To figure out which ports are open, the attacker needs to monitor the network traffic to analyze the replies that are sent back to the destination address
* In general, you expect to specify the network interface using **-e** and to explicitly disable ping scan using **-Pn**
* You can also spoof you MAC address if you're in the same Ethernet (802.3) network or WiFi (802.11)
* Spoofing only works in a minimal number of cases where certain conditions are met

## Decoy Scan

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/754fc455556a424ca83f512665beaf7d.png)

* Decoy scanning involves making the scan appear to be coming from many IP addresses so that the attacker's IP address would be lost among them

## Idle Scan

* Requires an idle system to be connected to the network that you can use to communicate with (If the idle host is busy, then all the returned IP IDs would be useless)
* Nmap will make each probe appear as if it's coming from the idle host, then it'll check for indicators whether the idle host received any response to the spoofed probe, which can be accomplished by checking the IP ID value in the IP header of the packets

1. Trigger the idle host to respond so that you can record the current IP ID on the idle host
![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/a93e181f0effe000554a8b307448bbb2.png)

2. Send a spoofed SYN packet to a TCP port on the target to make it appear as if it was coming from the idle host
![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/8e28bf940936ddbc2367b193ea3550b8.png)
![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/2b0de492e2154a30760852e07cebae0e.png)

3. Trigger the idle machine again to respond so that you can compare the new IP ID with the one received earlier (If the difference is 1, it means the port on the target is closed or filtered, but if the difference is two, it means that the port on the target is open)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Nmap Scan Timing

| Nmap Scan Timing | Meaning | Description |
| --- | --- | --- |
| 0 | Paranoid | |
| 1 | Sneaky | |
| 2 | Polite | |
| 3 | Normal | |
| 4 | Aggressive | |
| 5 | Insane | |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Nmap Service Detection Scan Intensity Levels

| Nmap Scan Intensity Level | Description |
| --- | --- | --- |
| 0 | Quick but may miss some services and only includes the most likely probes |
| 1 | Includes slightly more probes than level 0 |
| 2 | Includes more probes to provide a better balance between speed and accuracy |
| 3 | Good balance between thoroughness and time consumption (The default level) |
| 4 | More probes than the default and is more likely to identify obscure services but takes more time |
| 5 | Further increases the number of probes to provide a more comprehensive version detection | 
| 6 | Adds even more probes to the scan but is more time-consuming |
| 7 | Very thorough since it uses almost all available probes but can be very slow |
| 8 | Uses all probes to provide maximum thoroughness | 
| 9 | All probes are used to ensure the most comprehensive detection but at the cost of scan time and potential false positives |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
