# Hydra Overview 

Hydra is a tool that's used for conducting brute-force attacks on various network services

# Brute Force Credentials 

## SSH
```Bash
#
hydra {-l <USER>|-L <FILE>} {-p <PASSWORD|-P <WORDLIST>} ssh://<TARGET_IP>[:PORT]
```

## FTP

```Bash
#
hydra {-l <USER>|-L <FILE>} {-p <PASSWORD|-P <WORDLIST>} ftp://<TARGET_IP>[:PORT]
```

# Additional Options
