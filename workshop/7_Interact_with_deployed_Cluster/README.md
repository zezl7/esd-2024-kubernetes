Heeeeey ESDealer, last one. This `seventh` assignment is about **interacting with the K8s cluster**.

## TODO 🎅
1. To see all components created in the cluster, run
    ```
    kubectl get all
    ```
You will see `pod/`, `service/`, `deployment/`, `replicaset/`. You will also see `ContainerCreating`, this will changes to `Running` in 1-2 min.

2. To see `configMap` and `secret`, run
    ```
    kubectl get configmap
    kubectl get secret
    ```
3. To see the pods,
```
    kubectl get pod
```
4. To see more details about a certain component,
```
    # example
    kubectl describe service webapp-service
    kubectl describe pod podName
```
5. To see the pod logs, run
```
    kubectl logs podName
```
6. To see all services, run
```
    kubectl get svc
```
7. To see the web app, run
```
    minikube service webapp-service
```
8. To delete the cluster, run
```
    minikube delete --all
```

Congratulations! You have finished this workshop. Thank you for your participation, if you made it thus far, send me a 🍍 via Teams.
