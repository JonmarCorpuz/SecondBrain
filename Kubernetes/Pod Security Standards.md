
* Offers a set of guidelines that define security contexts for Pods
* Can be used to ensure that Pods adhere to specific security standards to reduce the risk of potential vulnerabilities and misconfigurations
* Enforced via the Pod Security Admission Controller, which uses labels for configuration and is set on a namespace basis (pod-security.kubernetes.io/<MODE>: <LEVEL>)

# Pod Security Standard Type

## Privileged

* Imposes no restrictions on the Pod's security settings
* The least restrictive policy
* Allows full access to system resources
* Suitable for Pods that require elevated privileges

## Baseline

* Enforces a minimal set of security restrictions that are suitable for general-purpose workloads
* Allows common container configurations while preventing escalations in privilege

## Restricted

* Enforces the strictest set of security standards
* Designed for applications that run in highly sensistive or regulated environments and require maximum security controls

# Pod Security Standard Modes

## enforce

* Blocks the creation of Pods that violate the security standards

## warn

* Shows a user-facing warning if violations occur, but still allows the Pods to be created

## audit

* Logs a security violation in Kubernetes audit logs, but still allows the Pod to be created

# Pod Security Standard Levels

## privileged

## baseline

## restricted
