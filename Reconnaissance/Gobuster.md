# Gobuster Overview

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Gobuster Modes

## DNS Mode

Enumerate subdomains
```Bash
gobuster dns -d <TARGET_DOMAIN> -w <WORDLIST>
```

## Dir Mode

* Used to find additional content on a specific domain or subdomain

```Bash
gobuster dir -u <TARGET_URL> -w <WORDLIST>
```
