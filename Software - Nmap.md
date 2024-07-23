Network Mapper is an open-source tool that's used for network discovery and security auditing

* Provides host discovery by identifying live hosts on a network
* Provides a list of open, closed, and filtered ports on a host, as well as the services that are running on them
* Can detect which OS is running on a host
* Can map out the path that packets take to reach their destination

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Nmap Scanning Engines

## Host Discovery Engine

## Port Scanning Engine

## Service and Version Detection Engine

## OS Detection Engine

## NSE Engine

## Traceroute Engine

## Output Engine

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Nmap Scanning Options

## Host Discovery

* Nmap uses a ping scan to find live hosts on a network
* When a privileged user tries to scan targets on its local network, Nmap will use ARP requests
* When a privileged user tries to scan targets outside its local network, Nmap will use ICMP echo requests, TCP ACK to port 80, TCP SYN to port 443, and ICMP timestamp request
* When an unprivileged user tries to scan targets outside its local network, Nmap will resort to a TCP Three-Way Handshake by sending SYN packets to ports 80 and 443

| Nmap Host Discovery Option | Meaning | Purpose | Command Syntax |
| --- | --- | --- | --- |
| -sL | List Scan | | |
| -sn | Ping Scan | (No port scanning) | |
| -Pn | | | |
| -PR | ARP Scan | Sends an ARP request for every address in the specified network to discover live hosts | |
| -PS | | TCP SYN/ACK | |
| -PA | | UDP | |
| -PU | | SCTP discovery | |
| -PE | | ICMP echo | |
| -PO[protocol list] | | IP Protocol Ping | |
| -n | | Never do DNS resolution | |
| -R | | Always resolve | |
| --dns-servers <dns_server>[, <dns_server>] | | Specify custom DNS servers | |
| --system-dns | | Use OS's DNS resolver | |
| --traceroute | | Trace hop path to each host | |

## Scan Techniques

| Nmap Scan Technique Option | Meaning | Purpose | Command Syntax |
| --- | --- | --- | --- |
| -sS | | TCP SYN | |
| -sT | | Connect() | |
| -sA | | ACK | |
| -sW | | Window | |
| -sM | | Maimon scans | |
| -sU | | UDP scan | |
| -sN | | TCP Null | |
| -sF | | FIN | |
| -sX | | Xmas scans | |
| --scanflags <flags> | | Customize TCP scan flags | |
| -sI <zombie_host[:probeport]> | | Idle scan | |
| -sY | | SCTP INIT scan | |
| -sZ | | COOKIE-ECHO scan | |
| -sO | | IP protocol scan | |
| -b <ftp_relay_host | | FTP bounce scan | |

## Port Specification and Scan Order Scan Options

| Nmap Port Specification and Scan Order Option | Meaning | Purpose |
| --- | --- | --- |
| -p <port_range> | | Only scan specified ports |
| --exclude-ports <port_ranges> | | Exclude the specified ports from scanning |
| -F | Fast Mode | Scan fewer ports than the default scan |
| -r | | Scan ports consecutively (Don't randomize) |
| --top-ports <port_number> | | Scan the specified number of the most common ports | 
| --port-ratio <ratio> | | Scan port s more common than the specified ratio |

## Service and Version Detection Scan 

| Nmap Service and Version Detection Scan Option | Meaning | Purpose |
| --- | --- | --- |
| -sV | | Probe open ports to determine their service and its version |
| --version-intensity <intensity_level> | | Set from 0 (light) to 9 (try all probes) |
| --version-light | | Limit to most likely probes (intensity 2) |
| --version-all | | Try every single probe (intensity 9) |
| --version-trace | | Show detailed version scan activity (for debugging) |

## Script Scan

| Nmap Script Scan Option | Meaning | Purpose |
| --- | --- | --- |
| -sC | | Equivalent to --script=default |
| --script=<lua_script>[,<lua_script>,...] | |
| --script-args=<n1=v1[,n2=v2,...]> | | Provides arguments to scripts |
| --script-args-file=<filename> | | Provide NSE scripts args in a file | 
| --script-trace | | Shows all data sent and received |
| --script-updatedb | | Update the script database |
| --script-help=<lua_script>[,<lua_script>,...] | | Show help about scripts |

## OS Detection

| Nmap OS detection Option | Meaning | Purpose |
| --- | --- | --- |
| -O | OS Detection | Enable OS detection |
| --osscan-limit | | Limit OS detection to promising targets |
| --osscan-guess | | Guess OS more aggressively |

## Timing and Performance 

| Nmap Timing and Performance Option | Meaning | Purpose |
| --- | --- | --- |
| -T<0-5> | | Set timing template (Higher is faster) |
| --min-hostgroup <size> | | |
| --max-hostgroup <size> | | |
| --min-parallelism <number_of_probes> | | |
| --max-parallelism <number_of_probes> | | |
| min-rtt-timeout <time> | | |
| max-rtt-timeout <time> | | |
| initial-rtt-timeout <time> | | |
| --max-retries <number> | | Caps number of port scan probe retransmission |
| --host-timeout <seconds> | | Give up on target after the specified time |
| --scan-delay <seconds> | | |
| --max-scan-delay <seconds> | | |
| --min-rate <seconds> | | Sends packets no slower than the specified number of seconds |
| --max-rate <seconds> | | Sends packets no faster than the specified number of seconds |


## Firewall and IDS Evasion and Spoofing 

| Nmap Firewall and IDS Evasion and Spoofing | Meaning | Purpose |
| --- | --- | --- |
| -f; --mtu <number> | | Fragment packets |
| -D <decoy>[,<decoy>]> | | Cloak a scan with decoys |
| -S <ip_address> | | Spoof source address |
| -e <iface> | | Use the specified interface |
| -g <port_number> | | Use the specified port number |
| --source-port <port_number> | | Use the specified port number |
| --proxies <url>[,<url>][,...] | | Relay connections through HTTP/SOCKS4 proxies |
| --data <hex_string> | | Append a custom payload to sent packets | 
| --data-string <string> | | Append a custom ASCII string to sent packets |
| --data-length <number> | | Append random data to sent packets |  
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
| --reason | | Display the reason a port is in a particular state |
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
