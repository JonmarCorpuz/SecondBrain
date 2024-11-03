# Configure Lookup Zones

## Configure Forward Lookup Zone

```Bash
zone "<DOMAIN NAME>" {
  type <master|slave|stub|forward|hint>
  file "<FORWARD LOOKUP ZONE CONFIGURATION FILE PATH>"
}
```

## Configure Reverse Lookup Zone

```Bash
zone "<NETWORK ADDRESS>.in-addr.arpa" {
  type <master|slave|stub|forward|hint>
  file "<REVERSE LOOKUP ZONE CONFIGURATION FILE PATH>"
}
```
![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Bind9%20Zones.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Configure Forward Lookup Zones

```Bash
@             IN      SOA   <DOMAIN NAME>. root.localhost. (
                        0          ; se = serial number
                        60         ; ref = refresh
                        60         ; ret = update retry
                        60         ; ex = expiry
                        60         ; min = minimum
                        )

@             IN      NS      <DOMAIN NAME>.

@             IN      A       <HOST IP ADDRESS>
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Bind9%20Forward%20Zones.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Configure Reverse Lookup Zones

```Bash
@             IN      SOA   <DOMAIN NAME>. root.localhost. (
                        0          ; se = serial number
                        60         ; ref = refresh
                        60         ; ret = update retry
                        60         ; ex = expiry
                        60         ; min = minimum
                        )

@             IN      NS      <DOMAIN NAME>.

@             IN      PTR     <FQDN>
[...]
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Bind9%20Reverse%20Lookup%20Zone.png)
