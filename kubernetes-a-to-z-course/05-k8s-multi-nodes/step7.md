
### Deploy thingsboard persistent volume

Some Node Affinity properties were added to the persistent volume manifest:

```yaml
  nodeAffinity:
    required:
      nodeSelectorTerms:
      - matchExpressions:
        - key: performance
          operator: In
          values:
          - disk
```

This is so that Kubernetes creates the persistent volume on the disk optimized node, as per our defined label.

`kubectl create -f ./postgres-conf-volume-deployment-service.yaml`{{execute HOST1}}

### Deploy thingsboard

First, make sure that postgres deployment is READY

`kubectl get deployments --namespace dev-1`{{execute HOST1}}

Now you may deploy the thingsboard application and service

`kubectl apply -f ./thingsboard-deployment-service.yaml`{{execute HOST1}}