Fuzz Faster U Fool is a tool that's used for web fuzzing, which is a security testing technique that's used to find vulnerabilities, hidden files, directories, and other undisclosed resources on a web server by sending large amounts of varying data to the web application and analyzing the responses

# ffuf Enumeration Techniques 

## Username Enumeration 

```Bash
ffuf -w <path_to_wordlist> -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u <target_url> -mr "<string_to_validate_valid_username>"
```

## Subdomain Enumeration

```Bash
ffuf -w <path_to_wordlist> -H "Host: FUZZ.<domain>" -u <target_url> [-fs <bytes>]
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# ffuf Brute Force Techniques

## Account Brute Force

```Bash
ffuf -w <username_wordlist>:W1,<password_wordlist>:W2 -X POST -d "username=W1&password=W2" -H "Content-Type: application/x-www-form-urlencoded" -u <target_login_page> -fc 200
```
