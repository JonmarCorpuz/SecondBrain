# Toleration Overview

A toleration is a property that you can set on Pods to allow them to be scheduled on Nodes with certain taints

* Enables Pods to run on Nodes with certain taints despite the restrictions imposed by the taints by permitting Pods to ignore specific taints

![](https://github.com/JonmarCorpuz/LetsLearn/blob/main/Assets/Whitespace.png)

# Toleration Components

## Key

A key is a label that the toleration is addressing

## Value

A value is a label value that the toleration is addressing

## Operator

An operator specifies how to match the value of the toleration and the taint

| Toleration Operator | Description |
| --- | --- |
| `Equal` | Requires an exact match |
| `Exists` | The key must simply exist, regardless of the value |

## Effect

An effect 

| Toleration Effect | Description |
| --- | --- |
| `NoSchedule` | |
| `PreferNoSchedule` | |
| `NoExecute` | |

## TolerationSeconds
