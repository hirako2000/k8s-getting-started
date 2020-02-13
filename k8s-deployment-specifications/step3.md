### List the currently running nodes:

`kubectl get nodes`{{execute}}

### Add Label to the minikube's node

`kubectl label nodes minikube disktype=ssd`{{execute}}

### Create a naked pod using specification file

`kubectl apply -f ./thingsboard-naked-pod.yaml`{{execute}}

### See the naked pod is running

`kubectl get pods`{{execute}}

### See the event for the pod creation

`kubectl get events`{{execute}}

### Delete all the pod to clear out our node

`kubectl delete pod --all` {{execute}}
