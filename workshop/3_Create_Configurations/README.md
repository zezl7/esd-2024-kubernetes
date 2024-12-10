Wow, you have come so far ESDealer, this `third` assignment is about **configuring a deployment of a web app to the K8s cluster**.

## INFO 💡
### `K8s configuration files`
`ConfigMap`: contains configuration data (e.g., database endpoint) used by multiple pods.

`Secret`: contains **base64 encoded** configuration data (e.g., login credentials) used by multiple pods.

`Deployment`: specifies pod creation.

`Service`: a permament IP attached to a pod.


## TODO 🎅
1. In [`database-config.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/database-config.yaml), specify a name for the configmap and the service.
2. In [`database-secret.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/database-secret.yaml), 
    - specify a name for the secret,
    - select your own username and password.
        > 🚧 read the `Secret` part above.
3. The file [`database.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/database.yaml) is empty. Copy the contents of the `nginx-deployment.yaml` file from [the K8s documention](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) to this file. Here, both `deployment` and `service` are entailed. The former is dependent on the latter. The `specification` section has deployment specific configuration, the `template` configures the **pod** within the deployment.
    - change the image for the pod to `mongo:8.0`,
    - rename the container,
    - change the port to the mongodb one `27017`,
    - change the app labels' values to another string to group the pods by,
    - change the name of the deployment,
    - change the `replicas` to 1, since databases require a `StatefulSet` in K8s, not a deployment.

Congrats! You have created the configuration files and are one step closer to deploying the web app on the K8s cluster. 
