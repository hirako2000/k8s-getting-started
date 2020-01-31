
### Create deployment
`kubectl create deployment thingsboard --image=thingsboard/tb`{{execute}}

### Expose port
`kubectl expose deployment thingsboard --type=NodePort --name=thingsboard-clusterip --port=9090 --target-port=9090`{{execute}}