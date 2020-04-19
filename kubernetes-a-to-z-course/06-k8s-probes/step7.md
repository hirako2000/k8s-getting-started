
### Deploy thingsboard persistent volume

`kubectl create -f ./postgres-conf-volume-deployment-service.yaml`{{execute HOST1}}

### Deploy thingsboard

First, make sure that postgres deployment is READY

`kubectl get deployments --namespace dev-1`{{execute HOST1}}

Now you may deploy the thingsboard application and service

`kubectl create -f ./thingsboard-deployment-service.yaml`{{execute HOST1}}

### Open ThingsBoard app

https://[[HOST_SUBDOMAIN]]-32001-[[KATACODA_HOST]].environments.katacoda.com/