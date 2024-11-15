# Services Overview

A [Service](https://kubernetes.io/docs/concepts/services-networking/service/#:~:text=Expose%20an%20application%20running%20in%20your%20cluster%20behind%20a%20single%20outward%2Dfacing%20endpoint%2C%20even%20when%20the%20workload%20is%20split%20across%20multiple%20backends.) exposes an application running in your cluster behind a single outward-facing endpoint, even when the workload is split across multiple backends, through Kubernete's [Service API](https://kubernetes.io/docs/concepts/services-networking/service/#:~:text=The%20Service%20API%2C%20part%20of%20Kubernetes%2C%20is%20an%20abstraction%20to%20help%20you%20expose%20groups%20of%20Pods%20over%20a%20network), which is an abstraction that helps you expose groups of Pods over a network

* Provides built-in load balancing across Pods
* Allows clients to interact with applications that are running within Pods in your cluster
* Service abstraction enables you to decouple frontends from backends
* The set of Pods targeted by a Service is usually determined by a [selector](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/#:~:text=Via%20a%20label%20selector%2C%20the%20client/user%20can%20identify%20a%20set%20of%20objects.%20The%20label%20selector%20is%20the%20core%20grouping%20primitive%20in%20Kubernetes.)
