Transport Layer Security is a cryptographic protocol that's designed to provide secure communication over a computer network

* More secure than SSL and is practically replacing it
* Can be used to upgrade protocols (Ex: *HTTP*, *FTP*, *SMTP*, *POP3*, *IMAP*, *etc.*) by giving them an encryption upgrade (Ex: *HTTPS*, *FTPS*, *SMTPS*, *POP3S*, *IMAPS*, *etc.*)
* Requires upgraded protocols to establish an SSL/TLS connection, which is done through an SSL Handshake
* When a user browses to a website over HTTPS, it expects that website to provide a signed certificate from a trusted Certificate Authority in order to ensure that it's communicating with the correct server 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SSL/TLS Components

## Digital Certificates

A digital certificate in SSL/TLS is an electronic document that's used to prove the ownership of a public key

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/2362c08e3a718863a1b1b56279931538.png)

* Issued by trusted Certificate Authorities and are essential for establishing secure connections over the Internet
* Automatically checked by our web browser to ensure that we're talking with the correct webserver and ensure that our communication is secure

## Master Key

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SSL Handshake

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ea654470ae699d10e9c07bd11a8320ac.png)

1. The client sends a **ClientHello** to the server to indicate its capabilities (Ex: *Supported algorithms*, *etc.*)
2. The server responds with a **ServerHello** to indicate the selected connection parameters while providing its certificate if server authentication is required along with additional information necessary to generate the master key in its **ServerKeyExchange** message before sending the **ServerHelloDone** message to indicate that it's done with the negotiation
3. The client responds back with a **ClientKeyExchange**, which contains additional information required to generate the master key, and it'll then switch to use encryption and inform the server using the **ChangeCipherSpec** message
4. The server will switch to use encryption as well and inform the client using a **ChangeCipherSpec** message

![](![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
)

# Secured Protocols Using TLS

* **HTTPS**
* **DoT** (DNS over TLS)
