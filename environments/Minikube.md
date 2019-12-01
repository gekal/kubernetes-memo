# Minikube

## [Overview](https://minikube.sigs.k8s.io/docs/overview/)

Local Kubernetes, focused on application development & education

## [Getting Started](https://minikube.sigs.k8s.io/docs/start/)

- Linux
- macOS
- Windows

## コマンド

> 基本コマンド一覧

| コマンド   | 説明                                                             |
| --------- | ------------------------------------------------------------------- |
| start     | Starts a local kubernetes cluster                                   |
| status    | Gets the status of a local kubernetes cluster                       |
| stop      | Stops a running local kubernetes cluster                            |
| delete    | Deletes a local kubernetes cluster                                  |
| dashboard | Access the kubernetes dashboard running within the minikube cluster |

1. start

    ```bash
    $ minikube delete
    🔥  Deleting "minikube" in hyperkit ...
    💔  The "minikube" cluster has been deleted.
    🔥  Successfully deleted profile "minikube"
    dreamer:~ gekal$
    dreamer:~ gekal$
    dreamer:~ gekal$ minikube start
    😄  minikube v1.5.2 on Darwin 10.15.1
    ✨  Automatically selected the 'hyperkit' driver (alternates: [virtualbox])
    🔥  Creating hyperkit VM (CPUs=2, Memory=2000MB, Disk=20000MB) ...
    🐳  Preparing Kubernetes v1.16.2 on Docker '18.09.9' ...
    🚜  Pulling images ...
    🚀  Launching Kubernetes ...
    ⌛  Waiting for: apiserver
    🏄  Done! kubectl is now configured to use "minikube"
    ```

2. status

    ```bash
    $ minikube status
    host: Running
    kubelet: Running
    apiserver: Running
    kubeconfig: Configured
    ```

3. stop

    ```bash
    $ minikube stop
    ✋  Stopping "minikube" in hyperkit ...
    🛑  "minikube" stopped.
    ```

4. delete

    ```bash
    $ minikube delete
    🔥  Deleting "minikube" in hyperkit ...
    💔  The "minikube" cluster has been deleted.
    🔥  Successfully deleted profile "minikube"
    ```

5. dashboard

    ```bash
    $ minikube dashboard
    🤔  Verifying dashboard health ...
    🚀  Launching proxy ...
    🤔  Verifying proxy health ...
    🎉  Opening http://127.0.0.1:52909/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/ in your default browser...
    ```
