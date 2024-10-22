Unicast Reverse Path Forwarding is a security feature that ensures that incoming packets have a valid source address that matches the network's routing table

* Helps prevent IP address spoofing

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# uRPF Modes

## Strict Mode

* Checks if the source IP address of incoming packets is reachable via the exact interface they arrived on

## Loose Mode

* Checks if the source IP address of incoming packets is reachable via any interface
