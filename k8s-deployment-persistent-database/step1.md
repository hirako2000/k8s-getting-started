### Create Cluster

`minikube start`{{execute}}

### Create postgres config map

`kubectl create -f postgres-configmap.yaml`{{execute}}

### Create postgres persistent volume

`kubectl create -f postgres-persistent-volume.yaml`{{execute}}

### Deploy postgres

`kubectl create -f postgres-deployment.yaml`{{execute}}

### Create service to expose postgres

`kubectl create -f postgres-service.yaml`{{execute}}
