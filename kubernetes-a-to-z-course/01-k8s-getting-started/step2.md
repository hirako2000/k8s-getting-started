### Create deployment

Run this command to create a deployment using the standalone thingsboard Docker image

`kubectl create deployment thingsboard --image=thingsboard/tb`{{execute}}

### Get Deployment

See information about the existing deployment, you shall see the thingsboard deployment you've just created

`kubectl get deployments`{{execute}}

### See Kubernetes Events

Take a look at the events handled by kubernetes

`kubectl get events`{{execute}}

See the creation of the deployment at the end of the output.

### Expose port

Expose the deployment to external traffic using a NodePort service

`kubectl expose deployment thingsboard --type=NodePort --name=thingsboard-nodeport --port=9090 --target-port=9090`{{execute}}
