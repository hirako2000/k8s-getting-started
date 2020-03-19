### Deploy thingsboard persistent volume

`kubectl create -f ./postgres-conf-volume-deployment-service.yaml`{{execute HOST1}}

Wait for the deployment to be ready.

### Deploy thingsboard

First, make sure that postgres deployment is READY

`kubectl get deployments --namespace dev-1`{{execute HOST1}}

Now you may deploy the thingsboard application and service

`kubectl apply -f ./thingsboard-deployment-service.yaml`{{execute HOST1}}