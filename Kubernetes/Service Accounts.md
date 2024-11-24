
* Service accounts authenticate via JWT tokens, which are automatically generated and mounted by Kubernetes inside each Pod using a service account
* JWT tokens are mounted under /var/run/secrets/kubernetes.io/serviceaccount/token
* JWT tokens can be used to authenticate your requests against the Kubernetes API
