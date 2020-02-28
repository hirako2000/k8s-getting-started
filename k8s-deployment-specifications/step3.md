### List the currently running nodes:

`kubectl get nodes`{{execute}}

### List the currently running nodes with Labels

`kubectl get nodes --show-labels`{{execute}}

### Add disktype Label to the minikube's node

`kubectl label nodes minikube disktype=ssd`{{execute}}

### Add environment Label to the minikube's node

`kubectl label nodes minikube environment=test`{{execute}}

### See the new labels added to the nodes

`kubectl get nodes --show-labels`{{execute}}

### Create dev-1 namespace via spec file

`kubectl apply -f ./dev-1-namespace.yaml`{{execute}}

### Create a naked pod using specification file

`kubectl apply -f ./thingsboard-naked-pod.yaml`{{execute}}

### See the naked pod is running

`kubectl get pods --namespace dev-1`{{execute}}

### See the event for the pod creation

`kubectl get events`{{execute}}

### Delete all the pod to clear out our node

`kubectl delete pod --all --namespace dev-1`{{execute}}
