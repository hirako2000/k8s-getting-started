### Add Label to the minikube's node

`kubectl label nodes minikube disktype=ssd`{{execute}}

### Create a naked pod using specification file

`kubectl apply -f ./thingsboard-naked-pod.yaml`{{execute}}

### Delete Naked pod

`kubectl delete pod --all` {{execute}}

### Create a deployment using specification file

`kubectl apply -f ./thingsboard-deployment.yaml`{{execute}}
