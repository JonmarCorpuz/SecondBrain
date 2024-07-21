# Enumeration

## Username Enumeration 

```Bash
ffuf -w <path_to_wordlist> -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u http://MACHINE_IP/customers/signup -mr "username already exists"
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Brute Force

## DNS Bruteforce

```Bash
ffuf -w <path_to_wordlist> -H "Host: FUZZ.<domain>" -u <target_url> [-fs <bytes>]
```
