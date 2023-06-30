# loki-helm-operator
A helm based operator for the loki solution with single binary mode deployment optionality for experimentation purposes

# example yaml for a minimal deploy
```
apiVersion: charts.example.com/v1alpha1
kind: Loki
metadata:
  name: loki-sample
spec:
  global:
    clusterDomain: cluster.local
    dnsService: dns-default
    dnsNamespace: openshift-dns
  loki:
    auth_enabled: false
    commonConfig:
      replication_factor: 1
    storage:
      type: 'filesystem'
  singleBinary:
    replicas: 1
  rbac:
    sccEnabled: true
  test:
    enabled: false
  monitoring:
    dashboards:
      enabled: false
    rules:
      enabled: false
      alerting: false
    selfMonitoring:
      enabled: false
      grafanaAgent:
        installOperator: false
    serviceMonitor:
      enabled: false
      metricsInstance:
        enabled: false
    lokiCanary:
        enabled: false
```

