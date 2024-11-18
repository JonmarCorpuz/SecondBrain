# Services Overview

The [Service API](https://kubernetes.io/docs/concepts/services-networking/service/#:~:text=Expose%20an%20application%20running%20in%20your%20cluster%20behind%20a%20single%20outward%2Dfacing%20endpoint%2C%20even%20when%20the%20workload%20is%20split%20across%20multiple%20backends.) exposes an application running in your cluster behind a single outward-facing endpoint, even when the workload is split across multiple backends

* Provides built-in load balancing across Pods
* Allows clients to interact with applications that are running within Pods in your cluster
* Service abstraction enables you to decouple frontends from backends 
* The set of Pods targeted by a Service is usually determined by a [selector](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/#:~:text=Via%20a%20label%20selector%2C%20the%20client/user%20can%20identify%20a%20set%20of%20objects.%20The%20label%20selector%20is%20the%20core%20grouping%20primitive%20in%20Kubernetes.) that you define

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EndpointSlices

The [EndpointSlice API](https://kubernetes.io/docs/concepts/services-networking/endpoint-slices/#:~:text=The%20EndpointSlice%20API%20is%20the%20mechanism%20that%20Kubernetes%20uses%20to%20let%20your%20Service%20scale%20to%20handle%20large%20numbers%20of%20backends%2C%20and%20allows%20the%20cluster%20to%20update%20its%20list%20of%20healthy%20backends%20efficiently.) is the mechanism that Kubernetes uses to let your Service scale to handle large numbers of backends, and allows the cluster to update its list of healthy backends efficiently

* Contains references to a set of network endpoints
* Offer a more scalable and extensible alternative to [Endpoints](https://kubernetes.io/docs/concepts/services-networking/service/#endpoints)
* The control plane automatically creates EndpointSlices for any Kubernetes Service that has a [selector](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/#label-selectors) specified
* Group network endpoints together by unique combination of protocol, port number, and Service name
* The name of an EndpointSlice object must be a valid DNS subdomain name
* By default, the control plane creates and manages EndpointSlices to have no more than 100 endpoints each
* Can act as the source of truth for kube-proxy when it comes to how to route internal traffic

## EndpointSlice Conditions

* The EndpointSlice API stores conditions about endpoints that may be useful for consumers

### Ready

The [Ready](https://kubernetes.io/docs/concepts/services-networking/endpoint-slices/#ready) condition maps to a Pod's Ready condition

* A running Pod with the Ready condition set to True should have this EndpointSlice condition also set to true
* For compatibility reasons, ready is never true when a Pod is terminating (The only exception to this rule is for Services with `spec.publicNotReadyAddresses` set to true since endpoints for these Services will always have the ready condition set to true)

### Serving

The [Serving](https://kubernetes.io/docs/concepts/services-networking/endpoint-slices/#serving) condition is similar to the Ready condition but allows users to track readiness for terminating Pods independent of existing semantics for ready

* Users should use this condition if they care about Pod readiness while the Pod is also terminating

### Terminating

The [Terminating](https://kubernetes.io/docs/concepts/services-networking/endpoint-slices/#terminating) condition indicates whether an endpoint is terminating

* For Pods, this is any Pod that has a deletion timestamp set

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Endpoints

An [endpoints](https://kubernetes.io/docs/concepts/services-networking/service/#endpoints) (The resource kind is plural) defines a list of network endpoints that are typically referenced by a Service to define which Pods the traffic can be sent to

* Each endpoint within an EndpointSlice can contain relevant topology information (*Location of the endpoint*, *Information about the corresponding Node and zone*, *etc.*)
* The [EndpointSlice API](https://kubernetes.io/docs/concepts/services-networking/endpoint-slices/#:~:text=The%20EndpointSlice%20API%20is%20the%20mechanism%20that%20Kubernetes%20uses%20to%20let%20your%20Service%20scale%20to%20handle%20large%20numbers%20of%20backends%2C%20and%20allows%20the%20cluster%20to%20update%20its%20list%20of%20healthy%20backends%20efficiently.) is the recommended replacement for Endpoints
