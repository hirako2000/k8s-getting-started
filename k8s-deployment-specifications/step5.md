### Create a NodePort Service using specification file

`kubectl apply -f ./thingsboard-service.yaml`{{execute}}

### See the service

`kubectl get services`{{execute}}

### Access the Webapp from external network

With a web browser, access localhost on the port defined in the service (80)
In Katacode, `Select Port to view on Host 1` using the (+) menu item next to the Terminal tab
