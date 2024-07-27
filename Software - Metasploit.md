Metasploit is an open-source framework that's used for developing, testing, and executing exploits against software vulnerabilities

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Metasploit Database

The Metasploit database allows you to store and manage information about the targets your working on

* Stores information about the hosts you have discovered (Ex: *IP addresses*, *Hostnames*, *OSes*, *Open ports*, *etc.*)
* Keeps track of the services running on each host (Ex: *Service names*, *Service versions*, *etc.*)
* Logs the vulnerabilities that were discovered on each host 

| Metasploit Database Feature | Description |
| --- | --- |
| Workspaces | Allows you to create separate environments within the Metasploit database to organize testing activities |

**Launching the Metasploit Database**
```Bash
# You'll first need to start the PostgreSQL database
sudo systemctl start postgresql

# Then initialize the Metasploit Database
msfdb_init
```

Manage Worksapces
```Bash
# Add a workspace
workspace {-a|--add} <workspace_name>

# Rename a workspace
workspace {-r|--rename} <old_workspace_name> <new_workspace_name>

# Delete a workspace 
workspace {-d|-delete} <workspace_name>

# Delete all workspaces
workspace {-D|--delete-all}
```

**Troubleshoot**
```Bash
# Launch the Metasploit console
msfconsole

# Check the database status
db_status

# List all available workspace
workspace

# List all available workspace in more detail
workspace {-v|--list-verbose}

# Search for a workspace
workspace {-s|--search} <workspace_name>
```

```Bash
hosts [-R]
services [-S <service_name>]
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Metasploit Commands

| Basic Metasploit Command | Description |
| --- | --- |
| msfconsole | Launches the Metasploit Framework console | 
| msfupdate | Updates the Metasploit Framework to the latest version |
| msfdb init | Initializes the Metasploit database |
| msfvenom | Generates and outputs various types of shellcode, executable, files, and payloads |

| Exploitation Metasploit Command | Description |
| --- | --- |
| exploit | Runs the selected exploit module |
| check | Checks if the target is vulnerable to the selected exploit |
| background | Backgrounds the current session | 
| sessions -l | Lists all active sessions |
| sessions -i <session_id> | Interacts with a specified session |
| sessions -k <session_id> | Kills the specified session |

| Module Interaction Metasploit Command | Description |
| --- | --- |
| search <keyword> | Searches for modules related to the keyword |
| use <module> | Selects a module to use |
| info | Disaplys information about the selected module |
| show options | Displays the options available for the selected module |
| show payloads | Lists the payloads that are compatible with the selected exploit |
| show {exploits|auxiliary|encoders|nops|post} | Lists all modules for the specified type |

| Configuration Metasploit Command | Description |
| --- | --- |
| set <parameter> <value> | Sets a value for the specified parameter in the selected module |
| unset <parameter> | Unsets the value of a specified parameter in the selected module |
| setg <parameter> <value> | Sets a global value for the specified option |
| unsetg <parameter> | Unsets the value of a global parameter |
| show advanced | Displays advanced options for the selected module |
| set target <index> | Sets the target index for the exploit |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Metasploit Parameters

| Metasploit Paramater  | Description | Syntax |
| --- | --- | --- |
| **RHOSTS** | Specifies the the IP address or IP addresses, IP address range, or subnet of the target host or hosts | set RHOSTS {<ip_address>|<ip_address_range>|<subnet>} |
| **RPORT**  | Specifies the port number on the target system that the exploit will connect to | set RPORT <port_number> |
| **LHOSTS** | Specifies the IP address of the machine that the target host will connect back to | set LHOST <ip_address> |
| **LPORT** | Specifies the port number of the machine that'll listen for incoming connections from the target | set LPORT <port_number> |
| **TARGET** | Specifies the target OS or software version if the exploit supports multiple targets | set TARGET <> |
| **PAYLOAD** | Specifies the payload to be delivered once the exploit is successful | set PAYLOAD <path_to_payload> |
| **USERNAME** | Specifies the username to authenticate with on the target | set USERNAME <username> |
| **PASSWORD** | Specifies the password to authenticate with on the target | set PASSWORD <password> |
| **VERBOSE** | Toggles verbose output to get more detailed information during the exploit process | set VERBOSE {true|false} |
| **CMD** | Specifies the command to execute on the target system | set CMD <command> |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Metasploit Keyboard Shortcuts

| Metasploit Keyboard Shortcut | Description |
| --- | --- |
| CTRL + Z | Background a session |
| CTRL + C | Kill a session |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Metasploit Shell Types

## Command Shell

The command shell provides a basic command-line interface to interact with the target host

* Provides direct access to the command prompt of the target
* Limited functionality

## Meterpreter Shell

The Meterpreter shell is a more advanced and versatile shell that runs in memory

* Runs in memory (RAM) on the target system and acts as an agent, meaning that it's not directly installed on the target system and doesn't write itself to the disk on the target, making it seen as a process and not have a file that can be detected on the target system
* Provides extensive port-exploitation capabilities
* Provides an encrypted communication (TLS) channel between the local host and the target host to avoid being detected
* Extensible via scripts and modules
* Provides filesystem navigation, process management, and privilege escalation capabilities

| Meterpreter Command | Description |
| --- | --- | 
| background | Backgrounds the current session |
| exit | Terminates the Meterpreter session |
| guid | Gets the session GUID |
| getpid | Shows the current PID |
| getuid | Shows the user that Meterpreter is running as |
| irb | Opens an interactive Ruby shell on the current session |
| load | Loads one or more Meterpreter extensions |
| migrate <pid> | Migrates Meterpreter to the specified process |
| run | Executes a Meterpreter script or Post-Exploitation module |
| sessions | Quickly switch to another session |
| edit | Will allow you to edit a file |
| search | Searches for files |
| upload | Uploads a file or directory |
| download | Downloads a file or directory |
| portfwd | Forwards a local port to a remote service |
| route | Allows you to view and modify the routing table |
| clearev | Clears the event logs |
| execute | Executes a command |
| shell | Drops into a system command shell |
| sysinfo | Gets information about the remote system |
| idletime | Returns the number of seconds the remote user has been idle |
| keyscan_dump | Dumps the keystroke buffer |
| keyscan_start | Starts capturing keystrokes |
| keyscan_stop | Stops capturing keystrokes |
| screenshare | Watches the remote user's desktop in real-time |
| screenshot | Grabs a screenshot of the interactive desktop |
| record_mic | Records audio from the default microphone for the specified amount of seconds |
| webcam_chat | Starts a video chat |
| webcam_list | Lists webcams |
| webcam_snap | Takes a screenshot from the specified webcam |
| webcam_stream | Plays a video stream from the specified webcam | 
| getsystem | Attempts to elevate your privileges to that of local system |
| hashdump | Dumps the content of the SAM database |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Metasploit Tools

## msfvenom

msfvenom is a tool within the Metasploit framework that's used to generate payloads, shellcode, and executable files

* Allows users to create custom payloads and encode them into many different formats for many different target systems
* Allows access to all the payloads that are available in the Metasploit framework

| msfvenom Option | Description |
| --- | --- |
| -l payloads | |
| --list formats | Lists all supported output formats |
| -p <path_to_payload> | Specifies the payload to use |
| -f <output_format> | Specifies the output format |
| -a <architecture> | Specifies the architecture |
| --platform <platform> | Specifies the platform | 
| -o <output_file> | Specifies the output file to write the payload to |
| -e <encoder> | Specifies the encoder to use |
| -i <number_of_iterations> | Specifies the number of times to encode the payload |
| -b <bad_characters> | Specifies characters to avoid in the payload |
| LHOST=<ip_address> | Specifies the local host IP address for reverse payloads |
| LPORT=<port_number> | Specifies the local port number for reverse payloads |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Metasploit Modules

| Metasploit Module Type | Description |
| --- | --- |
| Auxiliary | Versatile tools for tasks other than exploitation, such as reconnaissance (Ex: *Scanners*, *Fuzzers*, *etc.*) |
| Encoders | Encodes payloads to avoid detection by antivirus software by transforming them into a different formal that's less likely to be flagged as malicious |
| Evasion | Used to bypass security defenses (Ex: *Firewalls*, *IDS*, *Antivirus software*, *etc.*) |
| Exploits | Contains the actual code to exploit a specific vulnerability |
| NOP Generator | Creates no-operation instructions to pad shellcode in order to ensure that it aligns correctly in memory to prevent buffer overflow exploits from crashing the target system |
| Payloads | Code snippets that run on the target system after a successful exploit |
| Post-Exploitation | Used after gaining access to a target system |

## Auxiliary Modules

## Encoder Modules

## Exploit Modules

| Metasploit Exploit Module | Description |
| --- | --- |
| exploit/multi/handler | |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
