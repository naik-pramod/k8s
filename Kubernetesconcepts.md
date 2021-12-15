### Kubernetes concepts

 ![arch](/images/arch.png "arch")

 #### Cluster
 A cluster is a collection of compute, storage, and networking resources that Kubernetes uses to run the various workloads that comprise your system.

#### Node
A node is a single host. It may be a physical or virtual machine. Its job is to run pods.

#### Master
The master is the control plane of Kubernetes. 
It consists of several components, such as an API server, a scheduler, and a controller manager.

#### Pod
A pod is the unit of work in Kubernetes. 
Each pod contains one or more containers.
All the containers in a pod have the same IP address and port space.

#### Label
Labels are key-value pairs that are used to group together sets of objects, such as pods.

#### Annotations
Annotations let you associate arbitrary metadata with Kubernetes objects. 
Kubernetes just stores the annotations and makes their metadata available. 
Unlike labels, they don't have strict restrictions about allowed characters and size limits.

#### Label selectors
Label selectors are used to select objects based on their labels.
There are two operators, = (or ==) and !=, to denote equality or inequality based on the value.
`role = webserver`

`role = webserver, application != foo`

#### Replication controllers and replica sets
Replication controllers and replica sets both manage a group of pods identified by a label selector and ensure that a certain number is always up and running.
Replica sets are the way to go, as they are a superset of replication controllers.

#### Services
Services are used to expose a certain functionality to users or other services. 
They usually encompass a group of pods, usually identified by a label.

#### Volume
Local storage on the pod is ephemeral and goes away with the pod. 
Sometimes it's important for the data to outlive the pod, or it's necessary to share data between pods. The volume concept supports that need. 

Note that, while Docker has a volume concept too, it is quite limited. Kubernetes uses its own separate volumes

#### StatefulSet
Sometimes you might want Kubernetes to manage a distributed data store, such as Kubernetes or MySQL Galera. 
These clustered stores keep the data distributed across uniquely identified nodes.
You can't model that with regular pods and services.

#### Secrets
Secrets are small objects that contain sensitive information, such as credentials and tokens. 
They are stored in etcd, are accessible by the Kubernetes API server, and can be mounted as files into pods

#### Names
Each object in Kubernetes is identified by a UID and a name. 
The name is used to refer to the object in API calls.

Names should be up to 253 characters long and use lowercase alphanumeric characters, dashes (-), and dots (.). 
If you delete an object, you can create another object with the same name as the deleted object.

#### Namespaces
A namespace is a virtual cluster. 
You can have a single physical cluster that contains multiple virtual clusters segregated by namespaces.
