Before we get started, you need start a cluster with minikube.

### Create Cluster

From the Terminal, run:

`minikube start`{{execute}}

### Check kubectl's version

Use kubectl to check the version of the client and server

`kubectl version`{{execute}}

### Get cluster information

See information about the cluster

`kubectl cluster-info`{{execute}}

### Get nodes

See information about the node. In minikube, only one node is running

`kubectl get nodes`{{execute}}
