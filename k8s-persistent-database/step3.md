Let's verify the volume actually persists the database.
To do so, we will use the web application to modify the database, and verify that those changes persist after redeployment of the entire cluster.

### Delete a widget through the web app interface

In the thingsboard interface, go to Widgets Library, and delete the **Chart** widget.

### Delete all the namespace

`kubectl delete -f ./dev-1-namespace.yaml`{{execute}}

This will delete all resources associated with this namespace. All sevices, deployments, pods, and persistent volumes from the cluster

### Stop the cluster

`minikube stop`{{execute}}

Wait until all the resources are actually deleted and the cluster stopped, this may take a minute.
