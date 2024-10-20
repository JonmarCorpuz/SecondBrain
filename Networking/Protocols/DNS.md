# DNS Overview

The Domain Name System protocol is a protocol that's used to translate human-readable domain names into numerical IP addresses

* Standard DNS queries and responses use port UDP 53 (Port TCP 53 is used for DNS messages that are greater than 512 bytes)
* Devices will save a DNS server's responses to a local DNS cache, which prevents them from querying the DNS server every single time they want to access a same destination

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DNS Structure

## Root Domain

The root domain serves as the starting point for all DNS resolutions and is denoted by a single dot (Ex: *www.example.com.*, *victim.local.*. *etc.*)

* The highest level in the hierarchical DNS structure

## Top-Level Domain

A TLD is the last segment of a domain name and serves to identify the type and location of websites and online resources

* TLDs are managed by domain name registries 

### Genertic Top-Level Domain

A gTLD is a type of TLD that's not tied to any specific country or territory (Ex: *.com*, *.org*, *.net*, *.info*, *etc.*)

### Country Code Top-Level Domain

A ccTLD is a type of TLD that's reserved for a specific country or territory (Ex: *.us*, *.ca*, *.uk*, *.jp*. *etc.*)

## Second-Level Domain

A SLD represents the unique identifier within a domain name 

* The segment of a domain that appears directly to the left of the TLD (Ex: *example in example.com*, *etc.*)
* A SLD must be unique within their TLD

## Subdomains

A subdomain is a subdivision of a domain 

* Enables the creation of separate or distinct branches within a domain name hierarchy
* Helps organize content or services into logical sections under a single domain name

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DNS Servers

## Recursive Resolver

A recursive DNS server is a type of DNS server that acts as a middleman between a DNS client and a DNS nameserver

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/hjgjkhgbmvncvxbxvcbxcvbcvbcxvbxcvbvcxbvcn.png)

* The first hop in a DNS query
* After receiving a DNS query from web client, a recursive resolver will either respond with cached data or send a request to a root nameserver, followed by another request to a TLD nameserver, and then one last request to an authoritative nameserver

## Root Nameserver

The DNS root nameserver is a type of DNS server that's responsible for resolving DNS queries starting from the root of the DNS hierarchy

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/asdadfdasfsadasdsafdafsdasfadfdfasdfdsfadfafsdfadfadfad.png)

* Stores the IP addresses of the authoritative nameservers for the TLDs
* All root nameservers are known to every recursive resolver
* The first hop in a recursive resolver's request for DNS records
* Replies to a recursive resolver's request by redirecting it to a TLD nameserver, based on the extension of the requested domain

## TLD Nameserver

A TLD nameserver is a type of DNS server that's responsible for managing DNS records and responding to queries for domain names within a specific TLD

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/qweqweqwewqeqrewrqwerwerqrqetqwerqfsdfsdfsdf.png)

* Maintains information for all the domain names that share a common domain extension
* Responds to a recursive resolver's request by redirecting it to the authoritative nameserver for that domain

## Authoritative Nameserver

An authoritative nameserver is a type of DNS server that contains information specific to the domain name it serves

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/iuyoiiottuyiuyoyiututyuytiuotututuiuoiturtuytiuoiyturutoiutituitui.png)

* Provides a recursive resolver with the information for the DNS queries that it's requesting (Ex: *IP address*, *Alias domain*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DNS Zones

## Primary Zone

## Secondary Zone

## Stub Zone

## Forward Lookup Zone

## Reverse Lookup Zone

## Root Zone

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DNS Records

## SOA

## A

## AAAA

## CNAME

## MX

## PTR

## TXT

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DNS Resolution

## Recursive DNS Resolution



## Iterative DNS Resolution



## Caching DNS Resolution



## Reverse DNS Resolution
