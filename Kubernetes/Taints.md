# Taint Overview

A taint is a property you can set on a Node that marks it to repel certain Pods unless they have a corresponding toleration

* Affects how Pods are scheduled onto Nodes
* Works together with tolerations
* Ensures that certain Nodes are reserved for specific worloads (*Nodes with special hardware meant for only special applications*, *etc.*)
* Maintains Node security by restricting which Pods can run on a Node (Useful for Nodes that handle sensitive data or critical operations)
* Controls Pod placement

![](https://github.com/JonmarCorpuz/LetsLearn/blob/main/Assets/Whitespace.png)

# Taint Components

## Key

A key is a label that's associated with the taint

## Value

A value is the label value corresponding to the key

## Effect

The effect defines what happens to Pods that don't tolerate the taint

| Effect | Description |
| --- | --- |
| `NoSchedule` | Pods that don't tolerate this taint are not scheduled on the Node |
| `PreferNoSchedule` | Kubernetes will try to avoid scheduling Pods that don't tolerate this taint on the Node (Not guaranteed) |
| `NoExecute` | Pods that don't tolerate this taint will be evicted if they're already running on the Node and will not be scheduled on the Node in the future |

![](https://github.com/JonmarCorpuz/LetsLearn/blob/main/Assets/Whitespace.png)

# Untainted Node

An untainted Node refers to a Node that doesn't have any taints applied to them

* Doesn't restrict the scheduling of Pods based on taints and tolerations
* Assuming that that there are no other scheduling restrictions in place, any Pod can be scheduled on untainted Nodes
* Nodes are untainted by default when added to a Kubernetes cluster (They'll accept any Pods unless the Pods themselves specify Node selection criteria that prevent them from being scheduled on certain Nodes)

# Configuring Taints

Adding a taint
```Bash
kubectl taint nodes NODE_NAME KEY=VALUE:EFFECT
```

Removing a taint
```Bash
kubectl taint nodes NODE_NAME KEY=VALUE:EFFECT-
```
