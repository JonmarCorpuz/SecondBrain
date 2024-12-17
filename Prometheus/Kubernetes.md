# CrashLoopBackOff 

## Detect CrashLoopBackOff

PromQL query
```PromQL
kube_pod_container_status_waiting_reason{reason="CrashLoopBackOff"} == 1
```

## Trace the Amount of Restarts Happening in Pods

PromQL query
```PromQL
rate(kube_pod_container_status_restarts_total[5m]) > 0
```

Alerting rule
```YAML
- alert: RestartsAlert
  expr: rate(kube_pod_container_status_restarts_total[5m]) > 0
  for: 10m
  labels:
    severity: warning
  annotations:
    summary: Pod is being restarted
  description: Pod {{ $labels.pod }} in {{ $labels.namespace }} has a container {{ $labels.container }} which is being restarted
```
