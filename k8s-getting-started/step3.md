## Scale

### Set nuber of replicas

`kubectl scale deployment/thingsboard --replicas=3`{{execute}}

### See events

`kubectl get events`{{execute}}

### See number of running pods

This shows all the pods in the cluster

`kubectl get pods`{{execute}}

## Logs

Commands to see logs in the pods

### See logs

Run this command to see the logs of the app we named thingsboard

`kubectl logs -l app=thingsboard`{{execute}}

### See all containers logs

To see the logs on all containers:

`kubectl logs -l app=thingsboard --all-containers`{{execute}}

### See pods labels

Display the pods with their labels

`kubectl get pods --show-labels`{{execute}}
