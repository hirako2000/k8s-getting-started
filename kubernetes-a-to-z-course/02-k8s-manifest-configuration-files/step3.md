### List the currently running nodes:

This command lists the existing nodes in the cluster. With minikube, there is only one node:

`kubectl get nodes`{{execute}}

### List the currently running nodes with Labels

Adding the `--show-labels` option shows the labels set on the nodes:

`kubectl get nodes --show-labels`{{execute}}

### Add disktype Label to the minikube's node

Run this command to add a `disktype` label to the minikube node. The value is ssd, as an indicuation that this node runs on an ssd drive:

`kubectl label nodes minikube disktype=ssd`{{execute}}

### Add environment Label to the minikube's node

Now let's add another label, called `environment`, we set it as `test` to indicate this node is just a test enviroment node:

`kubectl label nodes minikube environment=test`{{execute}}

### See the new labels added to the nodes

List the labels set on the node again, you shall see the newly added labels:

`kubectl get nodes --show-labels`{{execute}}

### Create dev-1 namespace via spec file

Here is the dev-1 namespace manifest content:

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: dev-1
```

Let's create again the `dev-1` namespace we had deleted earlier. The `dev-1-namespace.yaml` file is conveniently already placed into your current path, here is its content:

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: dev-1
```

Run this command to create that namespace:

`kubectl apply -f ./dev-1-namespace.yaml`{{execute}}

We will create all the resources in this Scenario in the `dev-1` namespace.

### Create a naked pod using specification file

Run this command to create a Naked pod from the manifest file:

`kubectl apply -f ./thingsboard-naked-pod.yaml`{{execute}}

### See the naked pod is running

`kubectl get pods --namespace dev-1`{{execute}}

### See the event for the pod creation

`kubectl get events --namespace dev-1`{{execute}}

### Delete all the pod to clear out our node

`kubectl delete pod --all --namespace dev-1`{{execute}}
