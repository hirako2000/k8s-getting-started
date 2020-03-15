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

### List secrets

Run this command to list all secrets for a given namespace:

`kubectl get secrets --namespace kube-system`{{execute}}

### Get the token

Now you may see the token for a particular secret, replace -xxxx with the secret id
`kubectl describe secret kubernetes-dashboard-token-xxxx --namespace kube-system`{{copy}}
