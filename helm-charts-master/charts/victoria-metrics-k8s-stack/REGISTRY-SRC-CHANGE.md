# Change default registry for images

dependencies:

[+] name: victoria-metrics-operator
  version: "0.27.4"
  condition: victoria-metrics-operator.enabled

[-] name: kube-state-metrics
  version: "5.16.0"
  condition: kube-state-metrics.enabled

[-] name: prometheus-node-exporter
  version: "4.26.1"
  condition: prometheus-node-exporter.enabled

[-] name: grafana
  version: "7.3.0"
  condition: grafana.enabled

[-] name: crds
  version: "0.0.0"
  condition: crds.enabled

## victoria-metrics-operator
from
```
image:
  # -- Image repository
  repository: victoriametrics/operator
  # -- Image tag
  tag: v0.40.0
  # -- Image pull policy
  pullPolicy: IfNotPresent
  
cleanupCRD: false
cleanupImage:
  repository: gcr.io/google_containers/hyperkube
  tag: v1.18.0
  pullPolicy: IfNotPresent
```
to https://msk-phub-i-01.mangazeya.local:5002
```
image:
  # -- Image repository
  repository: https://msk-phub-i-01.mangazeya.local:5002/victoriametrics/operator
  # -- Image tag
  tag: v0.40.0
  # -- Image pull policy
  pullPolicy: IfNotPresent
  
cleanupCRD: false
cleanupImage:
  repository: https://msk-phub-i-01.mangazeya.local:5002/google_containers/hyperkube
  tag: v1.18.0
  pullPolicy: IfNotPresent
```

## victoria-metrics-single
```
repository: victoriametrics/victoria-metrics -> https://msk-phub-i-01.mangazeya.local:5002/victoriametrics/victoria-metrics
repository: victoriametrics/vmbackupmanager -> https://msk-phub-i-01.mangazeya.local:5002/victoriametrics/vmbackupmanager
```

## victoria-metrics-agent
```
repository: victoriametrics/vmagent -> https://msk-phub-i-01.mangazeya.local:5002/victoriametrics/vmagent
```

## victoria-metrics-alert
```
repository: victoriametrics/vmalert -> https://msk-phub-i-01.mangazeya.local:5002/victoriametrics/vmalert
```

## victoria-metrics-auth
```
repository: victoriametrics/vmauth -> https://msk-phub-i-01.mangazeya.local:5002/victoriametrics/vmauth
```

## victoria-metrics-cluster
```
repository: victoriametrics/vmselect -> https://msk-phub-i-01.mangazeya.local:5002/victoriametrics/vmselect
```
## victoria-metrics-gateway
```
repository: victoriametrics/vmgateway -> https://msk-phub-i-01.mangazeya.local:5002/victoriametrics/vmgateway
```