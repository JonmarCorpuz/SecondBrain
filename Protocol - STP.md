The Spanning Tree Protocol is a network protocol that ensures a loop-free topology in Ethernet networks

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# STP Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ihbjgudfafdgbhjaobjodfsggdasfhjbnou.jpg)

## Root Bridge

The root bridge is the reference point for all spanning tree calculations within a network of interconnected switches

## Designated Port

## Blocking Port

* Remains in a listening and learning state, ready to become active if the active path fails

## Root Port

The root port is the port that provides the shortest path to the root bridge

* The root bridge is elected based on a comparison of Bridge IDs, which consists of a bridge priority value and a MAC address

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# How STP Works

1. **Root bridge election**, which is the reference point for all spanning tree calculations to determine the shortest path to all other switches in the network
2. **Determination of root ports and designated ports**, which is done after the root bridge has been elected and is where non-root switches will select a root port
3. **Blocking redundant paths**, which is where STP will identify and block redundant paths in the network to prevent loops
4. **Dynamic reconfiguration**, which is when STP will dynamically reconfigure the network topology in resonse to changes by recalculating the spanning tree to ensure that there are no loops and that traffic can still flow through the network

