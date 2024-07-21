Fuzz Faster U Fool is a tool that's used for web fuzzing, which is a security testing technique that's used to find vulnerabilities, hidden files, directories, and other undisclosed resources on a web server by sending large amounts of varying data to the web application and analyzing the responses

# Enumeration 

## Username Enumeration 

```Bash
ffuf -w <path_to_wordlist> -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u <target_url> -mr "<string_to_validate_valid_username>"
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Brute Force

## DNS Bruteforce

```Bash
ffuf -w <path_to_wordlist> -H "Host: FUZZ.<domain>" -u <target_url> [-fs <bytes>]
```
