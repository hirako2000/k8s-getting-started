## Scale

### Set nuber of replicas

`kubectl scale deployment/thingsboard --replicas=3`{{execute}}

### See events

`kubectl get events`{{execute}}

### See number of running pods

`kubectl get pods`{{execute}}

## Logs

### See logs

`kubectl logs -l app=thingsboard`{{execute}}

### See all containers logs

`kubectl logs -l app=thingsboard --all-containers`{{execute}}

### See pods labels

`kubectl get pods --show-labels`{{execute}}
