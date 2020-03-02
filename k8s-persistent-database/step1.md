### Start Cluster

The first step is to start the cluster:

`minikube start`{{execute}}

### Create postgres config map

Creates the configmap for postgres:

`kubectl create -f ./postgres-configmap.yaml`{{execute}}

### See the configmap values:

`kubectl get configmap --namespace dev-1`{{execute}}

### Create postgres persistent volume

Then create the persistent volume for the postgres data

`kubectl create -f ./postgres-persistent-volume.yaml`{{execute}}

### Deploy postgres

Now deploy postgres

`kubectl create -f ./postgres-deployment.yaml`{{execute}}

### Create service to expose postgres

We need to expose postgres, via a ClusterIP service to make it accessible within the cluster only:

`kubectl create -f ./postgres-service.yaml`{{execute}}
