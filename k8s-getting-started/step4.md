## Copy

To copy files from and to a pod.

### Copy from pod to local

`kubectl cp thingsboard-xxxxxx:/var/log/thingsboard/install.log ./tb-install.log`{{copy}}

Replace the `xxxxxx` part with the suffix shown on your pod. To get this, simply run:

`kubectl get pods`{{execute}}

### Copy from local to pod

`kubectl cp ./tb-install.log thingsboard-xxxxxx:/tmp/`{{copy}}

### Print the copied file content

`kubectl exec thingsboard-xxxxxx -- cat /tmp/tb-install.log`{{copy}}

## Interactive Shell

We may also get the interfactive shell of a specific pod.

## Get bash interfactive shell

Run this command to get an interactive shell:

`kubectl exec thingsboard-xxxxxx -it bash`

## Exit bash

Exit the interactive shell:

`exit`{{execute}}

## Done

You have completed this Scenario. You may stop the cluster now.

`minikube stop`{{execute}}
