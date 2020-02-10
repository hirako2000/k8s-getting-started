### Label the minikube's node

`kubectl label nodes minikube disktype=ssd`{{execute}}

### Creates a naked pod using specification file

`kubectl apply -f ./thingsboard-naked-pod.yaml`{{execute}}

### Creates a deployment using specification file

`kubectl apply -f ./thingsboard-deployment.yaml`{{execute}}
