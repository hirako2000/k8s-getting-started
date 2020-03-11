### Deploy the thingsboard webapp

First, make sure that postgres deployment is READY

`kubectl get deployments --namespace dev-1`{{execute}}

Also ensure that the CluserIP service is now created.

Why? The thingsboard app will connect to the database at startup, if the database isn't running, the deployment would fail.

`kubectl get services --namespace dev-1`{{execute}}

Now you may deploy the thingsboard application

`kubectl apply -f ./thingsboard-deployment.yaml`{{execute}}

### Create a NodePort Service using specification file

Finally, we expose the web application externally:

`kubectl apply -f ./thingsboard-service.yaml`{{execute}}

## Access the Webapp from external network

### Open the web interface

Click on `Select Port to view on Host 1` using the (+) menu item next to the Terminal tab
Enter the port generated by the NodePort service.

You may see the generated port by running:

`kubectl get service thingsboard-service --namespace dev-1`{{execute}}

Take note of the generated port shown as 80:**port**/TCP

```bash
NAME                  TYPE       PORT(S)
thingsboard-service   NodePort   80:32464/TCP
```

**To login:**

- System Administrator: sysadmin@thingsboard.org / sysadmin
- Tenant Administrator: tenant@thingsboard.org / tenant
- Customer User: customer@thingsboard.org / customer