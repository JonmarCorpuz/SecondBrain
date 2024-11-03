```Cisco IOS
enable
configure terminal

spanning-tree mode {pvst+|rapid-pvst|mst}
```

```Cisco IOS
enable 
configure terminal

spannig-tree vlan <vlan_id> root {primary|secondary|<bridge priority>}
```

# STP Toolkit

```Cisco IOS
enable
configure terminal

spannig-tree portfast
```

```Cisco IOS
enable
configure terminal

spanning-tree portfast default
```

```Cisco IOS
enable
configure terminal

spannig-tree bpduguard default
```

```Cisco IOS
enable
configure terminal

spanning-tree bpduguard enable
```

# RSTP

```Cisco IOS
enable
configure terminal

interface <interface_id>
spanning-tree link-type {point-to-point|shared}
```
