
| Gobuster Short Option | Gobuster Long Option | Purpose |
| --- | --- | --- |
| -u | **--url** | Specifies the target URL to scan |
| -w | **--wordlist** | Specifies the path to the wordlist file containing directories or files to brute-force |
| -t | **--threads** | Specifies the number of concurrent threads (requests) to use at the same time (10 by default) |
| -k | **--insecure** | Allows insecure SSL connections when using HTTPS |
| -x | **--extensions** | Specifies the file extensions to search for |
| -r | **--recursive** | Performs recursive directory brute-forcing |
| -e | **--expanded** | Displays the full URLs |
| -l | **--wildcard** | Force continued operation when a wildcard is found |
| -s | **--statuscodes** | Specifies the comma-separated list of status codes of responses to consider valid |
| -a | **--useragent** | Specifies a custom user-agent string |
| -H | **--header** | Specifies HTTP headers |
| -b | **--cookies** | Specifies cookies to use for the requests |
| -v | **--verbose** | Verbose output |

# Brute-Force  

```Bash
gobuster -u <target_url> -w <path_to_wordlist> dir
```
