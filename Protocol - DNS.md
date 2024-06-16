The Domain Name System protocol is a protocol that's used to translate domain names into numerical IP addresses

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DNS Hierarchy

## Root Zone

## Top-Level Domain

## Second-Level Domain

## Subdomains

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DNS Servers

## Recursive Resolver

A recursive DNS server is a server that acts as a middleman between a DNS client and a DNS nameserver

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/hjgjkhgbmvncvxbxvcbxcvbcvbcxvbxcvbvcxbvcn.png)

* The first hop in a DNS query
* After receiving a DNS query from web client, a recursive resolver will either respond with cached data or send a request to a root nameserver, followed by another request to a TLD nameserver, and then one last request to an authoritative nameserver

## Root Nameserver

The DNS root nameserver is a server that's responsible for resolving DNS queries starting from the root of the DNS hierarchy

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/asdadfdasfsadasdsafdafsdasfadfdfasdfdsfadfafsdfadfadfad.png)

* Stores the IP addresses of the authoritative nameservers for the TLDs
* All root nameservers are known to every recursive resolver
* The first hop in a recursive resolver's request for DNS records
* Replies to a recursive resolver's request by redirecting it to a TLD nameserver, based on the extension of the requested domain

## TLD Nameserver

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/qweqweqwewqeqrewrqwerwerqrqetqwerqfsdfsdfsdf.png)

## Authoritative Nameserver

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/iuyoiiottuyiuyoyiututyuytiuotututuiuoiturtuytiuoiyturutoiutituitui.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DNS Zones

## Primary Zone

## Secondary Zone

## Stub Zone

## Forward Lookup Zone

## Reverse Lookup Zone

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DNS Records

## SOA

## A

## AAAA

## CNAME

## MX

## PTR

## TXT
