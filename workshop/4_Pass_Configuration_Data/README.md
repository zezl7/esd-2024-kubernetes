You are halfway there ESDealer, this `fourth` assignment is about **passing configuration data to the database & webapp deployments**.

## INFO 💡
### `K8s configuration files`
`ConfigMap`: contains configuration data (e.g., database endpoint) used by multiple pods.

`Secret`: contains **base64 encoded** configuration data (e.g., login credentials) used by multiple pods.


## TODO 🎅
1. The data defined in [`database-secret.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/database-secret.yaml) and [`database-config.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/database-config.yaml) needs to be passed to the pods. In [`database.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/database.yaml) the username and password propmpted at start of the database need to be specified.
    - after the `ports` section in the deployment, add 
    ```
    env:
    - name: MONGO_INITDB_ROOT_USERNAME
      valueFrom:
        secretKeyRef:
          name: database-secret
          key: database-user
    ```
    This'll reference the values from the [`database-secret.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/database-secret.yaml).
3. Do the same for the password, the environemnt name is `MONGO_INITDB_ROOT_PASSWORD`.
4. When the web app starts, it requires connection to the database. In [`webapp.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/webapp.yaml) add the same code blocks as the previous two. With the respective names `USER_NAME`, `USER_PWD`.
5. One more environment variable is needed for [`webapp.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/webapp.yaml), namely `DB_URL` to reference the database access. For this, add the following code block after `USER_PWD`:
    ```
    - name: DB_URL
      valueFrom:
        configMapKeyRef:
          name: 
          key: database-url
    ```
    For `name` enter the `configMap` name you specified in the [`database-config.yaml`](https://github.com/zezl7/esd-2024-kubernetes/blob/main/workshop/3_Create_Configurations/database-config.yaml) file.

Congrats! You have taken care of referencing all configuration data. There is one more thing to do before the web app is up and running...
