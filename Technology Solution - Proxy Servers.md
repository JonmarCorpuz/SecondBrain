A proxy server is an intermediate server that sits between end users and the web services that they want to access and forwards their web requests to the destined web server and return its reponses back to the client

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/615635613cd4216f4d4f01d5_web-browsing-with-proxy.png)

* Hides IP addresses from the web resources that the user is requesting access to
* Can block IP addresses and websites
* Can filter web content
* Can cache data to speed up common requests
* Introduces delay and a single point of failure

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Proxy Types

## Forward Proxy

A forward proxy is a type of proxy server that's placed in front of clients and forwards client requests to the intended web servers and then delivers the responses back to the requesting user 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Fordward%20Proxy.png)

* Doesn't let users go directly outside and vice-versa

## Reverse Proxy

A reverse proxy is a type of proxy server that's palced in front of web servers and retrieves resources on behalf of a client from one or more servers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Reverse%20Proxy.png)

* Doesn't let servers go directly outside and vice-versa

## HTTP Proxy

An HTTP proxy is a type of proxy server that handles HTTP requests from a client, forwards them to the destined web server, and then relays the HTTP response back to the client

## SSL Proxy

An SSL proxy is a type of proxy server that handles SSL/TLS encrypted traffic between a client and a web server

* Provides detailed inspection and management of secure HTTPS traffic by intercepting, decrypting, and inspecting the encrypted SSL/TLS traffic, and then re-encrypting and forwarding that traffic to its intended destination

## SOCKS Proxy

A SOCKS proxy is a type of proxy server that handles any type of traffic

## Transparent Proxy

A transparent proxy is a type of proxy server that intercepts normal communication at the network layer without requiring any special client configuration

## Authentication Proxy

An authentication proxy is a type of proxy server that authenticates users or devices attempting to access network resources and services, typically by validating their credentials against a centralized authentication system (Ex: *LDAP*, *etc.*)

* Sits between client devices and servers 
