# ConfigMaps Overview

* Gives us a way to decouple and inject configuration data into Pods
* Can be used to store non-sensitive data in key-value pairs and decouple this data from the Pod definitions and lifecycle (Meaning that if we delete a Pod, the ConfigMap will still exist and can be referenced in other places)
* Can be referenced either as environmental variables or as files via volume mounts
* Data inside ConfigMaps can't exceed 1 MB in size (Meaning that ConfigMaps aren't entended to store large data)
* Pods must be in the same namespace as the ConfigMaps they reference, except when fetching values directly via the Kubernetes API
* Can be set as immutable so that it can't be updated (To update, you must delete and recreate it)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
