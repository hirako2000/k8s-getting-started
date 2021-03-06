### Start Cluster

The first step is to start the cluster:

`minikube start`{{execute}}

### Create namespace

Now we create our usual dev-1 namespace:

`kubectl apply -f ./dev-1-namespace.yaml`{{execute}}

### Create postgres config map

Here is the configmap manifest content:

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: postgres-config
  namespace: dev-1
  labels:
    app: postgres
data:
  POSTGRES_DB: thingsboarddb
  POSTGRES_USER: thingsboard
  POSTGRES_PASSWORD: thingsboard
  SPRING_DATASOURCE_URL: jdbc:postgresql://${TB_DATABASE_SERVICE_HOST}:${TB_DATABASE_SERVICE_PORT}/thingsboarddb
  SPRING_DATASOURCE_USERNAME: thingsboard
  SPRING_DATASOURCE_PASSWORD: thingsboard
```

Create the configmap for postgres:

`kubectl create -f ./postgres-configmap.yaml`{{execute}}

### See the configmaps:

`kubectl get configmap --namespace dev-1`{{execute}}

### See the configmaps manifest:

`kubectl get configmap --namespace dev-1 -o yaml`{{execute}}

### Create postgres persistent volume

Then create the persistent volume for the postgres data

`kubectl create -f ./postgres-persistent-volume.yaml`{{execute}}

### See the created persited volume

`kubectl get persistentvolumes --namespace dev-1`{{execute}}

### Create postgres persistent volume claim

Then create the persistent volume claim:

`kubectl create -f ./postgres-persistent-volume-claim.yaml`{{execute}}

### See the created persited volume claim

`kubectl get persistentvolumes --namespace dev-1`{{execute}}

### Deploy postgres

Now deploy postgres

`kubectl create -f ./postgres-deployment.yaml`{{execute}}

### Create service to expose postgres

We need to expose postgres, via a ClusterIP service to make it accessible within the cluster only:

`kubectl create -f ./postgres-service.yaml`{{execute}}

### See the created service

Let's see the created ClusterIP ervice

`kubectl get services --namespace dev-1`{{execute}}
