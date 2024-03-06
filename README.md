# Kubernetes cheat sheet

A list of useful commands, params etc. for the Kubernetes CLI using kubectl.

**Apply/configure from definitions**

The *apply* command is used to deploy/configure or as the name suggests, apply the YML definitions
to k8s. Within the definition file it will state the kind or type of definition, i.e. pod, deployment etc.

| Command | Description |
|---------|-------------|
| kubectl apply -f &lt;definition-yml&gt; | Configures k8s using hte supplied file |
| kubectl run &lt;pod name&gt; --image=&lt;image name&gt; | Deploys and application to the cluster |
| kubectl apply -f &lt;definition-yml&gt; --dry-run=*lt | Configures k8s using hte supplied file |

**Get**

| Command | Description |
|---------|-------------|
| kubectl get all | Gets all objects |
| kubectl get &lt;object type&gt; | Gets the current running objects of given type, i.e. pods, services, nodes etc. |

**Delete**

| Command | Description |
|---------|-------------|
| kubectl delete &lt;object type&gt; &lt;name&gt; | Delete a given object with the given name |

**Logs/Events**

| Command | Description |
|---------|-------------|
| kubectl logs &lt;pod name&gt; | View logs for a pod |
| kubectl get events | Get the cluster events |


**Rolling updates**

| Command | Description |
|---------|-------------|
| kubectl set image &lt;container name&lt;=&lt;new container version&gt; | Perform a rolling update by switching the image |
| kubectl rollout status &lt;container name&lt; | Check the status of a rolling update |
| kubectl rollout history &lt;container name&lt; | Check the history of a rolling update |
| kubectl rollout undo &lt;container name&lt; | Rollback an update |

**View/Edit YAML definitions**

| Command | Description |
|---------|-------------|
| kubectl get &lt;object type&gt; &lt;name&gt; -o &lt;output format&gt; | Outputs the deployed type (i.e. service, deployment etc.) to a format such as YAML, JSON |
| kubectl edit &lt;object type&gt; &lt;name&gt; | Edit a type, i.e. deployment  |

**ReplicaSets**

| Command | Description |
|---------|-------------|
| kubectl replace -f &lt;definition-yml&gt; | Change a replicaset |
| kubectl scale --replicas=&ltnumber&gt; replicaset &lt;replicaset name&gt; |


**Information**

| Command | Description |
|---------|-------------|
| kubectl cluster-info | Gets information about the cluster |
| kubectl describe &lt;object type&gt; &lt;name&gt; | Describes the currently deployed object |
| kubectl top &lt;object type&gt; | See resource consumptions of objects |

**Object Types**

*This is not an exhaustive list of object types (at this time)*

| Command | Description |
|---------|-------------|
| pod | A pod is the most basic type of object |
| service | A service is essentially an way of accessing a resource |
| deployment | A deployment |
| configMap | A configMap supplies extra configuration, for example a DB init script |
| ingress | An ingress service is a load balancer type |
| namespace | A namespace |
| serviceaccount | Your service account |
| hpa | Horizontal Pod Autoscaler |

## Use with different objects

These are really just examples of using the previous command against specific object types, such as deployments, pods etc. This is not an exhaustive list.

**Deployments**

| Command | Description |
|---------|-------------|
| kubectl get deployments | Get deployment objects |
| kubectl describe deployment &lt;deployment name&gt; | Describe the deployment |
| kubectl delete deployment &lt;deployment name&gt; | Delete the deployment |
| kubectl edit deployment &lt;deployment name&gt; | Delete the deployment |
| kubectl get deployment &lt;deployment name&gt; -o yaml | Generate the deployment as YAML |

**Services**

| Command | Description |
|---------|-------------|
| kubectl get services | Get service objects |
| kubectl describe service &lt;service name&gt; | Describe the service |
| kubectl delete service &lt;service name&gt; | Delete the service |
| kubectl edit service &lt;service name&gt; | Delete the service |
| kubectl get service &lt;service name&gt; -o yaml | Generate the service as YAML |

**Pods**

| Command | Description |
|---------|-------------|
| kubectl get pods | Get pod objects |
| kubectl describe pod &lt;pod name&gt; | Describe the pod |
| kubectl delete pod &lt;pod name&gt; | Delete the pod |
| kubectl edit pod &lt;pod name&gt; | Delete the pod |
| kubectl get pod &lt;pod name&gt; -o yaml | Generate the pod as YAML |

**Ingress**

| Command | Description |
|---------|-------------|
| kubectl get ingress | Get ingress objects |
| kubectl describe ingress &lt;ingress name&gt; | Describe the ingress |
| kubectl delete ingress &lt;ingress name&gt; | Delete the ingress |
| kubectl edit ingress &lt;ingress name&gt; | Delete the ingress |
| kubectl get ingress &lt;ingress name&gt; -o yaml | Generate the ingress as YAML |

**Service Accounts**

| Command | Description |
|---------|-------------|
| kubectl get serviceaccount | Get service account objects |
| kubectl describe serviceaccount &lt;serviceaccount name&gt; | Describe the service account |
| kubectl delete serviceaccount &lt;serviceaccount name&gt; | Delete the service account |
| kubectl edit serviceaccount &lt;serviceaccount name&gt; | Delete the service account |
| kubectl get serviceaccount &lt;serviceaccount name&gt; -o yaml | Generate the service account as YAML |