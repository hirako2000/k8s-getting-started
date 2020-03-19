The two nodes in the cluster should now be Ready. This means that our deployments can be scheduled and launched.

## Deploy Kubernetes (UI) Dashboard

We will now deploy the kubernetes dashboard

### Deploy

Run these commands to create all the dashboard objects

First the namespaces:

`kubectl create -f ./namespaces.yaml`{{execute HOST1}}

And the dashboard and metrics scrapper:

`kubectl create -f ./kubernetes-dashboard-all.yaml`{{execute HOST1}}

### List secrets

Run this command to list all secrets for the given namespace:

`kubectl get secrets --namespace kubernetes-dashboard`{{execute HOST1}}

### Get the token

Now you may see the token for a particular secret, replace -xxxx with the secret id
`kubectl describe secret kubernetes-dashboard-token-xxxx --namespace kubernetes-dashboard`{{copy}}

### Open the dashboard

https://[[HOST_SUBDOMAIN]]-32000-[[KATACODA_HOST]].environments.katacoda.com/
