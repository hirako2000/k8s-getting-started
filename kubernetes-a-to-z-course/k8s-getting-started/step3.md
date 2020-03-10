## Scale

We will explore how to scale up the number of running application using replicas, via the command line.

### Set number of replicas

Run this command to set the number of replica:

`kubectl scale deployment/thingsboard --replicas=3`{{execute}}

Kubernetes takes care of add a number of pods to the deployment.

### See events

Run this command to see the event received and executed by Kubernetes:

`kubectl get events`{{execute}}

### See number of running pods

This command shows all the pods in the cluster:

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

Display the pods with their labels:

`kubectl get pods --show-labels`{{execute}}
