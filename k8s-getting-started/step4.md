## Copy

To copy files from and to a pod

### Copy from pod to local

`kubectl cp thingsboard-xxxxxx:/var/log/thingsboard/install.log ./tb-install.log`

### Copy from local to pod

`kubectl cp ./tb-install.log thingsboard-xxxxxx:/tmp/`

### Cat copied file

`kubectl exec thingsboard-xxxxxx -- cat /tmp/tb-install.log`

## Interactive Shell

We can also get the interfactive shell of a pod

## Get bash interfactive shell

Replace xxxxx with the pod suffix

`kubectl exec thingsboard-xxxxxx -it bash`

## Exit bash

Exit the interactive shell

`exit`{{execute}}
