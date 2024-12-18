# StatefulSets Overview

* Ensures that even if a Pod is restarted that it'll retain its unique identity and connection to peristent storage by assigning stable and unique identifiers for each Pod (Allows Kubernetes to track which Pod is used by which client and keep them together)
* Used for stateful applications (Provides consistent and stable persistent storage associated with each Pod that persists across restarts)
* Provides ordered Pod creation, scaling, and deletion when needed
* We can specify a `PersistentVolumeClaim` template in the Pod definition and as long as this stays the same, the Pod will use the same claim and have access to the same data
* Each replica in a `StatefulSet` will have its own `PersistentVolumeClaim` so that data isn't shared across different replicas (The `PersistentVolumes` aren't deleted automatically when a replica is deleted)
* Pod names and networking will constantly follow the following pattern: `<STATEFULSET_NAME>-<ORDINAL_ID>`  
