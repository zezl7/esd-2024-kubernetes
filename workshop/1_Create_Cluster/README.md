Hello fellow ESD warrior, this assignment is about **creating a local K8s cluster**.

## INFO 💡
### `Minikube`
`Obective`: create a virtual **node** on your local machine.

>Minikube is a `one-node` cluster where the master & worker processes run on one node (=machine / =server). Normally, each worker process and each master process gets their own server. E.g., if you have 4 worker processes and 2 master processes you would need 6 separate virtual/physical servers. 
This node has Docker pre-installed so you can run the containers in the pods.


### `kubectl`
`Objective`: **interact** with cluster to create pods and other components (e.g., _Service_, _Secret_, _ConfigMap_) on that node.

> Kubectl is a `comand line tool` for K8s clusters. It submits commands to the API server (a master node process, main entrypoint) in order to interact with cluster (e.g., create/delete components). The work processes will executing the commands.


## TODO 🎅
1. Install `minikube` as described [in step 1](https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download).
2. Start your cluster with
    ```
    minkube start
    ```

Congrats! You have created a local K8s cluster. There is nothing in it though.. Or is [there](https://github.com/zezl7/esd-2024-kubernetes/tree/main/workshop/2_Interact_with_Cluster)? 👤
