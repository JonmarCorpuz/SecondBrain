
* Regulate ingress and egress traffic for Pods
* Define how Pods can communicate with each other and with other network endpoints
* Can specify rules for both ingress and egress traffic, as well as which Pods the policy will apply to (By default, all traffic between Pods is allowed in Kubernetes)
* Provide one solution to isolate Pods and reduce the attack surface in case a Pod becomes compromised
* The CNI plugin used in the cluster must support this feature in order for Network Policies to have any effect

# Configure Network Policies

* With the Pod Selector by using `matchLabels` and `matchExpressions`
* With the Namespace Selector by using `matchLabels` and `matchExpressions`
* With the IP block by using CIDR blocks
* With the ports and protocols by defining specific ports and protocols
