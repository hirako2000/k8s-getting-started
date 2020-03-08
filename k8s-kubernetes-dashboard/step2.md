### Create the ServiceAccount

Run this command to create the ServiceAccount resource for the dashboard

`kubectl create -f ./kubernetes-dashboard-service-account.yaml`{{execute}}

### Create the cluster binding

Run this command to bind the role to this cluster

`kubectl create -f ./kubernetes-dashboard-cluster-binding.yaml`{{execute}}

### Deploy the dashboard

Run this command to deploy the UI Dashboard

`kubectl create -f ./kubernetes-dashboard-deployment.yaml`{{execute}}

### Create the NodePort service

Run this command to create the NodePort service to route traffic:

`kubectl create -f ./kubernetes-dashboard-service.yaml`{{execute}}
