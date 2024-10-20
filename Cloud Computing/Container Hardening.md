
* Containers that run applications should not have root privileges
* Containers should have an immutable filesystem, meaning that they can't be altered or added to
* Container images should be frequently scanned for vulnerabilities or misconfigurations
* Privileged containers should be prevented
* Access to the control plane node should be restricted using a firewall and RBAC in an isolated network
* Control plane components should communicate using TLS certificates
* Credentials and sensitive information shouldn't be stored as plaintext in configuration files, the should instead be encrypted and in Kubernetes secrets
* Anonymous access should be disabled
* Strong user authentication should be used
* Any obsolete components in the cluster should be removed

# Kubernetes Secrets

Kubernetes secret is an object used to store sensitive information 

# Pod Security Standards

| Pod Security Policy Level | Description |
| --- | --- |
| Privileged | |
| Baseline | |
| Restricted | |

# Pod Security Admission 

PSA enforces PSS by intercepting API server requests using a PSA controller and applying the policies 
