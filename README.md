

# pocket-id

![Version](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fapi.github.com%2Frepos%2Fpocket-id%2Fpocket-id%2Freleases%2Flatest&query=%24.name&label=Version)![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)
![AppVersion](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fapi.github.com%2Frepos%2Fpocket-id%2Fpocket-id%2Freleases%2Flatest&query=%24.name&label=Version)

Pocket-id Helm chart for Kubernetes

### Installing the Chart
To install the chart with the release name my-release:

```
helm install my-release oci://ghcr.io/hobbit44/pocket-id-helm/pocket-id
```

### Uninstalling the Chart
To uninstall/delete the my-release deployment:

```
helm delete my-release
```
The command removes all the Kubernetes components associated with the chart and deletes the release.

## Source Code

* <https://github.com/pocket-id/pocket-id>
* <https://github.com/hobbit44/pocket-id-helm>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| config | object | `{}` | Pocket-id configuration variables For more information see: https://pocket-id.org/docs/configuration/environment-variables |
| existingConfigMap | string | `""` | Name of an existing config map containing any environment variables |
| existingSecret | string | `""` | Name of an existing secret containing any environment variables |
| fullnameOverride | string | `""` | The full resource name override |
| image.pullPolicy | string | `"IfNotPresent"` | The pull policy for images |
| image.repository | string | `"ghcr.io/pocket-id/pocket-id"` | The container image to run |
| image.tag | string | `""` | Overrides the image tag whose default is the chart version. |
| imagePullSecrets | list | `[]` | This is for the secretes for pulling an image from a private repository more information can be found here: https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/ |
| ingress.annotations | object | `{}` | Annotations for the ingress |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` | Enables an ingress for the application |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"Prefix"` |  |
| ingress.tls | list | `[]` | Adds tls to the ingress |
| livenessProbe.httpGet.path | string | `"/health"` | Healthcheck endpoint |
| livenessProbe.httpGet.port | string | `"http"` |  |
| livenessProbe.initialDelaySeconds | int | `60` |  |
| nameOverride | string | `""` | The resource name suffix |
| nodeSelector | object | `{}` |  |
| persistence.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.annotations | object | `{}` |  |
| persistence.enabled | bool | `true` | Persist data to a persistent volume |
| persistence.existingClaim | string | `""` | A manually managed Persistent Volume and Claim Requires persistence.enabled: true If defined, PVC must be created manually before volume will be bound |
| persistence.size | string | `"8Gi"` |  |
| persistence.storageClass | string | `""` | Persistent Volume Storage Class If defined, storageClassName: <storageClass> If set to "-", storageClassName: "", which disables dynamic provisioning If undefined (the default) or set to null, no storageClassName spec is   set, choosing the default provisioner.  (gp2 on AWS, standard on   GKE, AWS & OpenStack) |
| podAnnotations | object | `{}` |  |
| podLabels | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| priorityClassName | string | `""` | Optionally set a priority class name to run the pods at. See Pod Priority and Preemption: https://kubernetes.io/docs/concepts/scheduling-eviction/pod-priority-preemption/ |
| readinessProbe.httpGet.path | string | `"/health"` | Healthcheck endpoint |
| readinessProbe.httpGet.port | string | `"http"` |  |
| readinessProbe.initialDelaySeconds | int | `60` |  |
| resources | object | `{}` | Specifiy resources for the pod |
| securityContext | object | `{}` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.automount | bool | `true` | Automatically mount a ServiceAccount's API credentials? |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| tolerations | list | `[]` |  |
| volumeMounts | list | `[]` | Additional volumeMounts on the pod definition. |
| volumes | list | `[]` | Additional volumes on the pod definition. |

### Todo

- [ ] Add database provider charts as dependencies
- [ ] Seperate front and backend to seperate deployments

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.14.2](https://github.com/norwoodj/helm-docs/releases/v1.14.2)
