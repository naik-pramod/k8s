### Resource Categories
Kubernetes defines the following resource categories:

- Workloads: The objects you use to manage and run containers on the cluster.
- Discovery and load balancing: The objects you use to expose your workloads to the world as externally accessible, load-balanced services.
- Config and storage: The objects you use to initialize and configure your applications, and to persist data that is outside the container.
- Cluster: The objects that define how the cluster itself is configured; these are typically used only by cluster operators.
- Metadata: The objects you use to configure the behavior of other resources within the cluster, such as HorizontalPodAutoscaler for scaling workloads.

#### Workloads API
The workloads API contains the following resources:

- Container: **Core**
- CronJob: **Batch**
- DaemonSet: **Apps**
- Deployment: **Apps**
- Job: **Batch**
- Pod: **Core**
- ReplicaSet: **Apps**
- ReplicationController: **Core**
- StatefulSet: **Apps**

`GET /api/v1/pods `

#### Discovery and load balancing
By default, workloads are only accessible within the cluster, and they must be exposed externally using either a LoadBalancer or NodePort service.

- Endpoints: **Core**
- Ingress: **Extensions**
- Service: **Core**

#### Config and storage
Dynamic configuration without redeployment is a cornerstone of Kubernetes and running complex distributed applications on your Kubernetes cluster:

- ConfigMap: **Core**
- Secret: **Core**
- PersistentVolumeClaim: **Core**
- StorageClass: **Storage**
- VolumeAttachment: **Storage**


#### Metadata
The metadata resources typically are embedded as subresources of the resources they configure. 
For example, a limit range will be part of a pod configuration. You will not interact with these objects directly most of the time. There are many metadata resources. 


#### Cluster
The resources in the cluster category are designed for use by cluster operators as opposed to developers. 
Here some of the most important resources:

- Namespace: **Core**
- Node: **Core**
- PersistentVolume: **Core**
- ResourceQuota : **Core**
- ClusterRole: **Rbac**
- NetworkPolicy : **Networking**