Netcat is a networking tool that's used for reading from and writing to network connections using TCP or UDP

* Can function as a client that connects to a listening port
* Can function as a server that listens on a port of your choice

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Netcat Options

| Netcat Option | Purpose |
| --- | --- |
| -l | Listen mode |
| -p | Specify the port number (Port numbers less than 1024 require root privileges to listen on) |
| -n | Numeric only (No resolution of hostnames via DNS) |
| -v | Verbose output |
| -vv | Very verbose output |
| -k | Keep listening after a client disconnects from the port |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Netcat Features

| Netcat Feature | Description | 
| --- | --- |
| Port Scanning | Scan for open ports on a target system |
| File Transfer | Send and receive files between two hosts |
| Chatting | Create a simple chat server between two hosts |
| Port Listening | Listen on a specific port for incoming connections |
| Banner Grabbing | Fetch information from services running on open ports |
| Proxying | Can act as a simple network proxy |

## Port Scanning 

```Bash
nc -zv <hostname> <port_range>
```

## File Transfer 

```Bash
# From sender's machine
nc -lp <port_number> < <file_to_send>

# From receiver's machine
nc <hostname> <port_number> > <file_to_receive> 
```

## Chatting

```Bash
# From listening machine
nc -lp <port_number>

# From connecting machine
nc <hostname> <port_number>
```

## Port Listening (Netcat as a Server)

```Bash
nc -lvnp <port_number>
```

## Banner Grabbing (Netcat as a Client)

```Bash
nc <hostname> <port_number>
```
