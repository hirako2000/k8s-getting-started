We will now recreate the entire cluster

### Start the cluster

`minikube start`{{execute}}

### Create postgres persistent volume

`kubectl create -f postgres-persistent-volume.yaml`{{execute}}

### Deploy postgres

`kubectl create -f postgres-deployment.yaml`{{execute}}

### Create service to expose postgres

`kubectl create -f postgres-service.yaml`{{execute}}

Note that the ClusterIP is now assigned a different IP.
It is fine, the application looksup the database hostname by the service name (tb-dabase), so everything will resolve just fine.

See the ClusterIP service:

`kubectl get services`{{execute}}

Then deploy the thingsboard webapp

`kubectl apply -f ./thingsboard-deployment.yaml`{{execute}}

### Create the NodePort Service

Finally, we expose the web application externally:

`kubectl apply -f ./thingsboard-service.yaml`{{execute}}

### Access the Webapp from external network

With a web browser, access localhost on the port defined in the service (80)
In Katacode, `Select Port to view on Host 1` using the (+) menu item next to the Terminal tab

Login, go to the Widget Library and observe the Charts is still not showing :)
