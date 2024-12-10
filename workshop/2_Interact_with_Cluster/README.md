Hello again fellow ESDealer, this `second` assignment is about **interacting with your K8s cluster**. And yes, there is already something in it, let's find out what.

## INFO 💡
### `kubectl`
`Objective`: **interact** with cluster to create pods and other components (e.g., _Service_, _Secret_, _ConfigMap_) on that node.

> Kubectl is a `comand line tool` for K8s clusters. It submits commands to the API server (a master node process, main entrypoint) in order to interact with cluster (e.g., create/delete components). The work processes will executing the commands.
>
> FYI: `kubectl` got installed as a dependency when you installed `minikube`. 🙀


## TODO 🎅
1. Get all the **nodes** in the cluster:
    ```
    kubectl get node
    ```
    You will see one node _ready_ to accept our application for deployment.
2. Get all services in master node:
    ```
    kubectl get po -A
    ```
    This should include what we talked about: `etcd`, `API server`, `controller manager`, `scheduler`, and others.
3. Get a dashboard of your K8s cluster:
    ```
    minikube dashboard
    ```
    Once you are on the dashboard, navigate to Cluster -> Nodes in the sidebar. There you will see the `one-node` created by `minikube`.

Congrats! You have passed the talking stage with your local K8s cluster. Now, let the fun begin. 👽
