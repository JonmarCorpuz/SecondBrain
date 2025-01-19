# Taint Overview

A taint is a property you can set on a Node that marks it to repel certain Pods

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

# Setting a Taint

Set a taint on a Node with the specified key and value
```Bash
kubectl taint nodes NODE_NAME KEY=VALUE:EFFECT
```

