# Configure EtherChannel Load Balance

```Cisco IOS
enable
configure terminal

port-channel load-balance {dst-ip|dst-mac|src-dst-ip|src-dst-mac|src-ip|src-mac}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Configure PAgP EtherChannel

```Cisco IOS
enable
configure terminal

interface range <interface_range>
channel-group <group_id> mode {auto|desirable}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Configure LACP EtherChannel

```Cisco IOS
enable
configure terminal

interface range <interface_range>
channel-group <group_id> mode {active|passive}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Configure Static EtherChannel

```Cisco IOS
enable
configure terminal

interface range <interface_range>
channel-group <group_id> mode on
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Configure the EtherChannel Negotiation Protocol

```Cisco IOS
enable
configure

interface range <interface_range>
channel-protocol {lacp|pagp}
```
