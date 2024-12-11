Heeeeey ESDealer, last one. This `seventh` assignment is about **interacting with the K8s cluster**.

## INFO 💡
### ``

## TODO 🎅
1. To see all components created in the cluster, run
    ```
    kubectl get all
    ```
You will see `pod/`, `service/`, `deployment/`, `replicaset/`.
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
    kubectl get svc # gets all services
```
7. To get the IP address of a node, run
```
    kubectl get node -o wide
```
8. Finally, you can access the application at the specified 30100 port with the external IP address from Step 7/30100.

Congratulations! You have finished this workshop. Thank you for your participation, if you made it thus far, send me a 🍍 via Teams.
