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

# Find Files

```Bash
# Find all directories or files containing the specified string
find / -type {d|f} -name <string> 2>/dev/null

# Find all directories or files containing the specified file permissions
find / -type {d|f} -perm {<file_permissions>|<subject>=<permission>} 2>/dev/null

# Find all directories or files owned by the specified user
find / -type {d|f} -user <username> 2>/dev/null

# Find all directories or files that were modified in the last specified time period
find / -type {d|f} -mtime <days> 2>/dev/null

# Find all directories or files that were accessed in the last specified days
find / -type {d|f} -atime <days> 2>/dev/null

# Find all directories or files that were changed within the specified time
find / -type {d|f} -cmin -<minutes> 2>/dev/null

# Find all directories or files that were accessed within the specified time
find / -type {d|f} -amin -<minutes> 2>/dev/null

# Find all directories or files with the specified size
find / -type {d|f} -size {[+]|[-]}<size> 2>/dev/null
```
