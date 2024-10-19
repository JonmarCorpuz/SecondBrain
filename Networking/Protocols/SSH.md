
* Allows you to confirm the identity of the remote webserver
* Exchanged messages are encrypted and can only be decrypted by the intended recipient
* Both sides of the SSH connection can detect any modification in the messages
* First time SSH connections require to confirm the fingerprint of the SSH server's public key to avoid MiTM attacks

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SSH Components

## SSH Server

* Listens on port 22 by default

## SSH Client

* Can authenticate using a username and password, or a private and public key

# Configuring SSH

1. Configure hostname
2. Configure DNS domain name
3. Generate RSA key pair (A key length of at least 768 bits is required for SSHv2)
4. Configure username and passwords
5. Enable SSH
6. Configure VTY lines 

