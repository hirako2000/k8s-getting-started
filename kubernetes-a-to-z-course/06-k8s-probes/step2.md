### Create namespaces

`kubectl create -f ./namespaces.yaml`{{execute HOST1}}

### Deploy persistent volume and postgres

`kubectl create -f ./postgres-conf-volume-deployment-service.yaml`{{execute HOST1}}

### Deploy ThingsBoard

`kubectl create -f ./thingsboard-deployment-service.yaml`{{execute HOST1}}
