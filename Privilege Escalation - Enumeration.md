| Privilege Escalation Enumeration Command | Description | Purpose |
| --- | --- | --- |
| hostname | Returns the hostname of the target machine | May provide information about the target system's role |
| uname -a | Prints system information | May provide additional detail about the kernel used by the target system |
| ps | Displays the currently running processes | May provide additional information about |
| env | Displays environmental variables |
| sudo -l | Lists all the commands that the current user can run using sudo |
| id | | |
| history | | |
| ifconfig | | |
| netstat | | |
| find | | |

| Privilege Escalation Enumeration File | Description | Purpose |
| --- | --- | --- |
| /proc/version | Contains information on the kernel version and additional data (Ex: *Whether a compiler is installed*, *etc.*) | May provide information about the target system processes |
| /etc/issue | Contains information about the operating system | May provide additional information about the target system |
| /etc/passwd |  |  |
