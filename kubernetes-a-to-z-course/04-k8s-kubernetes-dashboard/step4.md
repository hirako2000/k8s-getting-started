## Deploy Kubernetes (UI) Dashboard

We will now deploy the kubernetes dashboard

### Deploy

Run these commands to create all the dashboard objects

`kubectl create -f ./kubernetes-dashboard-metrics-scraper-all.yaml`{{execute}}
`kubectl create -f ./kubernetes-dashboard-all.yaml`{{execute}}

### List secrets

Run this command to list all secrets for the given namespace:

`kubectl get secrets --namespace kubernetes-dashboard`{{execute}}

### Get the token

Now you may see the token for a particular secret, replace -xxxx with the secret id
`kubectl describe secret kubernetes-dashboard-token-xxxx --namespace kubernetes-dashboard`{{copy}}
