Let's verify the volume actually persists the database.
To do so, we will use the web application to modify the database, and verify that those change persist after redeployment of the entire cluster.

### Delete a widget through the web app interface

In the thingsboard interface, go to Widgets Library, and delete the Chart widget.

### Delete all deployments and services

`kubectl delete all --all --namespace dev-1`{{execute}}

### Delete the persistent volume

`kubectl delete -f ./postgres-persistent-volume.yaml`{{execute}}

### Stop the cluster

`minikube stop`{{execute}}

Wait until all the resources are actually deleted and the cluster stopped, this may take a minute.
