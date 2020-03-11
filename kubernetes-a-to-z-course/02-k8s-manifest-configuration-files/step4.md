### Create a deployment using a manifest configuration file

Here is the thingsboard deployment manifest content:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: thingsboard-deployment
  namespace: dev-1
spec:
  selector:
    matchLabels:
      app: thingsboard
  replicas: 3
  template:
    metadata:
      labels:
        app: thingsboard
    spec:
      containers:
        - name: thingsboard-tb
          image: thingsboard/tb
```

The `thingsboard-deployment.yaml` file was conveniently placed in the current path.

So just run this command:

`kubectl apply -f ./thingsboard-deployment.yaml`{{execute}}

### See deployment

`kubectl get deployment --namespace dev-1`{{execute}}

### See pods

`kubectl get pods --namespace dev-1`{{execute}}
