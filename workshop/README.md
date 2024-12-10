Hi there, this workshop is about **creating a local K8s cluster**.

# Set-up of `Minikube` & `kubectl`

### `Minikube`
`Obective`: create a virtual **node** on your local machine.

>Minikube is a `one-node` cluster where the master & worker processes run on one node (=machine / =server). Normally, each worker process and each master process gets their own server. E.g., if you have 4 worker processes and 2 master processes you would need 6 separate virtual/physical servers. 
This node has Docker pre-installed so you can run the containers in the pods.

---

### `kubectl`
`Objective`: **interact** with cluster to create pods and other components (e.g., _Service_, _Secret_, _ConfigMap_) on that node.

> Kubectl is a `comand line tool` for K8s clusters. It submits commands to the API server (a master node process, main entrypoint) in order to interact with cluster (e.g., create/delete components). The work processes will executing the commands.
---
