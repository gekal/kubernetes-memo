# Kubernetesリソース

## 概要

1. リソース（In a namespace）

    ```bash
    # In a namespace
    kubectl api-resources --namespaced=true
    ```

    | NAME                      | SHORTNAMES | APIGROUP                  | NAMESPACED | KIND                     |
    | ------------------------- | ---------- | ------------------------- | ---------- | ------------------------ |
    | bindings                  |            |                           | true       | Binding                  |
    | configmaps                | cm         |                           | true       | ConfigMap                |
    | endpoints                 | ep         |                           | true       | Endpoints                |
    | events                    | ev         |                           | true       | Event                    |
    | limitranges               | limits     |                           | true       | LimitRange               |
    | persistentvolumeclaims    | pvc        |                           | true       | PersistentVolumeClaim    |
    | pods                      | po         |                           | true       | Pod                      |
    | podtemplates              |            |                           | true       | PodTemplate              |
    | replicationcontrollers    | rc         |                           | true       | ReplicationController    |
    | resourcequotas            | quota      |                           | true       | ResourceQuota            |
    | secrets                   |            |                           | true       | Secret                   |
    | serviceaccounts           | sa         |                           | true       | ServiceAccount           |
    | services                  | svc        |                           | true       | Service                  |
    | controllerrevisions       |            | apps                      | true       | ControllerRevision       |
    | daemonsets                | ds         | apps                      | true       | DaemonSet                |
    | deployments               | deploy     | apps                      | true       | Deployment               |
    | replicasets               | rs         | apps                      | true       | ReplicaSet               |
    | statefulsets              | sts        | apps                      | true       | StatefulSet              |
    | localsubjectaccessreviews |            | authorization.k8s.io      | true       | LocalSubjectAccessReview |
    | horizontalpodautoscalers  | hpa        | autoscaling               | true       | HorizontalPodAutoscaler  |
    | cronjobs                  | cj         | batch                     | true       | CronJob                  |
    | jobs                      |            | batch                     | true       | Job                      |
    | leases                    |            | coordination.k8s.io       | true       | Lease                    |
    | events                    | ev         | events.k8s.io             | true       | Event                    |
    | ingresses                 | ing        | extensions                | true       | Ingress                  |
    | ingresses                 | ing        | networking.k8s.io         | true       | Ingress                  |
    | networkpolicies           | netpol     | networking.k8s.io         | true       | NetworkPolicy            |
    | poddisruptionbudgets      | pdb        | policy                    | true       | PodDisruptionBudget      |
    | rolebindings              |            | rbac.authorization.k8s.io | true       | RoleBinding              |
    | roles                     |            | rbac.authorization.k8s.io | true       | Role                     |

2. リソース（Not in a namespace）

    ```bash
    # Not in a namespace
    kubectl api-resources --namespaced=false
    ```

    | NAME                            | SHORTNAMES | APIGROUP                     | NAMESPACED | KIND                           |
    | ------------------------------- | ---------- | ---------------------------- | ---------- | ------------------------------ |
    | componentstatuses               | cs         |                              | false      | ComponentStatus                |
    | namespaces                      | ns         |                              | false      | Namespace                      |
    | nodes                           | no         |                              | false      | Node                           |
    | persistentvolumes               | pv         |                              | false      | PersistentVolume               |
    | mutatingwebhookconfigurations   |            | admissionregistration.k8s.io | false      | MutatingWebhookConfiguration   |
    | validatingwebhookconfigurations |            | admissionregistration.k8s.io | false      | ValidatingWebhookConfiguration |
    | customresourcedefinitions       | crd,crds   | apiextensions.k8s.io         | false      | CustomResourceDefinition       |
    | apiservices                     |            | apiregistration.k8s.io       | false      | APIService                     |
    | tokenreviews                    |            | authentication.k8s.io        | false      | TokenReview                    |
    | selfsubjectaccessreviews        |            | authorization.k8s.io         | false      | SelfSubjectAccessReview        |
    | selfsubjectrulesreviews         |            | authorization.k8s.io         | false      | SelfSubjectRulesReview         |
    | subjectaccessreviews            |            | authorization.k8s.io         | false      | SubjectAccessReview            |
    | certificatesigningrequests      | csr        | certificates.k8s.io          | false      | CertificateSigningRequest      |
    | runtimeclasses                  |            | node.k8s.io                  | false      | RuntimeClass                   |
    | podsecuritypolicies             | psp        | policy                       | false      | PodSecurityPolicy              |
    | clusterrolebindings             |            | rbac.authorization.k8s.io    | false      | ClusterRoleBinding             |
    | clusterroles                    |            | rbac.authorization.k8s.io    | false      | ClusterRole                    |
    | priorityclasses                 | pc         | scheduling.k8s.io            | false      | PriorityClass                  |
    | csidrivers                      |            | storage.k8s.io               | false      | CSIDriver                      |
    | csinodes                        |            | storage.k8s.io               | false      | CSINode                        |
    | storageclasses                  | sc         | storage.k8s.io               | false      | StorageClass                   |
    | volumeattachments               |            | storage.k8s.io               | false      | VolumeAttachment               |
