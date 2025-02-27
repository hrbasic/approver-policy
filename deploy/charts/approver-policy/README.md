# cert-manager-approver-policy

![Version: v0.0.0](https://img.shields.io/badge/Version-v0.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v0.0.0](https://img.shields.io/badge/AppVersion-v0.0.0-informational?style=flat-square)

A Helm chart for cert-manager-approver-policy

**Homepage:** <https://github.com/cert-manager/approver-policy>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| cert-manager-dev | <cert-manager-dev@googlegroups.com> | <https://cert-manager.io> |

## Source Code

* <https://github.com/cert-manager/approver-policy>

## Values

<!-- AUTO-GENERATED -->


<table>
<tr>
<th>Property</th>
<th>Description</th>
<th>Type</th>
<th>Default</th>
</tr>
<tr>

<td>replicaCount</td>
<td>

Number of replicas of approver-policy to run.

</td>
<td>number</td>
<td>

```yaml
1
```

</td>
</tr>
<tr>

<td>image.repository</td>
<td>

Target image repository.

</td>
<td>string</td>
<td>

```yaml
quay.io/jetstack/cert-manager-approver-policy
```

</td>
</tr>
<tr>

<td>image.registry</td>
<td>

Target image registry. Will be prepended to the target image repository if set.

</td>
<td>unknown</td>
<td>

```yaml
null
```

</td>
</tr>
<tr>

<td>image.tag</td>
<td>

Target image version tag. Defaults to the chart's appVersion.

</td>
<td>unknown</td>
<td>

```yaml
null
```

</td>
</tr>
<tr>

<td>image.digest</td>
<td>

Target image digest. Will override any tag if set.  
For example:

```yaml
digest: sha256:0e072dddd1f7f8fc8909a2ca6f65e76c5f0d2fcfb8be47935ae3457e8bbceb20
```

</td>
<td>unknown</td>
<td>

```yaml
null
```

</td>
</tr>
<tr>

<td>image.pullPolicy</td>
<td>

Kubernetes imagePullPolicy on Deployment.

</td>
<td>string</td>
<td>

```yaml
IfNotPresent
```

</td>
</tr>
<tr>

<td>imagePullSecrets</td>
<td>

Optional secrets used for pulling the approver-policy container image.

</td>
<td>array</td>
<td>

```yaml
[]
```

</td>
</tr>
<tr>

<td>app.logLevel</td>
<td>

Verbosity of approver-policy logging. This is a value from 1 to 5.

</td>
<td>number</td>
<td>

```yaml
1
```

</td>
</tr>
<tr>

<td>app.extraArgs</td>
<td>

Extra CLI arguments that will be passed to the approver-policy process.

</td>
<td>array</td>
<td>

```yaml
[]
```

</td>
</tr>
<tr>

<td>app.approveSignerNames</td>
<td>

List if signer names that approver-policy will be given permission to approve and deny. CertificateRequests referencing these signer names can be processed by approver-policy.  
  
ref: https://cert-manager.io/docs/concepts/certificaterequest/#approval


</td>
<td>array</td>
<td>

```yaml
- issuers.cert-manager.io/*
- clusterissuers.cert-manager.io/*
```

</td>
</tr>
<tr>

<td>app.metrics.port</td>
<td>

Port for exposing Prometheus metrics on 0.0.0.0 on path '/metrics'.

</td>
<td>number</td>
<td>

```yaml
9402
```

</td>
</tr>
<tr>

<td>app.metrics.service.servicemonitor</td>
<td>

Create a Service resource to expose metrics endpoint.

</td>
<td>bool</td>
<td>

```yaml
true
```

</td>
</tr>
<tr>

<td>app.metrics.service.servicemonitor</td>
<td>

Service type to expose metrics.

</td>
<td>string</td>
<td>

```yaml
ClusterIP
```

</td>
</tr>
<tr>

<td>app.metrics.service.servicemonitor.enabled</td>
<td>

Create Prometheus ServiceMonitor resource for approver-policy

</td>
<td>bool</td>
<td>

```yaml
false
```

</td>
</tr>
<tr>

<td>app.metrics.service.servicemonitor.prometheusInstance</td>
<td>

Value for the "prometheus" label on the ServiceMonitor, this allows for multiple Prometheus instances selecting difference ServiceMonitors using label selectors

</td>
<td>string</td>
<td>

```yaml
default
```

</td>
</tr>
<tr>

<td>app.metrics.service.servicemonitor.interval</td>
<td>

Interval that the Prometheus will scrape for metrics

</td>
<td>string</td>
<td>

```yaml
10s
```

</td>
</tr>
<tr>

<td>app.metrics.service.servicemonitor.scrapeTimeout</td>
<td>

Timeout on each metric probe request

</td>
<td>string</td>
<td>

```yaml
5s
```

</td>
</tr>
<tr>

<td>app.metrics.service.servicemonitor.labels</td>
<td>

Additional labels to give the ServiceMonitor resource

</td>
<td>object</td>
<td>

```yaml
{}
```

</td>
</tr>
<tr>

<td>app.readinessProbe.port</td>
<td>

Container port to expose approver-policy HTTP readiness probe on default network interface.

</td>
<td>number</td>
<td>

```yaml
6060
```

</td>
</tr>
<tr>

<td>app.webhook.host</td>
<td>

Host that the webhook listens on.

</td>
<td>string</td>
<td>

```yaml
0.0.0.0
```

</td>
</tr>
<tr>

<td>app.webhook.port</td>
<td>

Port that the webhook listens on.

</td>
<td>number</td>
<td>

```yaml
10250
```

</td>
</tr>
<tr>

<td>app.webhook.timeoutSeconds</td>
<td>

Timeout of webhook HTTP request.

</td>
<td>number</td>
<td>

```yaml
5
```

</td>
</tr>
<tr>

<td>app.webhook.service.type</td>
<td>

Type of Kubernetes Service used by the Webhook

</td>
<td>string</td>
<td>

```yaml
ClusterIP
```

</td>
</tr>
<tr>

<td>app.webhook.hostNetwork</td>
<td>

Boolean value, expose pod on hostNetwork  
Required when running a custom CNI in managed providers such as AWS EKS  
  
ref: https://cert-manager.io/docs/installation/compatibility/#aws-eks

</td>
<td>bool</td>
<td>

```yaml
false
```

</td>
</tr>
<tr>

<td>app.webhook.dnsPolicy</td>
<td>

May need to be changed if hostNetwork: true

</td>
<td>string</td>
<td>

```yaml
ClusterFirst
```

</td>
</tr>
<tr>

<td>app.webhook.affinity</td>
<td>

A Kubernetes Affinity, if required; see https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.27/#affinity-v1-core  
  
For example:

```yaml
affinity:
  nodeAffinity:
   requiredDuringSchedulingIgnoredDuringExecution:
     nodeSelectorTerms:
     - matchExpressions:
       - key: foo.bar.com/role
         operator: In
         values:
         - master
```

</td>
<td>object</td>
<td>

```yaml
{}
```

</td>
</tr>
<tr>

<td>app.webhook.nodeSelector</td>
<td>

The nodeSelector on Pods tells Kubernetes to schedule Pods on the nodes with matching labels. See https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/

</td>
<td>object</td>
<td>

```yaml
{}
```

</td>
</tr>
<tr>

<td>app.webhook.tolerations</td>
<td>

A list of Kubernetes Tolerations, if required; see https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.27/#toleration-v1-core  
  
For example:

```yaml
tolerations:
- key: foo.bar.com/role
  operator: Equal
  value: master
  effect: NoSchedule
```

</td>
<td>array</td>
<td>

```yaml
[]
```

</td>
</tr>
<tr>

<td>volumeMounts</td>
<td>

Optional extra volume mounts. Useful for mounting custom root CAs  
  
For example:

```yaml
volumeMounts:
- name: my-volume-mount
  mountPath: /etc/approver-policy/secrets
```

</td>
<td>array</td>
<td>

```yaml
[]
```

</td>
</tr>
<tr>

<td>volumes</td>
<td>

Optional extra volumes.  
  
For example:

```yaml
volumes:
- name: my-volume
  secret:
    secretName: my-secret
```

</td>
<td>array</td>
<td>

```yaml
[]
```

</td>
</tr>
<tr>

<td>resources</td>
<td>

Kubernetes pod resources  
ref: https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/  
  
For example:

```yaml
resources:
  limits:
    cpu: 100m
    memory: 128Mi
  requests:
    cpu: 100m
    memory: 128Mi
```

</td>
<td>object</td>
<td>

```yaml
{}
```

</td>
</tr>
<tr>

<td>commonLabels</td>
<td>

Optional allow custom labels to be placed on resources

</td>
<td>object</td>
<td>

```yaml
{}
```

</td>
</tr>
<tr>

<td>podAnnotations</td>
<td>

Optional allow custom annotations to be placed on cert-manager-approver pod

</td>
<td>object</td>
<td>

```yaml
{}
```

</td>
</tr>
</table>

<!-- /AUTO-GENERATED -->