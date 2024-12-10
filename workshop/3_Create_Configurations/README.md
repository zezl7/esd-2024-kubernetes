Wow, you have come so far ESDealer, this `third` assignment is about **configuring the database and webapp deployment on the K8s cluster**.

## INFO 💡
### `K8s configuration files`
`ConfigMap`: contains configuration data (e.g., database endpoint) used by multiple pods.

`Secret`: contains **base64 encoded** configuration data (e.g., login credentials) used by multiple pods.

`Deployment`: specifies pod creation.

`Service`: forwards requests to its endpoint pods based on a label, serves as a permament IP attached to a pod.


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
4. To add the `Service` configuration, create a separate yaml unit separated by `---` at the bottom of the [`database.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/database.yaml) file. There,
    - copy & paste the first service example from the [K8s documentation](https://kubernetes.io/docs/concepts/services-networking/service/),
    - change the name of the service to the previoulsy set `database-url` in the `configMap`,
    - change the app selector's value to the previously set app label value,
    - change the `targetPort` and `port` to the `containerPort`'s value (this is where the forwarding of the request should happen).
5. Copy the contents of [`database.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/database.yaml) and paste them in [`webapp.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/webapp.yaml) .
    - adjust the labels, names, and selector to a new string of your choice,
    - change the container image to `zezl7/esd-2024-kubernetes:latest`,
    - change all ports to `3000`.

Congrats! You have configured the database and webapp application and are one step closer to deploying the whole thing on the K8s cluster... Buut not quite yet. 💆 The [configuration data](https://github.com/zezl7/esd-2024-kubernetes/tree/main/workshop/4_Pass_Configuration_Data) needs to be passed.
