# Kubernetes Deployment Overview

A [Deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#:~:text=A%20Deployment%20manages%20a%20set%20of%20Pods%20to%20run%20an%20application%20workload%2C%20usually%20one%20that%20doesn%27t%20maintain%20state.) in Kubernetes manages a set of Pods to run an application workload in a declarative way

* The members of the set of Pods may change as some Pods are terminated and others are started
* All Pods run the same application because they're created using the same Pod template, which defines the Pod specification and is used by Kubernetes to keep a Pod in the state specified in the template

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Deployment Features

## Rolling Updates

## Rollbacks

## Declarative Updates

## History and Version Control

* Ensures an application remains available by gradually replaces old Pods with new ones without downtime (Rolling updates)
* Maintains application stability by allowing users to roll back to a previous version in case something goes wrong during an update
* Allows users to view and revert to previous versions by keeping track of the history of all changes made
* Ensures updates are applied gradually and safely by leveraging controlled rollouts of new versions
