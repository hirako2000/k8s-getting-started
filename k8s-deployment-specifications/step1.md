### Create Cluster

`minikube start`{{execute}}

### List default namespaces in the cluster

`kubectl get namespaces`{{execute}}

### See pods running in the kube-system namespace

`kubectl get pods -n kube-system; echo`{{execute}}

### See pods running in the kube-public namespace

`kubectl get pods -n kube-public; echo`{{execute}}

### See cluster-info's configmap on the kube-public namespace

`kubectl get configmap -n kube-public cluster-info -o yaml; echo`{{execute}}
