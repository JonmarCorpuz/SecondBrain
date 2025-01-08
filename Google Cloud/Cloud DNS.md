# Cloud DNS Overview

Google's Cloud DNS is a managed DNS service provided by GCP that allows users to host their DNS zones and manage DNS records for their domain names without having to run their own DNS servers

* Designed to automatically scale so customers can have as many domains as they want without concern for scaling the underlying infrastructure
* Supports DNS forwarding (Allows DNS queries to be passed to an on-premises DNS server if you're using Cloud VPN or Interconnect)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud DNS Zones

* When a DNS zone is created, NS and SOA records are added automatically

## Public Zone

* Accessible from the Internet
* Provides name servers that respond to queries from any source

## Private Zone

* Provides name servers respond only to queries that originate from resources in the same projects as the zone

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DNSSEC

* Provides strong authentication of clients communicating with DNS services
* Designed to prevent spoofind and cache poisoning

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud DNS Record Parameters

## TTL

* Specifies how long the record can live in a cache (The period of time DNS resolvers should cache the data before querying for the value again)
* Performs lookup operations mapping domain names to IP addresses

## Routing Policy

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Transactions
