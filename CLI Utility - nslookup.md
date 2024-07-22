Name Server Lookup is a network administration CLI tool that's used to query the DNS to obtain domain name or IP address mapping information

* Used to diagnose DNS issues and for obtaining detailed information about DNS records

# Query DNS Records

Return all the IP addresses used by the target domain
```Bash
nslookup -type={A|AAAA} <domain_name> [dns_server_address]
```

Return all the mail servers used by the target domain
```Bash
nslookup -type=MX <domain_name>
```
