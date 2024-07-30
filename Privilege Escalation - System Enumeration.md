# System Information

```Bash
# Print system information
uname -a
```

```Bash
# Display all environmental variables and their values
env
```

```Bash
# View all running processes
ps -A

# View process tree
ps axjf

#
ps aux
```

```Bash
# List all commands that the user can run with sudo
sudo -l
```

```Bash
# Show all listening ports and established connections
netstat -a

# Show all listening ports and TCP established connections
netstat -at

# Show all listening ports and UDP established connections
netstat -au

# Show all ports that are open and ready to accept incoming connections (Listening mode)
netstat -l

# List network usage statistics by protocol
netstat -s

# List connections with the service name and PID information
netstat -tp

# Display interface statistics
netstat -i

#
netstat -ano
```

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

# Interesting Files

* /etc/issue
* /etc/passwd

* /proc/version
