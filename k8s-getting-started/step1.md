The first step of this scenario is to create a cluster, using minikube.

### Create Cluster

From the Terminal, run:

`minikube start`{{execute}}

### Check kubectl's version

Use kubectl to see the version of kubectl.

`kubectl version`{{execute}}

The output also includes the version of the kubernetes server

### Get cluster information

See information about the cluster:

`kubectl cluster-info`{{execute}}

### Get nodes

Run this commmand to get information about the node. In minikube, only one node is running:

`kubectl get nodes`{{execute}}
