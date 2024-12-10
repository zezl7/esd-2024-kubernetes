Hello fellow ESD-ler (or ESDealer 👀), this `first` assignment is about **creating a local K8s cluster**.

## INFO 💡
### `Minikube`
`Obective`: create a virtual **node** on your local machine.

>Minikube is a `one-node` cluster where the master & worker processes run on one node (=machine / =server). Normally, each worker process and each master process gets their own server. E.g., if you have 4 worker processes and 2 master processes you would need 6 separate virtual/physical servers. 
This node has Docker pre-installed so you can run the containers in the pods.


## TODO 🎅
1. Install `minikube` as described [in step 1](https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download).
    > ⌚ It'll take 3-4 min.
2. Start Docker (it'll host `minikube` as a container on your local machine).
3. Create and start your cluster with Docker Driver.
    ```
    minkube start --driver docker
    ```
    You instruct `minikube` to use Docker as the underlying virtualization method to host the K8s components as containers.
    > ⌚ It'll take 4-5 min (it downloads images and components).
4. Run the following to ensure the components inside are running:
    ```
    minikube status
    ```
    If everything is running or configured, then

Congrats! You have created a local K8s cluster. There is nothing interesting in it though.. Or is [there](https://github.com/zezl7/esd-2024-kubernetes/tree/main/workshop/2_Interact_with_Cluster)? 👤
