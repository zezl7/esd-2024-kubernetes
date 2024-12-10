Well, there is only one thing inside this cluster: a node ✨ Exciting? Not **yet**.

## INFO 💡
### `kubectl`
`Objective`: **interact** with cluster to create pods and other components (e.g., _Service_, _Secret_, _ConfigMap_) on that node.

> Kubectl is a `comand line tool` for K8s clusters. It submits commands to the API server (a master node process, main entrypoint) in order to interact with the cluster (e.g., create/delete components). The work nodes will execute the commands.
>
> FYI: `kubectl` got installed as a dependency when you installed `minikube`. 🙀


## TODO 🎅
1. See all the **nodes** in the cluster:
    ```
    kubectl get node
    ```
    You will see **the one** node _ready_ to accept our application for deployment.
2. See all services currently running:
    ```
    kubectl get po -A
    ```
    This should include what we talked about: `etcd`, `API server`, `controller manager`, `scheduler`, and others.
3. Get a dashboard of your K8s cluster:
    ```
    minikube dashboard
    ```
    Once you are on the dashboard, navigate to Cluster -> Nodes in the sidebar. There you will see your **one and only node**. ✨

Congrats! You have passed the talking stage with your local K8s cluster. Now, let the [configuration](https://github.com/zezl7/esd-2024-kubernetes/tree/main/workshop/3_Database_Configurations) begin. 👽
