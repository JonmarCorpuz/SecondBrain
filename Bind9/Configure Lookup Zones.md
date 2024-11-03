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
