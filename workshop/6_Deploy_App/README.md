This `sixth` assignment is about **deploying all resources in the K8 cluster**.

## INFO 💡
### `Service`
By default, services are internal and carry the `type: ClusterIP`.

## TODO 🎅
1. Create `configMap` and `secret` with 
```
kubectl apply -f database-config.yaml
kubectl apply -f database-secret.yaml
```
> Remember to change to the repo containing the files.
2. Create the database with 
```
kubectl apply -f database.yaml
```
3. Create the webapp with 
```
kubectl apply -f webapp.yaml
```

Congrats! You have deployed the configuration scripts to the cluster. The [next assignment](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/7_Interact_with_deployed_Cluster) is the last one, so you are almost done. 🎓
