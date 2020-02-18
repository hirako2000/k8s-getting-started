### Create deployment

`kubectl create deployment thingsboard --image=thingsboard/tb`{{execute}}

### Get Deployment

`kubectl get deployments`{{execute}}

### See Kubernetes Events

`kubectl get events`{{execute}}

### Expose port

`kubectl expose deployment thingsboard --type=NodePort --name=thingsboard-nodeport --port=9090 --target-port=9090`{{execute}}
