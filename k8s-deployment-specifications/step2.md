### Create a namespace via command line

`kubectl create namespace dev-1`{{execute}}

### Create a namespace via spec file

`kubectl apply -f ./dev-2-namespace.yaml`{{execute}}

### Check both namespaces were created

`kubectl get namespaces`{{execute}}

### Delete a workspace via command line

`kubectl delete namespace dev-1`{{execute}}

### Delete a workspace via via spec file

`kubectl delete -f ./dev-2-namespace.yaml`{{execute}}

### Check the namespaces were deleted

`kubectl get namespaces`{{execute}}
