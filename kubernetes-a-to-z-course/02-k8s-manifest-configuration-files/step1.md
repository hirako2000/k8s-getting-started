### Create Cluster

We first start the cluster:

`minikube start`{{execute}}

### List default namespaces in the cluster

Run this command to list the already existing namespaces:

`kubectl get namespaces`{{execute}}

### See pods running in the kube-system namespace

This command lists the pods running within the kube-system namespace:

`kubectl get pods -n kube-system; echo`{{execute}}

### See pods running in the kube-public namespace

Now run this command to see the pods running in the kube-public namespace:

`kubectl get pods -n kube-public; echo`{{execute}}

### See cluster-info's configmap on the kube-public namespace

And to see the configmap in the kube-public namespace:

`kubectl get configmap -n kube-public cluster-info -o yaml; echo`{{execute}}
