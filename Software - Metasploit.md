Metasploit is an open-source framework that's used for developing, testing, and executing exploits against software vulnerabilities

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Metasploit Modules

| Metasploit Module Type | Description |
| --- | --- |
| Auxiliary | Versatile tools for tasks other than exploitation, such as reconnaissance (Ex: *Scanners*, *Fuzzers*, *etc.*) |
| Encoders | Encodes payloads to avoid detection by antivirus software by transforming them into a different formal that's less likely to be flagged as malicious |
| Evasion | Used to bypass security defenses (Ex: *Firewalls*, *IDS*, *Antivirus software*, *etc.*) |
| Exploits | Contains the actual code to exploit a specific vulnerability |
| NOP Generator | Creates no-operation instructions to pad shellcode in order to ensure that it aligns correctly in memory to prevent buffer overflow exploits from crashing the target system |
| Paylaods | Code snippets that run on the target system after a successful exploit |
| Post-Exploitation | Used after gaining access to a target system |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Metasploit Commands

| Metasploit Command | Description |
| --- | --- |
| msfconsole | | 
| exploit | |
| history | |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Metasploit Parameters

| Metasploit Paramater  | Description | Syntax |
| --- | --- | --- |
| **RHOSTS** | Specifies the the IP address or IP addresses, IP address range, or subnet of the target host or hosts | `set RHOSTS {<ip_address>|<ip_address_range>|<subnet>}` |
| **RPORT**  | Specifies the port number on the target system that the exploit will connect to | `set RPORT <port_number>` |
| **LHOSTS** | Specifies the IP address of the machine that the target host will connect back to | `set LHOST <ip_address>` |
| **LPORT** | Specifies the port number of the machine that'll listen for incoming connections from the target | `set LPORT <port_number>` |
| **TARGET** | Specifies the target OS or software version if the exploit supports multiple targets | `set TARGET <>` |
| **PAYLOAD** | Specifies the payload to be delivered once the exploit is successful | `set PAYLOAD <path_to_payload>` |
| **USERNAME** | Specifies the username to authenticate with on the target | `set USERNAME <username>` |
| **PASSWORD** | Specifies the password to authenticate with on the target | `set PASSWORD <password>` |
| **VERBOSE** | Toggles verbose output to get more detailed information during the exploit process | `set VERBOSE {true|false}` |
| **CMD** | Specifies the command to execute on the target system | `set CMD <command>` |
