# Identify Live Hosts on a Network

## ping

```Bash
for i in {1..255} ;do (ping -c 1 <NETWORK_PORTION>.$i | grep "bytes from"|cut -d ' ' -f4|tr -d ':' &);done
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Expose Possible Sensitive Information

## .bash_history

```Bash
cat ~/.bash_history
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Enumerate Files Owned by Root

## find

```Bash
find / -perm -4000 2> /dev/null
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Query DNS Information

## dig

Domain Information Groper is a CLI tool that's used for querying DNS servers to retrieve information about DNS records

```Bash
dig [<DNS_SERVER_IP>] <DOMAIN> {<RECORD_TYPE>}
```
