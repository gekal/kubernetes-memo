# Pods

## 概要

<https://kubernetes.io/docs/concepts/workloads/pods/>

## [API Reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.16/#pod-v1-core)

### PodSpec

1. activeDeadlineSeconds
2. `affinity`
3. automountServiceAccountToken
4. `containers`
5. dnsConfig
6. dnsPolicy
    - ClusterFirstWithHostNet
    - **ClusterFirst**
    - Default
    - None
7. enableServiceLinks
8. ephemeralContainers
9. hostAliases
10. hostIPC
11. hostNetwork
12. hostPID
13. hostname
14. imagePullSecrets
15. `initContainers`
16. nodeName
17. nodeSelector
18. overhead
19. preemptionPolicy
20. priority
21. priorityClassName
22. readinessGates
23. `restartPolicy`
    - Always
    - OnFailure
    - Never
24. runtimeClassName
25. schedulerName
26. securityContext
27. serviceAccount
28. serviceAccountName
29. shareProcessNamespace
30. subdomain
31. terminationGracePeriodSeconds
32. `tolerations`
33. topologySpreadConstraints
34. `volumes`

## ライフサイクル

## クリックスタート

### マニフェスト生成

```bash
$ kubectl run nginx --image=nginx --restart=Never --dry-run -o yaml
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: nginx
  name: nginx
spec:
  containers:
  - image: nginx
    name: nginx
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Never
status: {}
```

## サンプル

1. [ベーシック](samples/basic.yaml)
