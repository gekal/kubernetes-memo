# Pods

## 概要

<https://kubernetes.io/docs/concepts/workloads/pods/>

## [API Reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.16/#pod-v1-core)

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
