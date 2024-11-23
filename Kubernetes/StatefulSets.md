# StatefulSets Overview

* Help manage applications more effectively by maintaining stable identities for each Pod, which ensures that even if a Pod is restarted that it'll retain its unique identity and connection to peristent storage
* Provide a stable and unique network identity for each Pod created as part of the `StatefulSet`
* Provide consistent and stable persistent storage associated with each Pod, also across restarts
* Provides ordered Pod creation, scaling, and deletion, should that be necessary when working with databases or replicated services
* We can specify a `PersistentVolumeClaim` template in the Pod definition and as long as this stays the same, the Pod will use the same claim and have access to the same data
* Each replica in a `StatefulSet` will have its own `PersistentVolumeClaim` so that data isn't shared across different replicas (The `PersistentVolumes` aren't deleted automatically when a replica is deleted)
* Pod names and networking will constantly follow the following pattern: <STATEFULSET_NAME>-<ORDINAL_ID>  
