# Services Overview

The [Service API](https://kubernetes.io/docs/concepts/services-networking/service/#:~:text=Expose%20an%20application%20running%20in%20your%20cluster%20behind%20a%20single%20outward%2Dfacing%20endpoint%2C%20even%20when%20the%20workload%20is%20split%20across%20multiple%20backends.) exposes an application running in your cluster behind a single outward-facing endpoint, even when the workload is split across multiple backends

* Provides built-in load balancing across Pods
* Allows clients to interact with applications that are running within Pods in your cluster
* Service abstraction enables you to decouple frontends from backends 
* The set of Pods targeted by a Service is usually determined by a [selector](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/#:~:text=Via%20a%20label%20selector%2C%20the%20client/user%20can%20identify%20a%20set%20of%20objects.%20The%20label%20selector%20is%20the%20core%20grouping%20primitive%20in%20Kubernetes.) that you define

# EndpointSlices

The [EndpointSlice API](https://kubernetes.io/docs/concepts/services-networking/endpoint-slices/#:~:text=The%20EndpointSlice%20API%20is%20the%20mechanism%20that%20Kubernetes%20uses%20to%20let%20your%20Service%20scale%20to%20handle%20large%20numbers%20of%20backends%2C%20and%20allows%20the%20cluster%20to%20update%20its%20list%20of%20healthy%20backends%20efficiently.) is the mechanism that Kubernetes uses to let your Service scale to handle large numbers of backends, and allows the cluster to update its list of healthy backends efficiently
