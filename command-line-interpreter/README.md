# コマンドラインインタプリタ(kubectl)

- [コマンドラインインタプリタ(kubectl)](#%e3%82%b3%e3%83%9e%e3%83%b3%e3%83%89%e3%83%a9%e3%82%a4%e3%83%b3%e3%82%a4%e3%83%b3%e3%82%bf%e3%83%97%e3%83%aa%e3%82%bfkubectl)
  - [kubectl](#kubectl)
  - [インストール](#%e3%82%a4%e3%83%b3%e3%82%b9%e3%83%88%e3%83%bc%e3%83%ab)
  - [コマンド](#%e3%82%b3%e3%83%9e%e3%83%b3%e3%83%89)
    - [Syntax](#syntax)
    - [使用例](#%e4%bd%bf%e7%94%a8%e4%be%8b)
    - [リソース作成](#%e3%83%aa%e3%82%bd%e3%83%bc%e3%82%b9%e4%bd%9c%e6%88%90)
    - [Serviceとしてエクスポス](#service%e3%81%a8%e3%81%97%e3%81%a6%e3%82%a8%e3%82%af%e3%82%b9%e3%83%9d%e3%82%b9)

## kubectl

Kubernetesのコマンドラインツールであるkubectlを使用して、Kubernetesクラスターに対してコマンドを実行することができます。

## インストール

1. Mac

    ```bash
    $ brew install kubernetes-cli
    ==> Downloading https://homebrew.bintray.com/bottles/kubernetes-cli-1.16.3.catalina.bottle.tar.gz
    ...
    ==> Summary
    🍺  /usr/local/Cellar/kubernetes-cli/1.16.3: 232 files, 52.3MB

    $ kubectl version
    Client Version: version.Info{Major:"1", Minor:"16", GitVersion:"v1.16.3", GitCommit:"b3cbbae08ec52a7fc73d334838e18d17e8512749", GitTreeState:"clean", BuildDate:"2019-11-14T04:24:29Z", GoVersion:"go1.12.13", Compiler:"gc", Platform:"darwin/amd64"}
    Server Version: version.Info{Major:"1", Minor:"16", GitVersion:"v1.16.2", GitCommit:"c97fe5036ef3df2967d086711e6c0c405941e14b", GitTreeState:"clean", BuildDate:"2019-10-15T19:09:08Z", GoVersion:"go1.12.10", Compiler:"gc", Platform:"linux/amd64"}
    ```

## コマンド

### Syntax

```bash
kubectl [command] [TYPE] [NAME] [flags]
```

1. GETTING STARTED
1. APP MANAGEMENT
1. WORKING WITH APPS
1. CLUSTER MANAGEMENT
1. KUBECTL SETTINGS AND USAGE

### 使用例

### リソース作成

1. pod

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

1. others

    <https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#create>

    > サンプルコマンドの後ろに「--dry-run --output yaml」を追加すれば、ダミーのマニフェストを生成する。

    1. clusterrole
    2. clusterrolebinding
    3. configmap
    4. cronjob
    5. deployment
    6. job
    7. namespace
    8. poddisruptionbudget
    9. priorityclass
    10. quota
    11. role
    12. rolebinding
    13. secret
    14. secret docker-registry
    15. secret generic
    16. secret tls
    17. service
    18. service clusterip
    19. service externalname
    20. service loadbalancer
    21. service nodeport
    22. serviceaccount

    ```bash
    # デプロイメント
    $ kubectl create deployment my-dep --image=busybox --dry-run --output yaml
    apiVersion: apps/v1
    kind: Deployment
    metadata:
      creationTimestamp: null
      labels:
        app: my-dep
      name: my-dep
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: my-dep
      strategy: {}
      template:
        metadata:
          creationTimestamp: null
          labels:
            app: my-dep
        spec:
          containers:
          - image: busybox
            name: busybox
            resources: {}
    status: {}
    ```

### Serviceとしてエクスポス

1. deployment

    ```bash
    kubectl expose deployment nginx --port=80 --target-port=8000
    ```

2. service

    ```bash
    kubectl expose service nginx --port=443 --target-port=8443 --name=nginx-https
    ```

3. replica set

    ```bash
    kubectl expose rs nginx --port=80 --target-port=8000
    ```

4. replication controller

    ```bash
    kubectl expose rc nginx --port=80 --target-port=8000
    ```

5. pod

    ```bash
    kubectl expose pod valid-pod --port=444 --name=frontend
    ```
