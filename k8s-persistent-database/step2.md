### Deploy the thingsboard webapp

First, make sure that postgres deployment is READY

`kubectl get deployments --namespace dev-1`{{execute}}

Also ensure that the CluserIP service is now created. Why? The thingsboard app will connect to the database at startup, if the database isn't running, the deployment will fail.

`kubectl get services --namespace dev-1`{{execute}}

Now you may deploy the thingsboard application

`kubectl apply -f ./thingsboard-deployment.yaml`{{execute}}

### Create a NodePort Service using specification file

Finally, we expose the web application externally:

`kubectl apply -f ./thingsboard-service.yaml`{{execute}}

### Access the Webapp from external network

With a web browser, access localhost on the port defined in the service (80)
In Katacode, `Select Port to view on Host 1` using the (+) menu item next to the Terminal tab
