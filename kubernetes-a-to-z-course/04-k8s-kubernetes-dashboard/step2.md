### Create namespace

`kubectl create -f ./kubernetes-dashboard-namespace.yaml`{{execute}}

### Create the roles and service account

Run this command to create the ServiceAccount, roles and binding resource for the dashboard

`kubectl create -f ./kubernetes-dashboard-role-binding.yaml`{{execute}}

### Metrics scrapper deployment

Deploy the metrics scraper:

`kubectl create -f ./kubernetes-dashboard-namespace.yaml`{{execute}}

### Metrics scrapper service

Create the metrics scraper service:

`kubectl create -f ./kubernetes-dashboard-metrics-scraper-service.yaml`{{execute}}

### Deploy the dashboard

Run this command to deploy the UI Dashboard

`kubectl create -f ./kubernetes-dashboard-deployment.yaml`{{execute}}

### Create the NodePort service

Run this command to create the NodePort service to route traffic:

`kubectl create -f ./kubernetes-dashboard-service.yaml`{{execute}}

### List secrets

Run this command to list all secrets for a given namespace:

`kubectl get secrets --namespace kubernetes-dashboard`{{execute}}

### Get the token

Now you may see the token for a particular secret, replace -xxxx with the secret id
`kubectl describe secret kubernetes-dashboard-token-xxxx --namespace kubernetes-dashboard`{{copy}}
