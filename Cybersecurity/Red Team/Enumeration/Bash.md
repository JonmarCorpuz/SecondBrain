
# Identifying Live Hosts on a Network

```Bash
for i in {1..255} ;do (ping -c 1 <NETWORK_PORTION>.$i | grep "bytes from"|cut -d ' ' -f4|tr -d ':' &);done
```
