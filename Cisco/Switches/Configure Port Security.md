# Configure Port Security

```Cisco IOS
enable
configure

! Enable port security
interface <interface_id>
switchport mode access
switchport port-security

! Configure the amount of allowed MAC addresses
switchport port-security maximum <number>

! Configure secure MAC addresses
switchport port-security mac-address {[mac_address]|sticky}

! Configure the violation mode
switchport port-security violation {shutdown|restrict|protect}

! Configure the aging type
switchport port-security aging type {absolute|inactivity}

! Static MAC aging
switchport port-security aging static

! Dynamic MAC aging
switchport port-security aging time <minutes>
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Enable Errdisable Recovery

```Cisco IOS
enable
configure terminal

errdisable recovery cause <errdisable_reason>
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Modify Errdisable Recovery Timer Interval

```Cisco IOS
enable
configure terminal

errdisable recovery interval <seconds>
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Modify Allowed Errdisable Recovery Attempts

```Cisco IOS
enable
configure terminal

errdisable recovery attempts <number>
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Configure DHCP Snooping

```Cisco IOS

```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Configure Dynamic ARP Inspection

```Cisco IOS

```
