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

### Dynamic Chain



### Strict Chain

### Round-Robin Chain

### Random Chain
