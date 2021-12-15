Master components
- **The API server**
  *Exposes the Kubernetes REST API*
- **Etcd**
  *Is a distributed data store, used to store entire cluster state*
- **Kube controller manager**
  *Is a collection of various managers combined into single binary - replication controller, pod controller, services controller, endpoint controller. Watches the cluster state and steer it to the desired state*
- **cloud controller managers**
  *Allows cloud providers to integrate and manage nodes, volumes, services*
- **kube-scheduler**
  *Resposible for scheduling pods into nodes*
- **DNS**
  *Is a Service, and scheudled as pod. Every service and pod recieves DNS name. Useful for automatic discovery*

  
