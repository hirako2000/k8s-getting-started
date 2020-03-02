### Create a namespace via command line

Run this command to create a `dev-1` namespace:

`kubectl create namespace dev-1`{{execute}}

### Create a namespace via spec file

Here is the dev-2 namespace manifest content:

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: dev-2
```

The `dev-2-namespace.yaml` file was conveniently placed in the current path.

Run this command to create a `dev-2` namespace, via manifest file:

`kubectl apply -f ./dev-2-namespace.yaml`{{execute}}

### Check both namespaces were created

List the namespaces in the cluster:

`kubectl get namespaces`{{execute}}

### Delete a workspace via command line

Delete the `dev-1` namespace:

`kubectl delete namespace dev-1`{{execute}}

### Delete a workspace via manifest file

And delete the `dev-2` namespace via manifest file:

`kubectl delete -f ./dev-2-namespace.yaml`{{execute}}

### Check the namespaces were deleted

List the namespaces in the cluster again to see the `dev-x` namepaces are deleted:
`kubectl get namespaces`{{execute}}
