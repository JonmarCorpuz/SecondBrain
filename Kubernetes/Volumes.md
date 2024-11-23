# Volumes Overview

Volumes are directories that are accessible to the containers in a Pod

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

# Mounting Volumes

```YAML
volumeMounts:
  - name: <VOLUME_NAME>
    path: <PATH_TO_VOLUME>
```
