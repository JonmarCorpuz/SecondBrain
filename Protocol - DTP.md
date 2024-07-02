The Dynamic Trunking Protocol is a Cisco proprietary networking protocol that's used between switches to dynamically determine their interface status (access or trunk) without manual configuration

* Allows switches to dynamically decide whether to form a trunk link based on their configurations and capabilities
* Manual configuration is recommended and DTP should be disabled on all switchports since DTP can be exploited by attackers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DTP Switchport Configuration Modes

## Desirable

A switchport in dynamic desirable mode will actively try to form a trunk with other Cisco switches

* Forms a trunk if the switchport is connected to another switchport that's configured in **trunk** mode, **dynamic desirable** mode, or **dynamic auto** mode

## Auto
