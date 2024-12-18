# Volumes Overview

Volumes are directories that are accessible to the containers in a Pod

* Stores data independently of the life of a Pod (Ensures that data saved to a volume is available for the replacement Pod if the Pod it's attached to crashes or restarts)
* Used by specifying the volumes in the Pod's `.spec.volumes` and declare where to mount those volumes into containers in `.spec.containers[*].volumeMounts`

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Volume Types

## emptyDir

An emptyDir volume creates an ephemeral storage within the Pod when the Pod is assigned to a Node

* Pod-level storage (Follows the Pod's lifecycle)
* Defined at the Pod level
* Follows the lifecycle of the Pod (When a Pod is terminated, its contents are also deleted)
* The volume is initially empty
* All containers within the same Pod can read and write the same files in the emptyDir volume
* All continaers within the same Pod might mount the volume in different paths
* When a Pod is removed from a node, the data in the emptyDir volume is permanently deleted

## local

  A local volume creates a durable storage within a specific Node

* Node-level storage (Follows the Node's lifecycle)
* Requires setting node affinity to correctly schedule Pods on the correct Nodes
* Preferred over hostPath because `hostPath` may introduce many security vulnerabilities and is currently discouraged
* Requires you to specify some node affinity configuration in the `PersistentVolume` configuration when creating a local volume by using a `PersistentVolume nodeAffinity` setting (kube-scheduler knows how to assign Pods to Nodes based on the affinity constraints defined in the `PersistentVolume` configuration)
* Requires you to create a `PersistentVolumeClaims` setting as well so that Pods can use the storage
* Only supports static provisioning

## Persistent Volume

A persistent volume creates durable storage 

* Backed by multiple technologies (*Cloud Storage*, *etc.*)
* Can be statically or dynamically provisioned

## ConfigMap

A ConfigMap volume injects configuration data into Pods, without having to hard-code the data into the Pod definition

## Secret

A secret volume injects sensitive data into Pods, without having to hard-code the data into the Pod definition

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Dynamic Provisioning

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Persistent Volume Claims

A `PersistentVolumeClaim` is what actually reserves a Persistent Volume when using static provisioning or creates and reserves a Persistent Volume when using dynamic provisioning

* Claims are bound to a single `PersistentVolume`
* A `PersistentVolume` can have at most one claim bound to it (one-to-one relationship, meaning that if a Persistent Volume is bound to a claim then it cannot be bound to any other claim)
* You can set specific criteria in a claim, so that only Persistent Volumes that match those criterias are considered for binds

## Reclamation Policies

* Reclamation policies can be either `Retain`, `Delete`, or `Recycle` (Although Recycle is deprecated)

### Retain

### Delete

### Recycle

## Access Modes

* Persistent Volume access mode can be either `ReadWriteOnce`, `ReadOnlyMany`, `ReadWriteMany`, `ReadWriteOncePod`

### ReadWriteOnce

The Persistent Volume can be mounted as read-write by a single Node, which can then be used by any number of Pods within that Node

### ReadOnlyMany

The Persistent Volume can be mounted as read-only by many Nodes, which can then be used by any number of Pods within those Nodes

### ReadWriteMany

The Persistent Volume can be mounted as read-write by many Nodes, which can then be used by any number of Pods within those Nodes

### ReadWriteOncePod

The Persistent Volume can be mounted  as read-write by a single Pod, which can then be used by any number of Pods within that Node

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Volume Provisioning Types

## Static Provisioning

* Works on a best-effort match-based on access mode and size requests
* Might not be fulfilled depending on what's available

## Dynamic Provisioning

* Provisions storage dynamically when PersistentVolumeClaims are created
* If the backend supports what's requested, it'll always be fulfilled
