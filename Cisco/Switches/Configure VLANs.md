# Data VLAN

```Cisco IOS
enable
configure

interface <interface_id>
switchport trunk encapsulation dot1q
switchport mode trunk
switchport trunk allowed vlan {all|none|<vlan_id>,[vlan_id],[vlan_range],[...]|except <vlan_id>,[vlan_id],[vlan_range],[...]|add <vlan_id>,[vlan_id],[vlan_range],[...]|remove <vlan_id>,[vlan_id],[vlan_range],[...]}
switchport trunk native vlan <vlan_id>
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Voice VLAN

```Cisco IOS
enable
configure terminal

switchport mode access
switchport voice vlan <vlan_id>
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# 

```Cisco IOS
enable
configure terminal

switchport mode dynamic {auto|desirable}
```
