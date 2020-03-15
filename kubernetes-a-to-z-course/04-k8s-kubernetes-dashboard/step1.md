### Disabling the Dashboard addons

Minikube starts with the dashboard enabled by default.
But we will deploy it ourselves. Run this command to disable the addon:

`minikube addons disable dashboard`{{execute}}

### Create namespace

Now we create our usual dev-1 namespace:

`kubectl apply -f ./dev-1-namespace.yaml`{{execute}}

### Create the postgres resources

Create all postgres related resources, this yaml contains the manifest for

- Configmap
- Persistent Volume and claim
- Application deployment
- ClusterIP Service

`kubectl create -f ./postgres-conf-volume-deployment-service.yaml`{{execute}}

Wait for the deployment to be ready.

### Deploy thingsboard

First, make sure that postgres deployment is READY

`kubectl get deployments --namespace dev-1`{{execute}}

Now you may deploy the thingsboard application and service

`kubectl apply -f ./thingsboard-deployment-service.yaml`{{execute}}
