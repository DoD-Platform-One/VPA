# vertical-pod-autoscaler

![Version: 6.1.0-bb.2](https://img.shields.io/badge/Version-6.1.0--bb.2-informational?style=flat-square) ![AppVersion: 0.13.0](https://img.shields.io/badge/AppVersion-0.13.0-informational?style=flat-square)

Set of components that automatically adjust the amount of CPU and memory requested by pods running in the Kubernetes Cluster

## Upstream References
* <https://github.com/kubernetes/autoscaler>

* <https://github.com/kubernetes/autoscaler>
* <https://github.com/cowboysysop/charts/tree/master/charts/vertical-pod-autoscaler>

## Learn More
* [Application Overview](docs/overview.md)
* [Other Documentation](docs/)

## Pre-Requisites

* Kubernetes Cluster deployed
* Kubernetes config installed in `~/.kube/config`
* Helm installed

Install Helm

https://helm.sh/docs/intro/install/

## Deployment

* Clone down the repository
* cd into directory
```bash
helm install vertical-pod-autoscaler chart/
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| kubeVersion | string | `""` |  |
| imagePullSecrets[0].name | string | `"private-registry"` |  |
| nameOverride | string | `""` |  |
| fullnameOverride | string | `""` |  |
| commonAnnotations | object | `{}` |  |
| commonLabels | object | `{}` |  |
| extraDeploy | list | `[]` |  |
| admissionController.enabled | bool | `true` |  |
| admissionController.replicaCount | int | `1` |  |
| admissionController.image.repository | string | `"registry1.dso.mil/ironbank/opensource/kubernetes/autoscaler/admission-controller"` |  |
| admissionController.image.tag | string | `"0.13.0"` |  |
| admissionController.image.pullPolicy | string | `"IfNotPresent"` |  |
| admissionController.pdb.create | bool | `false` |  |
| admissionController.pdb.minAvailable | int | `1` |  |
| admissionController.serviceAccount.create | bool | `true` |  |
| admissionController.serviceAccount.annotations | object | `{}` |  |
| admissionController.serviceAccount.name | string | `nil` |  |
| admissionController.podAnnotations | object | `{}` |  |
| admissionController.podLabels | object | `{}` |  |
| admissionController.podSecurityContext.runAsNonRoot | bool | `true` |  |
| admissionController.podSecurityContext.runAsUser | int | `65534` |  |
| admissionController.securityContext | object | `{}` |  |
| admissionController.livenessProbe.enabled | bool | `true` |  |
| admissionController.livenessProbe.initialDelaySeconds | int | `0` |  |
| admissionController.livenessProbe.periodSeconds | int | `10` |  |
| admissionController.livenessProbe.timeoutSeconds | int | `1` |  |
| admissionController.livenessProbe.failureThreshold | int | `3` |  |
| admissionController.livenessProbe.successThreshold | int | `1` |  |
| admissionController.readinessProbe.enabled | bool | `true` |  |
| admissionController.readinessProbe.initialDelaySeconds | int | `0` |  |
| admissionController.readinessProbe.periodSeconds | int | `10` |  |
| admissionController.readinessProbe.timeoutSeconds | int | `1` |  |
| admissionController.readinessProbe.failureThreshold | int | `3` |  |
| admissionController.readinessProbe.successThreshold | int | `1` |  |
| admissionController.service.annotations | object | `{}` |  |
| admissionController.service.type | string | `"ClusterIP"` |  |
| admissionController.resources | object | `{}` |  |
| admissionController.nodeSelector | object | `{}` |  |
| admissionController.tolerations | list | `[]` |  |
| admissionController.affinity | object | `{}` |  |
| admissionController.extraArgs.v | int | `2` |  |
| admissionController.extraEnvVars | list | `[]` |  |
| admissionController.extraEnvVarsCM | string | `nil` |  |
| admissionController.extraEnvVarsSecret | string | `nil` |  |
| admissionController.metrics.service.annotations | object | `{}` |  |
| admissionController.metrics.service.type | string | `"ClusterIP"` |  |
| admissionController.metrics.service.port | int | `8944` |  |
| admissionController.metrics.serviceMonitor.enabled | bool | `false` |  |
| admissionController.metrics.serviceMonitor.annotations | object | `{}` |  |
| admissionController.metrics.serviceMonitor.labels | object | `{}` |  |
| admissionController.metrics.serviceMonitor.jobLabel | string | `""` |  |
| admissionController.metrics.serviceMonitor.interval | string | `""` |  |
| admissionController.metrics.serviceMonitor.scrapeTimeout | string | `""` |  |
| admissionController.metrics.serviceMonitor.metricRelabelings | list | `[]` |  |
| admissionController.metrics.serviceMonitor.relabelings | list | `[]` |  |
| admissionController.tls.caCert | string | `""` |  |
| admissionController.tls.cert | string | `""` |  |
| admissionController.tls.key | string | `""` |  |
| admissionController.tls.existingSecret | string | `""` |  |
| recommender.replicaCount | int | `1` |  |
| recommender.image.repository | string | `"registry1.dso.mil/ironbank/opensource/kubernetes/autoscaler/recommender"` |  |
| recommender.image.tag | string | `"0.13.0"` |  |
| recommender.image.pullPolicy | string | `"IfNotPresent"` |  |
| recommender.pdb.create | bool | `false` |  |
| recommender.pdb.minAvailable | int | `1` |  |
| recommender.serviceAccount.create | bool | `true` |  |
| recommender.serviceAccount.annotations | object | `{}` |  |
| recommender.serviceAccount.name | string | `nil` |  |
| recommender.podAnnotations | object | `{}` |  |
| recommender.podLabels | object | `{}` |  |
| recommender.podSecurityContext.runAsNonRoot | bool | `true` |  |
| recommender.podSecurityContext.runAsUser | int | `65534` |  |
| recommender.securityContext | object | `{}` |  |
| recommender.livenessProbe.enabled | bool | `true` |  |
| recommender.livenessProbe.initialDelaySeconds | int | `0` |  |
| recommender.livenessProbe.periodSeconds | int | `10` |  |
| recommender.livenessProbe.timeoutSeconds | int | `1` |  |
| recommender.livenessProbe.failureThreshold | int | `3` |  |
| recommender.livenessProbe.successThreshold | int | `1` |  |
| recommender.readinessProbe.enabled | bool | `true` |  |
| recommender.readinessProbe.initialDelaySeconds | int | `0` |  |
| recommender.readinessProbe.periodSeconds | int | `10` |  |
| recommender.readinessProbe.timeoutSeconds | int | `1` |  |
| recommender.readinessProbe.failureThreshold | int | `3` |  |
| recommender.readinessProbe.successThreshold | int | `1` |  |
| recommender.resources | object | `{}` |  |
| recommender.nodeSelector | object | `{}` |  |
| recommender.tolerations | list | `[]` |  |
| recommender.affinity | object | `{}` |  |
| recommender.extraArgs.v | int | `2` |  |
| recommender.extraEnvVars | list | `[]` |  |
| recommender.extraEnvVarsCM | string | `nil` |  |
| recommender.extraEnvVarsSecret | string | `nil` |  |
| recommender.metrics.service.annotations | object | `{}` |  |
| recommender.metrics.service.type | string | `"ClusterIP"` |  |
| recommender.metrics.service.port | int | `8942` |  |
| recommender.metrics.serviceMonitor.enabled | bool | `false` |  |
| recommender.metrics.serviceMonitor.annotations | object | `{}` |  |
| recommender.metrics.serviceMonitor.labels | object | `{}` |  |
| recommender.metrics.serviceMonitor.jobLabel | string | `""` |  |
| recommender.metrics.serviceMonitor.interval | string | `""` |  |
| recommender.metrics.serviceMonitor.scrapeTimeout | string | `""` |  |
| recommender.metrics.serviceMonitor.metricRelabelings | list | `[]` |  |
| recommender.metrics.serviceMonitor.relabelings | list | `[]` |  |
| updater.enabled | bool | `true` |  |
| updater.replicaCount | int | `1` |  |
| updater.image.repository | string | `"registry1.dso.mil/ironbank/opensource/kubernetes/autoscaler/updater"` |  |
| updater.image.tag | string | `"0.13.0"` |  |
| updater.image.pullPolicy | string | `"IfNotPresent"` |  |
| updater.pdb.create | bool | `false` |  |
| updater.pdb.minAvailable | int | `1` |  |
| updater.serviceAccount.create | bool | `true` |  |
| updater.serviceAccount.annotations | object | `{}` |  |
| updater.serviceAccount.name | string | `nil` |  |
| updater.podAnnotations | object | `{}` |  |
| updater.podLabels | object | `{}` |  |
| updater.podSecurityContext.runAsNonRoot | bool | `true` |  |
| updater.podSecurityContext.runAsUser | int | `65534` |  |
| updater.securityContext | object | `{}` |  |
| updater.livenessProbe.enabled | bool | `true` |  |
| updater.livenessProbe.initialDelaySeconds | int | `0` |  |
| updater.livenessProbe.periodSeconds | int | `10` |  |
| updater.livenessProbe.timeoutSeconds | int | `1` |  |
| updater.livenessProbe.failureThreshold | int | `3` |  |
| updater.livenessProbe.successThreshold | int | `1` |  |
| updater.readinessProbe.enabled | bool | `true` |  |
| updater.readinessProbe.initialDelaySeconds | int | `0` |  |
| updater.readinessProbe.periodSeconds | int | `10` |  |
| updater.readinessProbe.timeoutSeconds | int | `1` |  |
| updater.readinessProbe.failureThreshold | int | `3` |  |
| updater.readinessProbe.successThreshold | int | `1` |  |
| updater.resources | object | `{}` |  |
| updater.nodeSelector | object | `{}` |  |
| updater.tolerations | list | `[]` |  |
| updater.affinity | object | `{}` |  |
| updater.extraArgs.v | int | `2` |  |
| updater.extraEnvVars | list | `[]` |  |
| updater.extraEnvVarsCM | string | `nil` |  |
| updater.extraEnvVarsSecret | string | `nil` |  |
| updater.metrics.service.annotations | object | `{}` |  |
| updater.metrics.service.type | string | `"ClusterIP"` |  |
| updater.metrics.service.port | int | `8943` |  |
| updater.metrics.serviceMonitor.enabled | bool | `false` |  |
| updater.metrics.serviceMonitor.annotations | object | `{}` |  |
| updater.metrics.serviceMonitor.labels | object | `{}` |  |
| updater.metrics.serviceMonitor.jobLabel | string | `""` |  |
| updater.metrics.serviceMonitor.interval | string | `""` |  |
| updater.metrics.serviceMonitor.scrapeTimeout | string | `""` |  |
| updater.metrics.serviceMonitor.metricRelabelings | list | `[]` |  |
| updater.metrics.serviceMonitor.relabelings | list | `[]` |  |
| crds.image.repository | string | `"registry1.dso.mil/ironbank/opensource/kubernetes/kubectl"` |  |
| crds.image.tag | string | `"v1.26.1"` |  |
| crds.image.pullPolicy | string | `"IfNotPresent"` |  |
| crds.podAnnotations | object | `{}` |  |
| crds.nodeSelector | object | `{}` |  |
| crds.tolerations | list | `[]` |  |
| crds.affinity | object | `{}` |  |
| tests.enabled | bool | `false` |  |
| tests.image.repository | string | `"ghcr.io/cowboysysop/pytest"` |  |
| tests.image.tag | string | `"1.0.35"` |  |
| tests.image.pullPolicy | string | `"IfNotPresent"` |  |

## Contributing

Please see the [contributing guide](./CONTRIBUTING.md) if you are interested in contributing.
