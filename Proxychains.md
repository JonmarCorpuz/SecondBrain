# Proxychains Overview

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/oghsidfhgsdihfgsdhfgaidofhdioas.PNG)

* Routes your internet traffic through multiple proxy servers, making it difficult to trace back to your original IP address
* Allows for increased flexibility and security when browsing the internet through possible integration with Tor, SOCKS, and HTTP proxies

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# proxychains-ng

## Install and Configure proxychains-ng

Install proxychains-ng
```Bash
sudo apt -y install proxychains4
```

Add your proxies in the [ProxyList] section in the /etc/proxychains4.conf proxychains configuration file
```text
[ProxyList]
#socks4    127.0.0.1    9050
{tor|socks4|http}    <PROXY_ADDRESS>    <PORT_NUMBER>    [USERNAME]    [PASSWORD]
```

## proxychains-ng Proxychain Types

### Dynamic Proxychain

A dynamic proxychain attemps to use the proxies in the listed order and if one fails, it'll simply skip it and move on to the next one

* Provides reliability

### Strict Proxychain

A strict proxychain attemps to use the proxies in the listed order and if one fails then the entire connection fails

* Provides predictability

### Round-Robin Proxychain

A round-robin proxychain is used circularly to distribute the connection amongst the provided proxies 

* Each connection request goes to the next one in the liust, and once it reaches the end, it starts over again at the beginning
* Provides load balancing

### Random Proxychain

A random proxychain selects proxies for each connection in a random order

* Provides a unique path through each listed proxy
* Provides highrt anonymity
