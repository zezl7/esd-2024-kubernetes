This `fifth` assignment is about **exposing the app to the outside world**.

## INFO 💡
### `Service`
By default, services are internal and carry the `type: ClusterIP`.

## TODO 🎅
1. In the [`webapp.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/webapp.yaml) add a `type: NodePort` just before the `selector`. This makes the service **external**.
2. `NodePort` requires a third port after `targetPort`, namely `nodePort`. The idea is to have each Node's IP exposing the `service`, which in turn exposes the `deployment`.
> The `nodePort` is in a range [30000-32767](https://kubernetes.io/docs/concepts/services-networking/service/). Choose one you like 🎄.


Congrats! You have taken care of exposing the app to the outside world. Now go [deploy all resources](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/6_Deploy_App) to the K8s cluster 🔍.
